# CROSS-COMPILING
Installing a distro for ARM. The distro is CRUX, the target is an Odroid C2. The device will appears as "_/dev/mmcblk0_" (with "_/dev/mmcblk0p1_" and "_/dev/mmcblk0p2_" as the partitions) in the target machine, but it can be seen as "_/dev/sdX_" in your x86 computer. The unpacking tool is provided by [Atool](http://www.nongnu.org/atool/).


## TOC
1. [CROSS COMPILATION TOOLS](#cross-compilation-tools)  
2. [PARTITIONING](#partitioning)  
3. [MOUNTING](#mounting)  
4. [ROOT PARTITION](#root-partition)  
5. [BOOT PARTITION](#boot-partition)  
6. [COMPILING KERNEL](#compiling-kernel)  
7. [BOOTLOADER](#bootloader)  


## CROSS COMPILATION TOOLS
Installing GCC cross compilation tools (for the X86 machine, not target ARM). Includes binutils.

* OPTION 1: Proportioned by [Linaro](https://releases.linaro.org/components/toolchain/binaries/latest/aarch64-linux-gnu/)  
```
wget -c https://releases.linaro.org/components/toolchain/binaries/latest/aarch64-linux-gnu/gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar.xz
aunpack gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar.xz
```  

* OPTION 2: From repository (Devuan example)  
`sudo apt-get install gcc-arm-none-eabi`  
NOTE: Check your tools are up-to-date to prevent errors like the lack of option _"-mgeneral-regs-only"_.

Name of "_CROSS_COMPILE_" variable will change depending on the choosen option. This guide assumes cross-compilation tools are from Linaro and therefore will equal to "_CROSS\_COMPILE=<LINARO\_TOOLS\_DIRECTORY>/bin/aarch64-linux-gnu-_"


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
* Create root partition  
`n`  
* Make primary partition  
`p`  
* Choose partition number  
`2`  
* Assign start of root partition at the end of the boot partition  
`134220802`  
* Assign end of root partition (the rest of the drive by default) by pressing ENTER  
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


## MOUNTING
* Mount root filesystem  
`mount /dev/sdX2 /mnt`  
* Create boot directory  
`mkdir /mnt/boot`  
* Mount boot filesystem  
`mount /dev/sdX1 /mnt/boot`  


## ROOT PARTITION
Can be the rest of the disk.

* Go to root directory  
`cd /mnt/`  
* Download CRUX image  
`wget -c http://resources.crux-arm.nu/files/devel-test/3.3/crux-arm-rootfs-3.3-64b-RC2.tar.xz`  
* Extract CRUX image to root directory  
`aunpack crux-arm-rootfs-3.3-64b-RC2.tar.xz --extract-to=/mnt`  
* Change network interface with the rules you want (IP, gateway, domain, etc).  
`elvis /etc/rc.d/net`  
* On the "/etc/resolv.conf.head" file set your preferred DNS provider (this example is from OpenNIC).  
`nameserver 185.121.177.177`  
* Change the "/etc/fstab" file with appropriate filesystems.  
```
/dev/sda1    /boot    <BOOTLOADER_FILESYSTEM>    defaults 0 1
/dev/sda2    /    <ROOT_FILESYSTEM>      errors=remount-ro,noatime 0 1
```  
* Uncomment the lines referring to "devpts", "tmp", and "shm" as some programs require it (Firefox), also "USB" and or "cdrom" if using those.
* Change the font, keyboard, timezone, hostname and services on the "/etc/rc.conf" file.
`ls /usr/share/kbd/keymaps/`  


## BOOT PARTITION
Must be FAT32 and 64 MB minimum.

* Clone kernel repo to destination "odroidc2-kernel-folder"  
`git clone --depth 1 --single-branch https://github.com/hardkernel/linux.git --branch odroidc2-v3.16.y odroidc2-kernel-folder`
* Enter destination folder  
`cd odroidc2-kernel-folder`

* OPTION 1: Make kernel config (oneliner)  
`make ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- odroidc2_defconfig`

* OPTION 2: Make kernel config  
```
export ARCH=arm64
export CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu-
make odroidc2_defconfig
```

* Refine configuration  
`make menuconfig`


## COMPILING KERNEL
* Compiling the devicetree blobs  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_DTBS_PATH=/mnt/boot/dtbs/ dtbs`
* Compiling the kernel  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_PATH=/mnt/boot/ Image`
* Compiling the modules  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_MOD_PATH=/mnt/ modules`
* Installing the kernel to destination "/mnt/boot/Image"  
`cp arch/arm64/boot/Image /mnt/boot/`
* Creating the devicetree directory  
`mkdir /mnt/boot/dtbs/`
* Installing the devicetree blobs to destination "/mnt/boot/dtbs/meson64_odroidc2.dtb"  
`cp arch/arm64/boot/dts/meson64_odroidc2.dtb /mnt/boot/dtbs/`
* Installing the modules to destination "INSTALL_MOD_PATH=/mnt/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_MOD_PATH=/mnt/ modules_install`
* Compiling the firmware to destination "INSTALL_FW_PATH=/mnt/lib/firmware/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_FW_PATH=/mnt/lib/firmware/ firmware_install`
* Compiling the kernel C headers to destination "INSTALL_HDR_PATH=/mnt/usr/"  
`make -j 4 ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- INSTALL_HDR_PATH=/mnt/usr/ headers_install`  


## BOOTLOADER
Minimum 3072 bytes free at the start of the drive and before the boot partition.

* OPTION 1: Download and extract the binary  
```
wget -c http://mirror.archlinuxarm.org/aarch64/alarm/uboot-odroid-c2-2015.01-17-aarch64.pkg.tar.xz
aunpack uboot-odroid-c2-2015.01-17-aarch64.pkg.tar.xz --extract-to=/mnt/boot
cd /mnt/boot
```  

* OPTION 2: Compile the bootloader yourself  
```
git clone https://github.com/hardkernel/u-boot.git -b odroidc2-v2015.01
cd u-boot
make ARCH=arm64 CROSS_COMPILE=<LINARO_TOOLS_DIRECTORY>/bin/aarch64-linux-gnu- odroidc2_defconfig
make -j4
cd boot
```  

* Flash the bootloader  
```
chmod +x sd_fusing.sh
./sd_fusing.sh /dev/sdX
```
* Notice the target is the device NOT a partition  
* Set resolution by editing file root/boot/boot.ini  
* Might want to comment out the display-autodetect option  


And done. Next follow the distro tweaks: https://github.com/mayfrost/guides/blob/master/DISTROS.md
Also check the list of software alternative to bloatware and support minimalism https://github.com/mayfrost/guides/blob/master/ALTERNATIVES.md
