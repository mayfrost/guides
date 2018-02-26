# Initiation Rite

This guide is for those who want to install either CRUX or Source Mage GNU/Linux. It was written so it can be used by both, only diverging on the particular details.
* __CRUX__: A ports based, BSD style init scripts, distro following true KISS principles (Keep It Simple, Stupid).
* __Source Mage GNU/Linux__: Without 3rd party patches, sensible defaults or masked packages, free from obfuscated and pre-configured code, use clean dependencies as they came from upstream developers and can also use flags. 

## START
Boot in UEFI mode if on UEFI, BIOS if on BIOS, and select installation media.
* Make sure your network is up (OPTIONAL)
`dhcpcd <NIC>`
* Temporarily change keyboard (available configurations can be found in /usr/share/keymaps/i386/qwerty)
`loadkeys <KEYMAP>`

## PARTITIONING
Supported filesystems by bootloaders are (if on UEFI ignore this as it only supports FAT):
* LILO: indifferent (anything?)
* SYSLINUX: ext2, ext3, ext4, btrfs, ufs 1/2, FAT16, FAT32, iso9660, udf, NTFS
* GRUB Legacy: FAT16, FAT32, minix, ext2, ext3, ext4, ReiserFS, JFS, XFS, VSTa fs, Btrfs
* GRUB 2: ext2, ext3, ext4, btrfs, zfs, ufs, minix, iso9660, udf, jfs, hfs, hfs+, afs, affs, sfs, xfs, reiserfs, tar, cpio, NTFS, FAT16, FAT32

In these examples we make only two partitions but you can extend this if you know how. The partitions are one root partition, later mounted to /mnt/drive format with mkfs.<ROOT_FILESYSTEM>, and one boot partition, later mounted to /mnt/drive/boot and format with mkfs.<BOOTLOADER_FILESYSTEM> unless is UEFI in which case mkfs.vfat is the only format available and will be mounted to /mnt/drive/boot/efi.

* Use parted  
`parted /dev/sda`
* Inside parted, if on UEFI label the disk "gpt", but if on BIOS label it "msdos"  
`mklabel <LABEL>
unit mb
mkpart primary 0g 128
mkpart primary 128 -1
toggle 1 boot
p free
quit`

* Make boot filesystem according to supported bootloader or just "mkfs.vfat" if on UEFI  
`mkfs.<BOOTLOADER_FILESYSTEM> /dev/sda1`
* Make root filesystem according to your personal preference  
`mkfs.<ROOT_FILESYSTEM> /dev/sda2
mkdir /mnt/drive
mount /dev/sda2 /mnt/drive`
* If on BIOS make directory and mount  
`mkdir /mnt/drive/boot
mount /dev/sda1 /mnt/drive/boot`
* If on UEFI make directory and mount  
`mkdir -p /mnt/drive/boot/efi
mount /dev/sda1 /mnt/drive/boot/efi
cd /mnt/drive
mount --bind /dev /mnt/drive/dev
mount --bind /sys /mnt/drive/sys
mount -t proc none /mnt/drive/proc
mount -t devpts none /mnt/drive/dev/pts`

## SETUP

* On CRUX run setup, and if on UEFI select on setup grub2-efi (if using GRUB 2), efibootmgr, and elfutils from opt (only select core, and say yes when you're asked if you want to select individual packages). And if you are not using LILO de-select it from core.
* On Source Mage GNU/Linux get the tarball  
`cd /mnt/drive
wget -c "http://download.sourcemage.org/image/official/smgl-stable-<version>-basesystem-x86_64.<compression>"
tar xvf smgl-stable-<version>-basesystem-x86_64.<compression>`

* Chroot specifying Bash in case live media has another shell  
`chroot /mnt/drive /bin/bash`

* Change root password in chroot (TEST IF YOUR KEYBOARD HAS ALL THE CORRECT MAPPINGS before you change the password)  
`passwd root`

### Change the network interfaces
* On CRUX modify /etc/rc.d/net with the rules you want (IP, gateway, domain, etc)  
`nano /etc/rc.d/net`
* On Source Mage GNU/Linux add preferred interfaces for example  
`nano /etc/network/interfaces`
`auto eth0
allow-hotplug eth0
iface eth0 inet dhcp`
* On /etc/resolv.conf.head set your preferred DNS provider (this example is from OpenNIC)  
`nano /etc/resolv.conf.head`
`nameserver 193.41.79.236`
* Or copy the resolv.conf file from /etc to /mnt/etc BEFORE chrooting

* Change the fstab with appropriate filesystems  
`nano /etc/fstab`
`/dev/sda1    /boot    <BOOTLOADER_FILESYSTEM>    defaults    0 2
/dev/sda2    /    <ROOT_FILESYSTEM>    noatime    0 1`
* On CRUX uncomment the lines referring to devpts, tmp, and shm as some programs require it (Firefox), also USB and or cdrom if using those
* If on UEFI replace /boot with /boot/efi

* On CRUX change the font, keyboard, timezone, hostname and services  
`ls /usr/share/kbd/keymaps/
nano /etc/rc.conf`
* On Source Mage GNU/Linux change the keymaps  
`ls /usr/share/keymaps/i386/qwerty
nano /etc/sysconfig/keymap`
* On CRUX generate locales (change interface language)  
`localedef -i <LOCALE> -f ISO-<CODE> <LOCALE>`
* On Source Mage GNU/Linux generate locales (change interface language)  
`cast -r locale`

## BOOTLOADER
* The drive where bootloaders and OSes are installed on these examples is /dev/sda, bu could be anywhere.
* The bootloader installation IS inside chroot AND with drives mounted, so this guides assumes you are inside "/mnt/drive".
* The "vmlinuz" makes reference to the kernel image, you can rename it or simlink to it in all cases, the only rule is you have to make sure the name is referenced correctly in the bootloader. By default it can have names like vmlinuz-linux, vmlinuz-<KERNEL_VERSION> and so on. The same with initramfs.img, it can be initramfs-<KERNEL_VERSION>.img and such.
* All bootloader examples have included other OS inside what is called "stanzas".
* FreeDOS and Windows stanzas are OPTIONAL.
* If dualbooting with Windows remember that it likes to be in the first partition.
* If on UEFI check if module is loaded by issuing `modprobe efivars`.
* On CRUX do `prt-get remove lilo` if you dont use LILO.
* On Source Mage GNU/Linux do `cast <BOOTLOADER>` to install the preferred bootloader.

### LILO
* If on UEFI use elilo and change names to /etc/elilo.conf instead of /etc/lilo.conf and elilo instead of lilo in commands  
`nano /etc/lilo.conf`
* Inserting password=<PASSWORD> inside an OS stanza will protect with a password the that OS, but inserting password=<PASSWORD> just before the stanzas will protect with a password the bootloader instead (notice the space inside stanzas)  
`boot = /dev/sda
image = /boot/vmlinuz
     Label = CRUX
     root = /dev/sda<PARTITION_NUMBER_OF_DISTRO>
other = /dev/sda<PARTITION_NUMBER_OF_FREEDOS>
     table = /dev/sda
     Label = FreeDos
other = /dev/sda<PARTITION_NUMBER_OF_WINDOWS>
     table = /dev/sda
     Label = Windows7`
`lilo -A /dev/sda 1
lilo`
* In case you used a password prevent anyone but root of reading the config file  
`chmod 600 /etc/lilo.conf`

### SYSLINUX
* If on BIOS make directory and copy files accordingly  
`mkdir -p /boot/syslinux
cp /usr/lib/syslinux/bios/*.c32 /boot/syslinux/`
* If on UEFI make directory and copy files accordingly  
`mkdir -p /boot/efi/EFI/syslinux
cp -r /usr/lib/syslinux/efi64/* /boot/efi/EFI/syslinux/`
* If on BIOS setup boot entry  
`umount /dev/sda1
syslinux --directory syslinux --install /dev/sda1
mount /dev/sda1 /boot`
* If on UEFI setup boot entry using efibootmgr  
`umount /dev/sda1
efibootmgr -c -d /dev/sda -p 1 -l /boot/efi/EFI/syslinux/syslinux.efi -L Syslinux
mount /dev/sda1 /boot/efi`
* Edit /boot/syslinux/syslinux.cfg if on BIOS or /boot/efi/EFI/syslinux/syslinux.cfg if on UEFI
* splash.png is the splash screen image located in /boot/syslinux/ if on BIOS or /boot/efi/EFI/syslinux/ if on UEFI  
`PROMPT 1
TIMEOUT 50
MENU BACKGROUND splash.png
DEFAULT CRUX
LABEL CRUX
      MENU LABEL CRUX
      LINUX /boot/vmlinuz
      INITRD /boot/initramfs.img
LABEL FreeDOS
      MENU LABEL FreeDOS
      KERNEL chain.c32
      APPEND sda <PARTITION_NUMBER_OF_FREEDOS>
LABEL Windows7
      MENU LABEL Windows7
      KERNEL chain.c32
      APPEND sda <PARTITION_NUMBER_OF_WINDOWS>`

### GRUB Legacy
* If on BIOS setup boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot
grub-install /dev/sda`
* If on UEFI setup boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot/efi
grub-install /boot/efi`
* Edit configuration file  
`nano /boot/grub/menu.lst`
`default=0
timeout=10
splashimage=(hd0,0)/grub/splash.xpm.gz
#hiddenmenu
title <DISTRO_NAME> (<KERNEL_VERSION>)
        root (hd0,<PARTITION_NUMBER_OF_DISTRO>)
        kernel /vmlinuz-<KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet
        initrd /initramfs-<KERNEL_VERSION>.img
title <DISTRO_NAME_alternative_kernel> (<ANOTHER_KERNEL_VERSION>)
        root (hd0,<PARTITION_NUMBER_OF_DISTRO>)
        kernel /vmlinuz-<ANOTHER_KERNEL_VERSION> ro root=/dev/sda5 rhgb quiet
        initrd /initramfs-<ANOTHER_KERNEL_VERSION>.img
title FreeDOS
        root (hd0,<PARTITION_NUMBER_OF_FREEDOS>)
        kernel /memdisk
        initrd (hd0,<PARTITION_NUMBER_OF_FREEDOS>)/fdboot.img
title Windows 7
        root (hd0,<PARTITION_NUMBER_OF_WINDOWS>)
        chainloader /EFI/Microsoft/Boot/bootmgfw.efi`

### GRUB 2
* If on BIOS setup boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot
grub-install /dev/sda`
* If on UEFI setup boot entry (boot partition must be mounted)  
`mount /dev/sda1 /boot/efi
grub-install /boot/efi`
* If Grub does not detect your OS run "os-prober" followed by "update-grub", or add the OS manually to the Grub config file  
`nano /etc/grub.d/40_custom`
`menuentry "FreeDOS" {
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
}`
* Update config file  
`grub-mkconfig -o /boot/grub/grub.cfg`
