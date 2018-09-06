# CROSS-COMPILING
Installing a distro for ARM. The distro is CRUX, the target is an Odroid C2. The device will appears as "_/dev/mmcblk0_" (with "_/dev/mmcblk0p1_" and "_/dev/mmcblk0p2_" as the partitions) in the target machine, but it can be seen as "_/dev/sdX_" in your x86 computer.


## TOC
1. [CROSS COMPILATION TOOLS](#cross-compilation-tools)  
2. [PARTITIONING](#partitioning)  
3. [BOOTLOADER](#bootloader)  
4. [MOUNTING](#mounting)  
5. [BOOT PARTITION](#boot-partition)  
6. [COMPILING KERNEL](#compiling-kernel)  
7. [ROOT PARTITION](#root-partition)  


## CROSS COMPILATION TOOLS
Installing GCC cross compilation tools (for the X86 machine, not target ARM). Includes binutils.

* OPTION 1: From repository (Devuan example)  
`sudo apt-get install gcc-arm-none-eabi`

* OPTION 2: Proportioned by odroid  
```
wget http://odroid.in/guides/ubuntu-lfs/arm-unknown-linux-gnueabi.tar.xz
tar -Jxf arm-unknown-linux-gnueabi.tar.xz
```  

Name of "_CROSS_COMPILE_" variable will change depending on the choosen option. This guide assumes from repository and therefore will equal to "_CROSS\_COMPILE=arm-none-eabi-_"


## PARTITIONING
* Clear the section for the bootloader  
`dd if=/dev/zero of=/dev/sdX bs=1M count=8`  
* Enter fdisk  
`fdisk /dev/sdX`  
* Help  
`m`  
* Create new MBR partition table  
`o`  
* Create boot partition  
`n`  
* Make primary partition  
`p`  
* Choose partition number  
`1`  
* Assign start of boot partition at the end of the bootloader space  
`3073`  
* Assign end of boot partition  
`+128M`  
* Change display units to cylinders  
`u`  
* Create root partition  
`n`  
* Make primary partition  
`p`  
* Choose partition number  
`2`  
* Assign start of boot partition at the end of the bootloader space (default cylinder)  
`131`  
* Assign end of boot partition (default) by pressing ENTER  
* Change display units back to sectors  
`u`  
* Show the partitions  
`p`  
* If you agree save and exit  
`w`  
* If you disagree delete a partition and start from that partition  
`d`  
* or  exit without saving  
`q`  
* Make root filesystem  
`mkfs.<ROOT_FILESYSTEM> /dev/sdX2`  
* Make boot filesystem according to supported bootloader (only "_mkfs.vfat_")  
`mkfs.<BOOTLOADER_FILESYSTEM> /dev/sdX1`  


## BOOTLOADER
Minimum 3072 bytes free at the start of the drive and before the boot partition.

* VERSION 1: Compile bootloader yourself  
```
git clone https://github.com/hardkernel/u-boot.git -b odroidc2-v2015.01
cd u-boot
make ARCH=arm64 CROSS_COMPILE=arm-none-eabi- odroidc2_defconfig
make -j4
cd boot
```

* VERSION 2: Download and extract the binary  
```
wget http://odroid.in/guides/ubuntu-lfs/boot.tar.gz
tar -zxvf boot.tar.gz
cd boot
```  

Alternative download link: http://dn.odroid.com/S905/BootLoader/ODROID-C2/c2_boot_release_ubuntu.tar.gz

* Flash bootloader  
```
chmod +x sd_fusing.sh
./sd_fusing.sh /dev/sdX
```
* Notice the target is the device NOT any partition  
* Set resolution by editing file root/boot/boot.ini  
* Might want to comment-out the display-autodetect option  


## MOUNTING
* Mount root filesystem  
`mount /dev/sdX2 /mnt`  
* Create boot directory  
`mkdir /mnt/boot`  
* Mount boot filesystem  
`mount /dev/sdX1 /mnt/boot`  


## BOOT PARTITION
Must be FAT32 and 64 MB minimum.

* Clone kernel repo to destination "odroidc2-kernel-folder"  
`git clone --depth 1 --single-branch https://github.com/hardkernel/linux.git --branch odroidc2-v3.16.y odroidc2-kernel-folder`
* Enter destination folder  
`cd odroidc2-kernel-folder`

* OPTION 1: Make kernel config (oneliner)  
`make ARCH=arm64 CROSS_COMPILE=arm-none-eabi- odroidc2_defconfig`

* OPTION 2: Make kernel config  
```
export ARCH=arm64
export CROSS_COMPILE=arm-none-eabi-
make odroidc2_defconfig
```

* Refine configuration  
`make menuconfig`


## COMPILING KERNEL
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
* Extract CRUX image  
`aunpack crux-arm-rootfs-3.3-64b-RC2.tar.xz`  
