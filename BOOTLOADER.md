# BOOTLOADER
* The drive where bootloaders and OSes are installed on these examples is "_/dev/sda_", but could be anywhere.
* The bootloader installation __IS__ inside chroot AND with drives mounted, so this guide assumes you are inside "_/mnt/drive_".
* "_<PARTITION_NUMBER_OF_ROOT>_", "_<PARTITION_NUMBER_OF_FREEDOS>_" and "_<PARTITION_NUMBER_OF_WINDOWS>_" are just the numbers of partitions.
* Specifically, "_<PARTITION_NUMBER_OF_ROOT>_" is the partition number of your root partition.
* The "_vmlinuz_" file makes reference to the kernel image, you can rename it or simlink to it in all cases, the only rule is you have to make sure the name is referenced correctly in the bootloader. By default it can have names like "_vmlinuz-linux_", "_vmlinuz-<KERNEL_VERSION>_" and so on. The same with "_initramfs.img_", it can be "_initramfs-<KERNEL_VERSION>.img_" and such.
* All bootloader examples have included other OS inside what is called "_stanzas_".
* FreeDOS and Windows stanzas are __OPTIONAL__.
* If dualbooting with Windows remember that it likes to be in the first partition.
* If on UEFI check if module is loaded by issuing "_modprobe efivars_".
* On __CRUX__ do "_prt-get remove lilo_" if you dont use LILO.
* On __Source Mage GNU/Linux__ do "_cast \<BOOTLOADER>_" to install the preferred bootloader.

Supported filesystems by bootloaders, they will boot the OS only if the "_/boot_" partition has a supported filesystem. If on "_UEFI_" ignore this as it only supports "_FAT_".:
* __SYSLINUX__: ext2, ext3, ext4, btrfs, ufs 1/2, FAT16, FAT32, iso9660, udf, NTFS.
* __GRUB 2__: ext2, ext3, ext4, btrfs, zfs, ufs, minix, iso9660, udf, jfs, hfs, hfs+, afs, affs, sfs, xfs, reiserfs, tar, cpio, NTFS, FAT16, FAT32.

## SYSLINUX
* If on BIOS make directory and copy files accordingly  
```  
mkdir -p /boot/syslinux
cp /usr/lib/syslinux/bios/*.c32 /boot/syslinux/  
```
* If on UEFI make directory and copy files accordingly  
```  
mkdir -p /boot/efi/EFI/syslinux
cp -r /usr/lib/syslinux/efi64/* /boot/efi/EFI/syslinux/  
```
* If on BIOS set boot entry  
```  
umount /dev/sda1
syslinux --directory syslinux --install /dev/sda1
mount /dev/sda1 /boot  
```
* If on UEFI set boot entry using "_efibootmgr_"  
```  
umount /dev/sda1
efibootmgr -c -d /dev/sda -p 1 -l /boot/efi/EFI/syslinux/syslinux.efi -L Syslinux
mount /dev/sda1 /boot/efi  
```
* Edit "_/boot/syslinux/syslinux.cfg_" if on BIOS or "_/boot/efi/EFI/syslinux/syslinux.cfg_" if on UEFI
* "_splash.png_" is the splash screen image located in "_/boot/syslinux/_" if on BIOS or "_/boot/efi/EFI/syslinux/_" if on UEFI  
```  
PROMPT 1
TIMEOUT 50
MENU BACKGROUND splash.png
DEFAULT <DISTRO_NAME>
LABEL <DISTRO_NAME>
      MENU LABEL <DISTRO_NAME>
      LINUX /boot/vmlinuz
      INITRD /boot/initramfs.img
LABEL FreeDOS
      MENU LABEL FreeDOS
      KERNEL chain.c32
      APPEND sda <PARTITION_NUMBER_OF_FREEDOS>
LABEL Windows7
      MENU LABEL Windows7
      KERNEL chain.c32
      APPEND sda <PARTITION_NUMBER_OF_WINDOWS>  
```

## GRUB 2
* If on BIOS set boot entry (boot partition must be mounted)  
```  
mount /dev/sda1 /boot
grub-install /dev/sda  
```
* If on UEFI set boot entry (boot partition must be mounted)  
```  
mount /dev/sda1 /boot/efi
grub-install /boot/efi  
```
* If Grub does not detect your OS run "_os-prober_" followed by "_update-grub_"
* Or add the OS manually to the Grub config file "_/etc/grub.d/40_custom_"  
```  
menuentry "FreeDOS" {
set root='(hd0,msdos2)'
linux16 /memdisk
initrd16 /fdboot.img
chainloader +1
}
menuentry "Windows 7" {
insmod part_msdos
insmod ntfs
insmod search_fs_uuid
insmod ntldr
search --fs-uuid --no-floppy --set=root 3482FBC382FB879E
chainloader +1
ntldr /bootmgr
}  
```
* Update config file  
`grub-mkconfig -o /boot/grub/grub.cfg`
