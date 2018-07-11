# Initiation Rite

This guide is for those wanting one of the two most beautiful source based distros, either __CRUX__ or __Source Mage GNU/Linux__. It was written so it can be used by both, only diverging on particular details.
* __CRUX__: A ports based, BSD style init scripts, distro following true KISS principles (Keep It Simple).  
* __Source Mage GNU/Linux__: Without 3rd party patches, sensible defaults or masked packages, free from obfuscated and pre-configured code, use clean dependencies as they came from upstream developers and can also use flags.  

__NOTE__:
* This guide attempts to describe __UEFI__ in detail side by side with __BIOS__. Also describes dualbooting (and triple booting) with the bootloader. If you feel overwhelmed for the amount of information don't be afraid, most of it is __OPTIONAL__, like password protection of the bootloader and the different filesystems the bootloaders can use.  
* For __CRUX__ you should be using their "_iso_".  
* For __Source Mage GNU/Linux__ you will be using their "_chroot image_" but __NOT__ the "_iso_", you can use any live CD or USB provided it has the commands here mentioned.  


## TOC
1. [START](#start)  
2. [PARTITIONING](#partitioning)  
3. [FILESYSTEM](#filesystem)  
4. [CREATING (AND MOUNTING) MAIN DIRECTORIES](#creating-and-mounting-main-directories)  
5. [SETUP](#setup)  
5.1. [CHROOT](#chroot)  
5.2. [CHANGE NETWORK INTERFACES](#change-network-interfaces)  
5.3. [EDIT FSTAB](#edit-fstab)  
5.4. [SET THE ENVIRONMENT](#setup-the-environment)  
6. [KERNEL](#kernel)  
7. [BOOTLOADER](#bootloader)  
7.1. [LILO](#lilo)  
8. [THE END](#the-end)  

## START
Boot in UEFI mode if on UEFI, BIOS if on BIOS, and select installation media. Then once you have a terminal:
* Check which NIC you are using.  
`ip addr`  
* Make sure your network is up.  
```ip link set <NIC> up
dhcpcd <NIC>
```

In the case you need Wi-Fi please refer to https://github.com/mayfrost/guides/blob/master/NETWORKING.md  

* Temporarily change keyboard to your mapping (available configurations can be found in the directories "_/usr/share/kbd/keymaps/_" for __CRUX__ and "_/usr/share/keymaps/i386/qwerty_" for __Source Mage GNU/Linux__).  
`loadkeys <KEYMAP>`  

## PARTITIONING

In these examples we make only two partitions but you can extend this if you know how. The partitions are one root partition, later mounted to "_/mnt_" with "_mkfs.<ROOT_FILESYSTEM>_" format, and one boot partition, later mounted to "_/mnt/boot_" and with "_mkfs.<BOOTLOADER_FILESYSTEM>_" format unless is __UEFI__ in which case "_mkfs.vfat_" is the only format available and will be mounted to "_/mnt/boot/efi_" instead.

* Use parted.  
`parted /dev/sda`
* Inside parted, if on UEFI label the disk "_gpt_", but if on BIOS label it "_msdos_".  
```
mklabel <LABEL>
unit mb
mkpart primary 0g 128
mkpart primary 128 -1
toggle 1 boot
p free
quit
```

## FILESYSTEM

Choose your preferred filesystem. Common filesystem types are:  
* __JFS__: Good read/write performance and crash recovery, reliable for low end computers like laptops and old computers.  
* __Reiser4__: High performance filesystem for use in performance intensive environments like multimedia workstations and gaming rigs.  
* __EXT4__: The newest version of the classic Linux filesystem and the one with most support, excels at a high quantity of files and nested directories. Ideal for FTP and fileservers.  
* __XFS__: Popular for its good handling of large files, its best use is in big, enterprise level databases.  
* __VFAT__: Most recent version of the filesystem from the time of DOS, most suitable for EFI partitions than anything else.  

Look into each one and decide for your use case. Next are the commands used for installation, remember to install the appropiate tools for your filesystem, like "_jfsutils_" for __JFS__.  
* Make root filesystem according to your personal preference.  
`mkfs.<ROOT_FILESYSTEM> /dev/sda2`  
* Make boot filesystem according to supported bootloader or just "_mkfs.vfat_" if on UEFI.  
`mkfs.<BOOTLOADER_FILESYSTEM> /dev/sda1`  

## CREATING (AND MOUNTING) MAIN DIRECTORIES
The two most important are the root directory ("_/_") and the boot directory ("_/boot_"), both of which need at the end of this step to be mounted. However, if you are an experienced user you may have created other partitions for other directories like "_/home_" or "_/var_", those need to be mounted too by the end of this step.
* Make a directory for the new root directory.  
`mkdir /mnt`  
* Mount the new root directory.  
`mount /dev/sda2 /mnt`  
* If on BIOS make boot directory and mount.  
`mkdir /mnt/boot`  
`mount /dev/sda1 /mnt/boot`
* If on UEFI make boot directory and mount.  
```mkdir -p /mnt/boot/efi
mount /dev/sda1 /mnt/boot/efi
```
* Create other directories under the new root directory.  
`mkdir -p /mnt/{dev,sys,proc,tmp,usr/src,var}`  

Don't forget to create and mount the extra directories in the case you had created them.

## SETUP
* On __CRUX__ run "_setup_", and if on UEFI during the setup select grub2-efi (if using GRUB 2), efibootmgr, and elfutils from opt (only select core, and say yes when you're asked if you want to select individual packages). And if you are not using LILO de-select it from core.  
`setup`  
* On __Source Mage GNU/Linux__ download and uncompress the tarball inside the new root directory.  
```cd /mnt
wget -c "http://download.sourcemage.org/image/official/smgl-stable-<VERSION>-basesystem-x86_64.tar.xz"
tar xJvf smgl-stable-<VERSION>-basesystem-x86_64.tar.xz
```

### CHROOT
* On __CRUX__ you can issue the next command to mount everything else and chroot automatically.  
`setup-chroot`  
* On __Source Mage GNU/Linux__ mount everything else manually.  
```mount --bind /dev /mnt/dev
mount --bind /tmp /mnt/tmp
mount --bind /sys /mnt/sys
mount -t proc none /mnt/proc
mount -t devpts none /mnt/dev/pts
```
* On __Source Mage GNU/Linux__ chroot manually specifying Bash in case live media has another shell.  
`chroot /mnt /bin/bash`  
* Now inside chroot change root password (TEST IF YOUR KEYBOARD HAS ALL THE CORRECT MAPPINGS before you change the password).  
`passwd root`  

### CHANGE NETWORK INTERFACES
* On __CRUX__ modify "_/etc/rc.d/net_" with the rules you want (IP, gateway, domain, etc).  
* On __Source Mage GNU/Linux__ add preferred interfaces to "_/etc/network/interfaces_" for example.  
```auto eth0
allow-hotplug eth0
iface eth0 inet dhcp
```
* On the "_/etc/resolv.conf.head_" file set your preferred DNS provider (this example is from [OpenNIC](https://servers.opennicproject.org/)).  
`nameserver 185.121.177.177`  
* Or copy "_/etc/resolv.conf_" to "_/mnt/etc/resolv.conf_" __BEFORE__ chrooting.  

### EDIT FSTAB
* Change the "_/etc/fstab_" file with appropriate filesystems.  
```/dev/sda1    /boot    <BOOTLOADER_FILESYSTEM>    defaults    0 2  
/dev/sda2    /    <ROOT_FILESYSTEM>    noatime    0 1
```
* On __CRUX__ uncomment the lines referring to "_devpts_", "_tmp_", and "_shm_" as some programs require it (Firefox), also "_USB_" and or "_cdrom_" if using those.  
* If on UEFI replace "_/boot_" with "_/boot/efi_".  

### SET THE ENVIRONMENT
* On __CRUX__ change the font, keyboard, timezone, hostname and services on the "_/etc/rc.conf_" file.  
`ls /usr/share/kbd/keymaps/`  
* On __Source Mage GNU/Linux__ change keymaps on the "_/etc/sysconfig/keymap_" file.  
`ls /usr/share/keymaps/i386/qwerty`  
* On __CRUX__ generate locales (change interface language).  
`localedef -i <LOCALE> -f ISO-<CODE> <LOCALE>`  
* On __Source Mage GNU/Linux__ generate locales (change interface language).  
`cast -r locale`  

## KERNEL
Next are simple examples of compiling the kernel, for a more in depth view see: https://github.com/mayfrost/guides/blob/master/KERNEL.md  
* On __CRUX__.  
```cd /usr/src/linux-<VERSION>
make all modules_install install
```

* On __Source Mage GNU/Linux__ (__OPTIONAL__).  
`cast -r linux`

## BOOTLOADER
Next is a simple example of setting the bootloader, for a more in depth view see: https://github.com/mayfrost/guides/blob/master/BOOTLOADER.md  
__NOTE__: If you are on __Source Mage GNU/Linux__ and need UEFI refer to the bootloader section and use grub2 as there is no elilo package:

### LILO
* On __Source Mage GNU/Linux__ do "_cast \<BOOTLOADER>_" to install the bootloader.  
* If on UEFI use __elilo__ and change names to "_/etc/elilo.conf_" instead of "_/etc/lilo.conf_" and "_elilo_" instead of "_lilo_" in commands.  
`nano /etc/lilo.conf`
* Inserting "_password=\<PASSWORD>_" inside an OS stanza will protect with a password that OS, but inserting "_password=\<PASSWORD>_" just before the stanzas and outside any of them will protect with a password the bootloader itself (notice the space inside stanzas).  
```boot = /dev/sda
image = /boot/vmlinuz
     Label = <DISTRO_NAME>
     root = /dev/sda<PARTITION_NUMBER_OF_ROOT>
other = /dev/sda<PARTITION_NUMBER_OF_FREEDOS>
     table = /dev/sda
     Label = FreeDOS
other = /dev/sda<PARTITION_NUMBER_OF_WINDOWS>
     table = /dev/sda
     Label = Windows7
```
* Set boot entry.  
```lilo -A /dev/sda 1
lilo
```
* Prevent anyone but root of reading the config file (in case you used a password).  
`chmod 600 /etc/lilo.conf`

## THE END
* Exit the chroot.  
`exit`
* Shutdown the machine.  
`shutdown -h now`  

And done. For more information on both distros and what to do next see: https://github.com/mayfrost/guides/blob/master/DISTROS.md  
Also check the list of software alternative to bloatware and support minimalism https://github.com/mayfrost/guides/blob/master/ALTERNATIVES.md
