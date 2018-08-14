# CROSS-COMPILING
Installing a distro for ARM. The distro is CRUX, the target is an Odroid C2.


## TOC
1. [CROSS COMPILATION TOOLS](#cross-compilation-tools)  
2. [PARTITIONING](#partitioning)  
3. [BOOTLOADER](#bootloader)  
4. [BOOT PARTITION](#boot-partition)  
5. [ROOT PARTITION](#root-partition)  
6. [COMPILING](#compiling)  


## CROSS COMPILATION TOOLS
Installing cross GCC compilation tools (for the X86 machine, not target ARM). Includes binutils.

* OPTION 1: from repository (Devuan example)  
`sudo apt-get install gcc-arm-none-eabi`

* OPTION 2: proportioned by odroid  
```
wget http://odroid.in/guides/ubuntu-lfs/arm-unknown-linux-gnueabi.tar.xz
tar -Jxf arm-unknown-linux-gnueabi.tar.xz
```  

Name of "_CROSS_COMPILE_" variable will change depending on the choosen option. This guide assumes from repository and therefore will equal to "_CROSS\_COMPILE=arm-none-eabi-_"


## PARTITIONING
* clear the section for the bootloader  
`dd if=/dev/zero of=/dev/mmcblk0 bs=1M count=8`  
* enter fdisk  
`fdisk /dev/mmcblk0`  
* help  
`m`  
* create new MBR partition table  
`o`  
* create boot partition  
`n`  
* assign start of boot partition at the end of the bootloader space  
`3073`  
* assign end of boot partition  
`+128M`  
* create root partition  
`n`  
* press enter twice to use the rest of the disk  
* Make root filesystem  
`mkfs.<ROOT_FILESYSTEM> /dev/mmcblk0p2`  
* Make boot filesystem according to supported bootloader (only "_mkfs.vfat_")  
`mkfs.<BOOTLOADER_FILESYSTEM> /dev/mmcblk0p1`  


## BOOTLOADER
Minimum 3072 bytes free at the start of the drive and before the boot partition.

* VERSION 1: compile  
```
git clone https://github.com/hardkernel/u-boot.git -b odroidc2-v2015.01
cd u-boot
make ARCH=arm64 CROSS_COMPILE=arm-none-eabi- odroidc2_defconfig
make -j4
cd boot
```

* VERSION 2: download and extract the binary  
```
wget http://odroid.in/guides/ubuntu-lfs/boot.tar.gz # http://dn.odroid.com/S905/BootLoader/ODROID-C2/c2_boot_release_ubuntu.tar.gz
tar -zxvf boot.tar.xz
cd boot
```

* flash bootloader  
```
chmod +x sd_fusing.sh
./sd_fusing.sh /dev/sdX
```
* notice the target is the device NOT any partition  
* set resolution by editing file root/boot/boot.ini  
* might want to comment-out the display-autodetect option  


## BOOT PARTITION
Must be FAT32 and 64 MB minimum.

* cloning kernel repo to destination "odroidc2-kernel-folder"  
`git clone --depth 1 --single-branch https://github.com/hardkernel/linux.git --branch odroidc2-v3.16.y odroidc2-kernel-folder`
* enter destination folder  
`cd odroidc2-kernel-folder`

* OPTION 1: making kernel config  
`make ARCH=arm64 CROSS_COMPILE=arm-none-eabi- odroidc2_defconfig`

* OPTION 2: making kernel config  
```
export ARCH=arm64
export CROSS_COMPILE=arm-none-eabi-
make odroidc2_defconfig
```

* Refine configuration  
`make menuconfig`


## COMPILING
* Compiling devicetree blobs to destination "INSTALL_DTBS_PATH=/mnt/boot/dtbs/meson64_odroidc2.dtb"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=arm-none-eabi- INSTALL_DTBS_PATH=/mnt/boot/dtbs/ dtbs`
* Compiling kernel to destination "INSTALL_PATH=/mnt/boot/Image"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=arm-none-eabi- INSTALL_PATH=/mnt/boot/ Image`
* Compiling the modules to destination "INSTALL_MOD_PATH=/mnt/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=arm-none-eabi- INSTALL_MOD_PATH=/mnt/ modules_install`
* Compiling firmware to destination "INSTALL_FW_PATH=/mnt/lib/firmware/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=arm-none-eabi- INSTALL_FW_PATH=/mnt/lib/firmware/ firmware_install`
* Compiling kernel C headers to destination "INSTALL_HDR_PATH=/mnt/usr/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=arm-none-eabi- INSTALL_HDR_PATH=/mnt/usr/ headers_install`


## ROOT PARTITION
Can be the rest of the disk.

* Download CRUX image  
`wget -c http://resources.crux-arm.nu/files/devel-test/3.3/crux-arm-rootfs-3.3-64b-RC2.tar.xz`
