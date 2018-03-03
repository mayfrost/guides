# KERNEL

Compiling a kernel has the advantage to make it as minimal and featureful as you want, you can test kernel patches and tweaks and optimize your system.
* You need the kernel source, build tools, the kernel configuration file (optional), and root or sudo privileges for the final stages of the process.
* Back up all of your files.
* Have a distro in a Live CD or USB at hand just in case.
* Give yourself a cup of tea or coffee while you wait to compile.

## PREPARATIONS
* To see which version the new kernel source.  
`head /usr/src/linux/Makefile`  
* To see which version the current kernel.  
`uname -r`  

## GETTING THE KERNEL SOURCE

* OPTIONAL: Is standard to download Linux sources under /usr/src/, link the downloaded kernel tree to /usr/src/linux-<VERSION_NUMBER> and work there, but is not a requirement.  
`cd /usr/src/`  
`ln -s linux-<VERSION_NUMBER> linux`  

### Download the latest kernel from kernel.org
* Get tarball.  
`wget https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable-rc.git/snapshot/linux-stable-rc-<VERSION>.tar.gz`  
* Uncompress.  
`tar -xvzf linux-<VERSION_NUMBER>.tar.xz`
* Enter directory.  
`cd linux-<VERSION_NUMBER>/`  

* Remove compiled files from the kernel tree AND the configuration file (backup your configuration file before this if you have one in the current directory).  
`make mrproper`  


## GENERATING A CONFIGURATION FILE
This process makes a .config file in the kernel source directory determines which drivers are built and other support. And turn on only the minimal set of options you need.

* OPTION 1: Use the config file of another kernel or the current system.  
`cp -v /boot/config-$(uname -r) .config`  
* Or in some distros you can take it from the running kernel  
`zcat /proc/config.gz > .config`  

* OPTION 2: Make a default config file (may or may not not have the options you are currently using).  
`make defconfig`  

* OPTION 3: Generate a config file disabling all options not loaded by the currently running kernel and will make questions on what kernel options to support when it finds new kernel options. Could have problems with peripherals not in use at that time unless you plug all devices like USBs. Available from kernel version 2.6.32 and up. Attach devices you use or insert modules manually with the insmod command before using this option.  
`make localmodconfig`  

* OPTION 4: Create a minimal kernel config file which necessarily needs to manually enable options afterwards to have a working system. Available from kernel version 3.17-rc1 and up.  
`make tinyconfig`  


## CHANGING THE CONFIGURATION (OPTIONAL)
* Depending on your tastes this part can take minutes, hours, or days to enable proper options.
* The Y (or "*" in menuconfig) flag in kernel configuration compiles options as part of vmlinuz.
* The M flag in kernel configuration compiles options as separate modules.
* The N (or a blank space in menuconfig) flag in kernel configuration will not build selected option.


* List hardware and kernel modules in use.  
`lspci -k`  
`lspci -v`  
`cat /proc/cpuinfo`  
`cat /proc/meminfo`  
`lsmod`  

* OPTION 1: Start a menu and browse options. Requires curses library but likely is already on your computer. Press "H" or "?" to see help. You can use the space bar to cycle between the available choices or press the appropriate key mentioned above. Pressing "/" to search for keywords.  
`make menuconfig`  

* OPTION 2: Will make questions on what kernel options to support when it finds new kernel options not marked on an existing config file (takes time and and if you are using a striped down config file it requires you knowledge).  
`make oldconfig`  

* OPTION 3: Will fill questions with default answers on what kernel options to support beyond your provided config file.  
`make olddefconfig`  


## COMPILATION
Can take minutes to hours.

* Clean directory (wont touch the config file just remove all compiled files from the kernel tree).  
`make clean`  

_NOTE_: The "-j<X>" flag, where <X> is the number of cores +1, is OPTIONAL and only goes if you have a processor with multiple cores. If you install ccache (OPTIONAL) you can speed up subsequent compilations by including CC="ccache gcc" after the "-j<X>" flag.  
`make -j<X> <OTHER_FLAGS>`  

* OPTION A: Compile and move everything to its place. The "all" flag makes modules AND the bzImage at the same time (replaces "bzImage" and "modules" flags).  
`make -j<X> all modules_install install`  

* OPTION B: One by one

* If your configuration does not contain answers for all of the options, especially if they are new and not currently included in your running kernel, you will need to answer the prompts for these options.  
`make -j<X> bzImage`  

## MOVE KERNEL IMAGE
* OPTION B1: Copy the new kernel to /boot, create the initrd file and change the GRUB menu.  
`cp arch/<YOUR_ARCHITECTURE>/boot/bzImage /boot/vmlinuz`  
* Not required for booting but some processes need it.  
`cp System.map /boot`  

* OPTION B2: Automatically move kernel to /boot (and in certain distros, symlink the new kernel to /boot/vmlinuz and update the bootloader configuration).  
`make install`  


## BUILD MODULES
* Compile individual files for each question you answered M during kernel config. The object code is linked against your freshly built kernel. (For questions answered Y, these are already part of vmlinuz, and for questions answered N they are skipped). Modules end with .ko.  
`make -j<X> modules`  

## MOVE MODULES
* Copy generated kernel modules to /lib/modules/<KERNEL_VERSION>/.  
`make modules_install`  

_NOTE_: The vmlinuz can be any name but that exact name has to be added to the configuration file of your bootloader of choice. Usually a version number is appended to the new kernel image. This has the advantage to avoid replacing a current kernel and having a fallback as backup to boot. You can set to boot from any image in the bootloader once you configure them in the bootloader.

## INITRD
* The initrd is used only while booting, unless you compile the kernel with the filesystem it resides on (initfs)
* OPTION 1: Compile the kernel with an initfs.
* OPTION 2: Use mkinitrd.  
`mkinitrd -o /boot/initrd.img`  
* OPTION 3: Use initramfs.  
`update-initramfs -u`  








## COMPILE A SINGLE MODULE

* Only compile a module.  
`cd linux-<VERSION_NUMBER>/`  
* Create files required for compiling external modules.  
`make modules_prepare`  
* Compile modules.  
`make M=<DIRECTORY_WHERE_MODULE_IS_LOCATED>`  
* Move module to <VERSION_NUMBER>.  
`cp <DIRECTORY_WHERE_MODULE_IS_LOCATED>/<NAME_OF_MODULE>.ko /lib/modules/$(uname -r)/`  
* Or  
`cp <DIRECTORY_WHERE_MODULE_IS_LOCATED>/<NAME_OF_MODULE>.ko /lib/modules/`  
* Update the modules.  
`depmod -a`  


## DKMS
To update modules automatically when changing a kernel use DKMS. Requires the dkms package and the module source code.
* Create a directory.  
`mkdir /usr/src/<MODULE>-<MODULE_VERSION>/`  
* Copy the source code of the module.  
`cp -a * <DIRECTORY_WHERE_MODULE_IS_LOCATED>`  
* Create a dkms.conf file in the directory.  
`vi /usr/src/<MODULE>-<MODULE_VERSION>/dkms.conf`  
* Edit.  
`PACKAGE_NAME="<MODULE>"`  
`PACKAGE_VERSION="<MODULE_VERSION>"`  
`BUILT_MODULE_NAME[0]="<MODULE>"`  
`DEST_MODULE_LOCATION[0]="/kernel/<SECTION>/<MODULE>/"`  
`AUTOINSTALL="yes"`  
* Add <MODULE> and <MODULE_VERSION> to DKMS.  
`dkms add -m <MODULE> -v <MODULE_VERSION>`  
* Compile the module with DKMS.  
`dkms build -m <MODULE> -v <MODULE_VERSION>`  
* Install the module with DKMS.  
`dkms install -m <MODULE> -v <MODULE_VERSION>`  



## KERNEL PATCH

You can find patch files on the Linux Kernel Mailing List https://lkml.org/.

* Go to kernel source tree.  
`cd /usr/src/linux-<VERSION_NUMBER>`  
* Download the patch file there.
* Following options assume is gzipped.

* OPTION 1: Git can be used to fallback from the patch and revert to the upatched source.
* Uncompress patch file.  
`gunzip <PATCH_FILE>.gz`  
* Apply patch.  
`git am <PATCH_FILE>`  
* To revert a single patch.  
`git apply -R <PATCH_FILE>`  
* To revert several patches first see the git log.  
`git log --pretty=oneline --abbrev-commit`  
* Select the proper number from the first column.  
`git reset --hard <FIRST_COLUMN_NUMBER>`  

* OPTION 2: Patch command
* Uncompress patch file.  
`gunzip <PATCH_FILE>.gz`  
* The -p flag specifies a number of leading directories to remove, location is at the top of the patch file filename and is relative to the current directory.  
`patch -p1 < <PATCH_FILE>`  

* OPTION 3: Use patch with zcat to use the uncrompressed file directly.  
`zcat <PATCH_FILE>.gz | patch -p1`  


* Compile kernel with the patch now included.
