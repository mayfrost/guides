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
6. [THE END](#the-end)  

## START
Boot in UEFI mode if on UEFI, BIOS if on BIOS, and select installation media.
* Make sure your network is up (OPTIONAL)  
`dhcpcd <NIC>`
* Temporarily change keyboard (available configurations can be found in the directories "_/usr/share/kbd/keymaps/_" for __CRUX__ and "_/usr/share/keymaps/i386/qwerty_" for __Source Mage GNU/Linux__)  
`loadkeys <KEYMAP>`

## PARTITIONING

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
* Mount everything else  
`mkdir -p /mnt/drive/{dev,sys,proc,tmp,usr/src,var}`  
`cd /mnt/drive`  
`mount --bind /dev /mnt/drive/dev`  
`mount --bind /tmp /mnt/drive/tmp`  
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
Next are simple examples of compiling the kernel, for a more in depth view see https://github.com/mayfrost/guides/blob/master/KERNEL.md  
* On __CRUX__  
`cd /usr/src/linux-<VERSION>`  
`make all modules_install install`  

* On __Source Mage GNU/Linux__ (__OPTIONAL__)  
`cast -r linux`

## BOOTLOADER
Next is a simple example of setting the bootloader, for a more in depth view see https://github.com/mayfrost/guides/blob/master/BOOTLOADER.md  

### LILO
* If on UEFI use __elilo__ and change names to "_/etc/elilo.conf_" instead of "_/etc/lilo.conf_" and "_elilo_" instead of "_lilo_" in commands  
`nano /etc/lilo.conf`
* Inserting "_password=\<PASSWORD>_" inside an OS stanza will protect with a password that OS, but inserting "_password=\<PASSWORD>_" just before the stanzas and outside any of them will protect with a password the bootloader itself (notice the space inside stanzas)  
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

## THE END
* Exit the chroot  
`exit`
* Shutdown the machine  
`shutdown -h now`  

And done. For more information on both distros and what to do next see https://github.com/mayfrost/guides/blob/master/DISTROS.md
