# Initiation Rite

This guide is for those wanting one of the two most beautiful source based distros, either __CRUX__ or __Source Mage GNU/Linux__. It was written so it can be used by both, only diverging on particular details.
* __CRUX__: A ports based, BSD style init scripts, distro following true KISS principles (Keep It Simple).  
* __Source Mage GNU/Linux__: Without 3rd party patches, sensible defaults or masked packages, free from obfuscated and pre-configured code, use clean dependencies as they came from upstream developers and can also use flags.  

__NOTE__: This guide attempts to describe __UEFI__ in detail side by side with __BIOS__. Also describes dualbooting (and triple booting) with the bootloader. If you feel overwhelmed for the amount of information don't be afraid, most of it is __OPTIONAL__, like password protection of the bootloader and the different filesystems the bootloaders can use.


## TOC
1. [START](#start)  
2. [PARTITIONING](#partitioning)  
3. [SETUP](#setup)  
3.1. [CHROOT](#chroot)  
3.2. [CHANGE NETWORK INTERFACES](#change-network-interfaces)  
3.3. [EDIT FSTAB](#edit-fstab)  
3.4. [SET THE ENVIRONMENT](#setup-the-environment)  
4. [KERNEL](#kernel)  
5. [BOOTLOADER](#bootloader)  
5.1. [LILO](#lilo)  
5.2. [SYSLINUX](#syslinux)  
5.3. [GRUB Legacy](#grub-legacy)  
5.4. [GRUB 2](#grub-2)  
6. [THE END](#the-end)  
7. [CONFIGURATION ON CRUX](#configuration-on-crux)  
7.1. [ENABLE CONTRIB REPO](#enable-contrib-repo)  
7.2. [ADD EXTERNAL REPOS](#add-external-repos)  
7.3. [INSTALL XORG](#install-xorg)  
8. [CRUX COMMANDS](#crux-commands)  
8.1. [AUTOMATED INSTALLATION OF PORTS](#automated-installation-of-ports)  
8.2. [MANUAL DOWNLOAD AND INSTALLATION](#manual-download-and-installation)  
9. [SOURCE MAGE GNU/LINUX COMMANDS](#source-mage-gnu/linu-commands)  

## START
Boot in UEFI mode if on UEFI, BIOS if on BIOS, and select installation media.
* Make sure your network is up (OPTIONAL)  
`dhcpcd <NIC>`
* Temporarily change keyboard (available configurations can be found in the directories "_/usr/share/kbd/keymaps/_" for __CRUX__ and "_/usr/share/keymaps/i386/qwerty_" for __Source Mage GNU/Linux__)  
`loadkeys <KEYMAP>`

## PARTITIONING
Supported filesystems by bootloaders are (if on UEFI ignore this as it only supports FAT):
* __LILO__: indifferent (anything?)
* __SYSLINUX__: ext2, ext3, ext4, btrfs, ufs 1/2, FAT16, FAT32, iso9660, udf, NTFS
* __GRUB Legacy__: FAT16, FAT32, minix, ext2, ext3, ext4, ReiserFS, JFS, XFS, VSTa fs, Btrfs
* __GRUB 2__: ext2, ext3, ext4, btrfs, zfs, ufs, minix, iso9660, udf, jfs, hfs, hfs+, afs, affs, sfs, xfs, reiserfs, tar, cpio, NTFS, FAT16, FAT32

In these examples we make only two partitions but you can extend this if you know how. The partitions are one root partition, later mounted to "_/mnt/drive_" with "_mkfs.<ROOT_FILESYSTEM>_" format, and one boot partition, later mounted to "_/mnt/drive/boot_" and with "_mkfs.<BOOTLOADER_FILESYSTEM>_" format unless is __UEFI__ in which case "_mkfs.vfat_" is the only format available and will be mounted to "_/mnt/drive/boot/efi_" instead.

* Use parted  
`parted /dev/sda`
* Inside parted, if on UEFI label the disk "_gpt_", but if on BIOS label it "_msdos_"  
`mklabel <LABEL>`  
`unit mb`  
`mkpart primary 0g 128`  
`mkpart primary 128 -1`  
`toggle 1 boot`  
`p free`  
`quit`  

* Make root filesystem according to your personal preference  
`mkfs.<ROOT_FILESYSTEM> /dev/sda2`  
`mkdir /mnt/drive`  
`mount /dev/sda2 /mnt/drive`
* Make boot filesystem according to supported bootloader or just "_mkfs.vfat_" if on UEFI  
`mkfs.<BOOTLOADER_FILESYSTEM> /dev/sda1`
* If on BIOS make directory and mount  
`mkdir /mnt/drive/boot`  
`mount /dev/sda1 /mnt/drive/boot`
* If on UEFI make directory and mount  
`mkdir -p /mnt/drive/boot/efi`  
`mount /dev/sda1 /mnt/drive/boot/efi`  
`cd /mnt/drive`  
`mount --bind /dev /mnt/drive/dev`  
`mount --bind /sys /mnt/drive/sys`  
`mount -t proc none /mnt/drive/proc`  
`mount -t devpts none /mnt/drive/dev/pts`

## SETUP
* On __CRUX__ run "_setup_", and if on UEFI select on setup grub2-efi (if using GRUB 2), efibootmgr, and elfutils from opt (only select core, and say yes when you're asked if you want to select individual packages). And if you are not using LILO de-select it from core.
* On __Source Mage GNU/Linux__ get the tarball  
`cd /mnt/drive`  
`wget -c "http://download.sourcemage.org/image/official/smgl-stable-<version>-basesystem-x86_64.<compression>"`  
`tar xvf smgl-stable-<version>-basesystem-x86_64.<compression>`

### CHROOT
* Chroot specifying Bash in case live media has another shell  
`chroot /mnt/drive /bin/bash`
* Change root password in chroot (TEST IF YOUR KEYBOARD HAS ALL THE CORRECT MAPPINGS before you change the password)  
`passwd root`

### CHANGE NETWORK INTERFACES
* On __CRUX__ modify "_/etc/rc.d/net_" with the rules you want (IP, gateway, domain, etc)
* On __Source Mage GNU/Linux__ add preferred interfaces to "_/etc/network/interfaces_" for example  
`auto eth0`  
`allow-hotplug eth0`  
`iface eth0 inet dhcp`
* On the "_/etc/resolv.conf.head_" file set your preferred DNS provider (this example is from OpenNIC)  
`nameserver 193.41.79.236`
* Or copy "_/etc/resolv.conf_" to "_/mnt/etc/resolv.conf_" __BEFORE__ chrooting

### EDIT FSTAB
* Change the "_/etc/fstab_" file with appropriate filesystems  
`/dev/sda1    /boot    <BOOTLOADER_FILESYSTEM>    defaults    0 2`  
`/dev/sda2    /    <ROOT_FILESYSTEM>    noatime    0 1`
* On __CRUX__ uncomment the lines referring to devpts, tmp, and shm as some programs require it (Firefox), also USB and or cdrom if using those
* If on UEFI replace "_/boot_" with "_/boot/efi_"

### SET THE ENVIRONMENT
* On __CRUX__ change the font, keyboard, timezone, hostname and services on the "_/etc/rc.conf_" file  
`ls /usr/share/kbd/keymaps/`
* On __Source Mage GNU/Linux__ change keymaps on the "_/etc/sysconfig/keymap_" file  
`ls /usr/share/keymaps/i386/qwerty`
* On __CRUX__ generate locales (change interface language)  
`localedef -i <LOCALE> -f ISO-<CODE> <LOCALE>`
* On __Source Mage GNU/Linux__ generate locales (change interface language)  
`cast -r locale`

## KERNEL
* Include the filesystem support the boot partition is format in.
* Include UEFI options if on UEFI.
* Include device drivers you need, build the rest as modules.

* On __CRUX__  
`cd /usr/src/linux-<VERSION>`  
`make menuconfig`  
`make all`  
`make modules_install`  
`cp arch/x86/boot/bzImage /boot/vmlinuz`  
`cp System.map /boot`

* On __Source Mage GNU/Linux__ (__OPTIONAL__)  
`cast -r linux`

## BOOTLOADER
* The drive where bootloaders and OSes are installed on these examples is "_/dev/sda_", but could be anywhere.
* The bootloader installation __IS__ inside chroot AND with drives mounted, so this guide assumes you are inside "_/mnt/drive_".
* "_<PARTITION_NUMBER_OF_DISTRO>_", "_<PARTITION_NUMBER_OF_FREEDOS>_" and "_<PARTITION_NUMBER_OF_WINDOWS>_" are just the numbers of partitions.
* The "_vmlinuz_" file makes reference to the kernel image, you can rename it or simlink to it in all cases, the only rule is you have to make sure the name is referenced correctly in the bootloader. By default it can have names like "_vmlinuz-linux_", "_vmlinuz-<KERNEL_VERSION>_" and so on. The same with "_initramfs.img_", it can be "_initramfs-<KERNEL_VERSION>.img_" and such.
* All bootloader examples have included other OS inside what is called "_stanzas_".
* FreeDOS and Windows stanzas are __OPTIONAL__.
* If dualbooting with Windows remember that it likes to be in the first partition.
* If on UEFI check if module is loaded by issuing "_modprobe efivars_".
* On __CRUX__ do "_prt-get remove lilo_" if you dont use LILO.
* On __Source Mage GNU/Linux__ do "_cast <BOOTLOADER>_" to install the preferred bootloader.

### LILO
* If on UEFI use __elilo__ and change names to "_/etc/elilo.conf_" instead of "_/etc/lilo.conf_" and "_elilo_" instead of "_lilo_" in commands  
`nano /etc/lilo.conf`
* Inserting "_password=<PASSWORD>_" inside an OS stanza will protect with a password that OS, but inserting "_password=\<PASSWORD>_" just before the stanzas and outside any of them will protect with a password the bootloader itself (notice the space inside stanzas)  
`boot = /dev/sda`  
`image = /boot/vmlinuz`  
`     Label = <DISTRO_NAME>`  
`     root = /dev/sda<PARTITION_NUMBER_OF_DISTRO>`  
`other = /dev/sda<PARTITION_NUMBER_OF_FREEDOS>`  
`     table = /dev/sda`  
`     Label = FreeDOS`  
`other = /dev/sda<PARTITION_NUMBER_OF_WINDOWS>`  
`     table = /dev/sda`  
`     Label = Windows7`  
* Set boot entry  
`lilo -A /dev/sda 1`  
`lilo`
* Prevent anyone but root of reading the config file (in case you used a password)  
`chmod 600 /etc/lilo.conf`

### SYSLINUX
* If on BIOS make directory and copy files accordingly  
`mkdir -p /boot/syslinux`  
`cp /usr/lib/syslinux/bios/*.c32 /boot/syslinux/`
* If on UEFI make directory and copy files accordingly  
`mkdir -p /boot/efi/EFI/syslinux`  
`cp -r /usr/lib/syslinux/efi64/* /boot/efi/EFI/syslinux/`
* If on BIOS set boot entry  
`umount /dev/sda1`  
`syslinux --directory syslinux --install /dev/sda1`  
`mount /dev/sda1 /boot`
* If on UEFI set boot entry using "_efibootmgr_"  
`umount /dev/sda1`  
`efibootmgr -c -d /dev/sda -p 1 -l /boot/efi/EFI/syslinux/syslinux.efi -L Syslinux`  
`mount /dev/sda1 /boot/efi`
* Edit "_/boot/syslinux/syslinux.cfg_" if on BIOS or "_/boot/efi/EFI/syslinux/syslinux.cfg_" if on UEFI
* "_splash.png_" is the splash screen image located in "_/boot/syslinux/_" if on BIOS or "_/boot/efi/EFI/syslinux/_" if on UEFI  
`PROMPT 1`  
`TIMEOUT 50`  
`MENU BACKGROUND splash.png`  
`DEFAULT <DISTRO_NAME>`  
`LABEL <DISTRO_NAME>`  
`      MENU LABEL <DISTRO_NAME>`  
`      LINUX /boot/vmlinuz`  
`      INITRD /boot/initramfs.img`  
`LABEL FreeDOS`  
`      MENU LABEL FreeDOS`  
`      KERNEL chain.c32`  
`      APPEND sda <PARTITION_NUMBER_OF_FREEDOS>`  
`LABEL Windows7`  
`      MENU LABEL Windows7`  
`      KERNEL chain.c32`  
`      APPEND sda <PARTITION_NUMBER_OF_WINDOWS>`

### GRUB Legacy
* If on BIOS set boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot`  
`grub-install /dev/sda`
* If on UEFI set boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot/efi`  
grub-install /boot/efi`
* Edit configuration file "_/boot/grub/menu.lst_"  
`default=0`  
`timeout=10`  
`splashimage=(hd0,0)/grub/splash.xpm.gz`  
`#hiddenmenu`  
`title <DISTRO_NAME> (<KERNEL_VERSION>)`  
`        root (hd0,<PARTITION_NUMBER_OF_DISTRO>)`  
`        kernel /vmlinuz-<KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet`  
`        initrd /initramfs-<KERNEL_VERSION>.img`  
`title <DISTRO_NAME_alternative_kernel> (<ANOTHER_KERNEL_VERSION>)`  
`        root (hd0,<PARTITION_NUMBER_OF_DISTRO>)`  
`        kernel /vmlinuz-<ANOTHER_KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet`  
`        initrd /initramfs-<ANOTHER_KERNEL_VERSION>.img`  
`title FreeDOS`  
`        root (hd0,<PARTITION_NUMBER_OF_FREEDOS>)`  
`        kernel /memdisk`  
`        initrd (hd0,<PARTITION_NUMBER_OF_FREEDOS>)/fdboot.img`  
`title Windows 7`  
`        root (hd0,<PARTITION_NUMBER_OF_WINDOWS>)`  
`        chainloader /EFI/Microsoft/Boot/bootmgfw.efi`

### GRUB 2
* If on BIOS set boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot`  
`grub-install /dev/sda`
* If on UEFI set boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot/efi`  
`grub-install /boot/efi`
* If Grub does not detect your OS run "_os-prober_" followed by "_update-grub_"
* Or add the OS manually to the Grub config file "_/etc/grub.d/40_custom_"  
`menuentry "FreeDOS" {`  
`set root='(hd0,msdos2)'`  
`linux16 /memdisk`  
`initrd16 /fdboot.img`  
`chainloader +1`  
`}`  
`menuentry "Windows 7" {`  
`insmod part_msdos`  
`insmod ntfs`  
`insmod search_fs_uuid`  
`insmod ntldr`  
`search --fs-uuid --no-floppy --set=root 3482FBC382FB879E`  
`chainloader +1`  
`ntldr /bootmgr`  
`}`
* Update config file  
`grub-mkconfig -o /boot/grub/grub.cfg`

## THE END
* Exit the chroot  
`exit`
* Shutdown the machine  
`shutdown -h now`  

And done.

## CONFIGURATION ON CRUX
### ENABLE CONTRIB REPO
* Enable contrib for ports  
`cd /etc/ports`  
`mv contrib.rsync.inactive contrib.rsync`
* Enable contrib for prt-get  
`nano /etc/prt-get.conf`
* Uncomment line "_prtdir /usr/ports/contrib_"

### ADD EXTERNAL REPOS
* Download httpup/rsync file and pub file  
`cd /etc/ports/`  
`wget -c <URL>`
* Add repo location to "_/etc/prt-get.conf_" (order sets precedence)  
`nano /etc/prt-get.conf`
* Add line "_prtdir /usr/ports/\<REPO>_"
* Populate repo  
`ports -u <REPO>`

* Enable pre-/post-install scripts in "_/etc/prt-get.conf_" (usually safe to run repeatedly, usually used to rebuild caches and add system users when installing certain software)  
`nano /etc/prt-get.conf`
* Uncomment line "_runscripts yes_"

* Ignore footprint mismatches due to new files (usually not a bad thing)  
`nano /etc/pkgmk.conf`
* Set line "_PKGMK_IGNORE_NEW="yes"_"

### INSTALL XORG
* Install a minimal set of xorg and xorg dependent tools one by one
`prtget depinst xorg-server xorg-xf86-video-<DRIVER> xorg-font-<FONT> xkeyboard-config xorg-xinit`
* Alternatively just install the metapackage "_xorg_"

## CRUX COMMANDS
### AUTOMATED INSTALLATION OF PORTS
* Populate ports tree (is empty by default)  
`ports -u`
* Automatically download and build a package with its required dependencies ignoring signature mismatch  
`prt-get -in depinst <PORT>`
* Remove a package  
`prt-get remove <PORT>`
* Search package  
`prt-get search <PORT>`
* Get info from package  
`prt-get info <PORT>`
* Get dependency info from package  
`prt-get depends <PORT>`
* Update all packages  
`prt-get sysup`
* List all installed packages  
`pkginfo -i`

### MANUAL DOWNLOAD AND INSTALLATION
* Go to apropriate directory for all these tasks  
`cd to /usr/ports/<REPO>/<PORT>`
* To download a package  
`pkgmk -d <PORT>`
* To install a downloaded package  
`pkgmk -i <PORT>`
* In case of signature mismatch  
`pkgadd -f <PORT>`
* To clean directory from downloaded package and build  
`pkgadd -c <PORT>`
* To remove installed package  
`pkgrm <PORT>`

## SOURCE MAGE GNU/LINUX COMMANDS
* To get a manual  
`cast smgl-setup`  
`man smgl-setup`
* To change general things like the color scheme  
`sorcery`
* To update the package manager  
`sorcery update`
* To update the package list  
`scribe update`
* To check for any changes in the architecture specs  
`cast smgl-archspecs`
* To rebuild everything from source  
`sorcery rebuild`
* To recompile the kernel  
`cast -r linux`
* To get a list of spells needing upgrade  
`sorcery -q`
* To upgrade the spells themselves known to be available for upgrade  
`cast --queue`
* To check for broken installations  
`cleanse --fix`
* After casting new spells you need this to have apropos, man -k, and whatis  
` makewhatis`
* To install new packages  
`cast <spell>`
* To update an existing package  
`cast <spell>`
* To search for packages  
`gaze search <spell>`
* To search by package name  
`gaze search -name  <spell>`
* To list installed packages  
`gaze installed`
* To remove a spell  
`dispel <spell>`
* To delete completely a package  
`dispel --nosustain <spell>`
* To list repositories  
`scribe index`
* To add a repository  
`scribe add <grimoire>`
* To remove a repository  
`scribe remove <grimoire>`
