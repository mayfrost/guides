# BOOTLOADER
* The drive where bootloaders and OSes are installed on these examples is "_/dev/sda_", but could be anywhere.
* The bootloader installation __IS__ inside chroot AND with drives mounted, so this guide assumes you are inside "_/mnt/drive_".
* "_<PARTITION_NUMBER_OF_DISTRO>_", "_<PARTITION_NUMBER_OF_FREEDOS>_" and "_<PARTITION_NUMBER_OF_WINDOWS>_" are just the numbers of partitions.
* The "_vmlinuz_" file makes reference to the kernel image, you can rename it or simlink to it in all cases, the only rule is you have to make sure the name is referenced correctly in the bootloader. By default it can have names like "_vmlinuz-linux_", "_vmlinuz-<KERNEL_VERSION>_" and so on. The same with "_initramfs.img_", it can be "_initramfs-<KERNEL_VERSION>.img_" and such.
* All bootloader examples have included other OS inside what is called "_stanzas_".
* FreeDOS and Windows stanzas are __OPTIONAL__.
* If dualbooting with Windows remember that it likes to be in the first partition.
* If on UEFI check if module is loaded by issuing "_modprobe efivars_".
* On __CRUX__ do "_prt-get remove lilo_" if you dont use LILO.
* On __Source Mage GNU/Linux__ do "_cast \<BOOTLOADER>_" to install the preferred bootloader.

Supported filesystems by bootloaders, they will boot the OS only if the "_/boot_" partition has a supported filesystem. If on "_UEFI_" ignore this as it only supports "_FAT_".:
* __LILO__: indifferent (anything?)
* __SYSLINUX__: ext2, ext3, ext4, btrfs, ufs 1/2, FAT16, FAT32, iso9660, udf, NTFS.
* __GRUB Legacy__: FAT16, FAT32, minix, ext2, ext3, ext4, ReiserFS, JFS, XFS, VSTa fs, Btrfs.
* __GRUB 2__: ext2, ext3, ext4, btrfs, zfs, ufs, minix, iso9660, udf, jfs, hfs, hfs+, afs, affs, sfs, xfs, reiserfs, tar, cpio, NTFS, FAT16, FAT32.

## LILO
* If on UEFI use __elilo__ and change names to "_/etc/elilo.conf_" instead of "_/etc/lilo.conf_" and "_elilo_" instead of "_lilo_" in commands.  
`nano /etc/lilo.conf`
* Inserting "_password=\<PASSWORD>_" inside an OS stanza will protect with a password that OS, but inserting "_password=\<PASSWORD>_" just before the stanzas and outside any of them will protect with a password the bootloader itself (notice the space inside stanzas)  
`boot = /dev/sda`  
`image = /boot/vmlinuz`  
`     Label = <DISTRO_NAME>`  
`     root = /dev/sda<PARTITION_NUMBER_OF_ROOT>`  
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

## SYSLINUX
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

## GRUB Legacy
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
`        root (hd0,<PARTITION_NUMBER_OF_ROOT>)`  
`        kernel /vmlinuz-<KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet`  
`        initrd /initramfs-<KERNEL_VERSION>.img`  
`title <DISTRO_NAME_alternative_kernel> (<ANOTHER_KERNEL_VERSION>)`  
`        root (hd0,<PARTITION_NUMBER_OF_ROOT>)`  
`        kernel /vmlinuz-<ANOTHER_KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet`  
`        initrd /initramfs-<ANOTHER_KERNEL_VERSION>.img`  
`title FreeDOS`  
`        root (hd0,<PARTITION_NUMBER_OF_FREEDOS>)`  
`        kernel /memdisk`  
`        initrd (hd0,<PARTITION_NUMBER_OF_FREEDOS>)/fdboot.img`  
`title Windows 7`  
`        root (hd0,<PARTITION_NUMBER_OF_WINDOWS>)`  
`        chainloader /EFI/Microsoft/Boot/bootmgfw.efi`

## GRUB 2
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
