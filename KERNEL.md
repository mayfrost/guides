# KERNEL

Compiling a kernel has the advantage to make it as minimal and featureful as you want, you can test kernel patches and tweaks and optimize your system.
* You need the kernel source, build tools, the kernel configuration file (__optional__), and __root__ or __sudo__ privileges for the final stages of the process.
* Back up all of your files.
* Have a distro in a Live CD or USB at hand just in case.
* Have a cup of tea or coffee while you wait to compile.

1. [PREPARATIONS](#preparations)  
2. [GETTING THE KERNEL SOURCE](#getting-the-kernel-source)  
2.1. [OPTIONAL: Symlink](#optional-symlink)  
2.2. [DOWNLOAD THE KERNEL SOURCE](#download-the-kernel-source)  
3. [GENERATING A CONFIGURATION FILE](#generation-a-configuration-file)  
4. [CHANGING THE CONFIGURATION (OPTIONAL)](#changing-the-configuration-optional)  
5. [COMPILATION](#compilation)  
5.1. [OPTION A: One command](#option-a-one-command)  
5.2. [OPTION B: One by one](#option-b-one-by-one)  
5.3. [BUILD MODULES](#build-modules)  
6. [INITRD](#initrd)  
7. [MODULES](#modules)  
7.1. [COMPILE A SINGLE MODULE](#compile-a-single-module)  
7.2. [DKMS](#dkms)  
8. [KERNEL PATCH](#kernel-patch)  
8.1. [OPTION 1: Git](#option-1-git)  
8.2. [OPTION 2: Patch command](#option-2-patch-command)  
8.3. [OPTION 3: Patch with zcat](#option-2-patch-with-zcat)  

## PREPARATIONS
* To see which version the new kernel source is.  
`head /usr/src/linux/Makefile`  
* To see which version the current kernel is.  
`uname -r`  
* List hardware and kernel modules in use (take note to know what kernel modules are appropriate).  
`lspci -k`  
`lspci -v`  
`cat /proc/cpuinfo`  
`cat /proc/meminfo`  
`lsmod`  

## GETTING THE KERNEL SOURCE

### OPTIONAL: Symlink
Is standard to download Linux sources under __/usr/src/__, then link the downloaded kernel tree to __/usr/src/linux-<VERSION_NUMBER>__ and work there, but is not a requirement.  
* Change to __/usr/src/__.  
`cd /usr/src/`  
* Symlink.
`ln -s linux-<VERSION_NUMBER> linux`  

### DOWNLOAD THE KERNEL SOURCE
Get latest kernel from kernel.org
* Get tarball.  
`wget https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable-rc.git/snapshot/linux-stable-rc-<VERSION>.tar.gz`  
* Uncompress.  
`tar -xvzf linux-<VERSION_NUMBER>.tar.xz`
* Enter directory.  
`cd linux-<VERSION_NUMBER>/`  

* Clean the directory (wont touch the config file just remove all compiled files from the kernel tree).  
`make clean`  
* Remove compiled files from the kernel tree AND the configuration file if there are any (backup your configuration file before this if you have one in the current directory).  
`make mrproper`  


## GENERATING A CONFIGURATION FILE
This process makes a "__.config__" file in the kernel source directory, this file determines which drivers are built and other support. There are three options here, you can turn on only the minimal set of options you need.

* __OPTION 1__: Use the config file of another kernel or the current system.  
`cp -v /boot/config-$(uname -r) .config`  
* Or in some distros you can take it from the running kernel.  
`zcat /proc/config.gz > .config`  

* __OPTION 2__: Make a default config file (may or may not not have the options you are currently using).  
`make defconfig`  

* __OPTION 3__: Generate a config file disabling all options not loaded by the currently running kernel and will make questions on what kernel options to support when it finds new kernel options. Could have problems with peripherals not in use at that time unless you plug all devices like __USBs__. Attach devices you use or insert modules manually with the insmod command before using this option. Available from kernel version 2.6.32 and up.  
`make localmodconfig`  

* __OPTION 4__: Create a minimal kernel config file which necessarily needs to manually enable options afterwards to have a working system. Available from kernel version 3.17-rc1 and up.  
`make tinyconfig`  


## CHANGING THE CONFIGURATION (OPTIONAL)
* Depending on your tastes this part can take minutes, hours, or days to enable proper options.
* The Y (or "__*__" in __menuconfig__) flag in kernel configuration compiles options as part of __vmlinuz__.
* The M flag in kernel configuration compiles options as separate modules.
* The N (or a blank space in __menuconfig__) flag in kernel configuration will not build selected option.

* __OPTION 1__: Start a menu and browse options. Requires curses library but likely is already on your computer. Press "__H__" or "__?__" to see help. You can use the space bar to cycle between the available choices or press the appropriate key mentioned above. Pressing "__/__" to search for keywords.  
`make menuconfig`  

* __OPTION 2__: Will make questions on what kernel options to support when it finds new kernel options not marked on an existing config file (takes time and and if you are using a striped down config file it requires you knowledge).  
`make oldconfig`  

* __OPTION 3__: Will fill questions with default answers on what kernel options to support beyond your provided config file.  
`make olddefconfig`  


## COMPILATION
Can take minutes to hours.
__NOTE__: The __-j\<X>__ flag, where __\<X>__ is the number of cores +1, __IS OPTIONAL__ and only goes if you have a processor with multiple cores. If you install __ccache__ (__THIS IS OPTIONAL__) you can speed up subsequent compilations by including __CC="ccache gcc"__ after the __-j\<X>__ flag.  
`make -j<X> <OTHER_FLAGS>`  
And with ccache.  
`make -j<X> CC="ccache gcc" <OTHER_FLAGS>`  

For compilation you have two options, __OPTION A__ is the easiest and is a single command. __OPTION B__ is here for didactic purposes.

### OPTION A: One command
Compile and move everything to its place. The "__all__" flag makes modules AND the __bzImage__ at the same time (replaces "__bzImage__" and "__modules__" flags).  
`make -j<X> all modules_install install`  

### OPTION B: One by one
* If your configuration does not contain answers for all of the options, especially if they are new and not currently included in your running kernel, you will need to answer the prompts for these options.  
`make -j<X> bzImage`  

* __OPTION B1__: Copy the new kernel to __/boot__.  
`cp arch/<YOUR_ARCHITECTURE>/boot/bzImage /boot/vmlinuz`  
* Not required for booting but some processes need it.  
`cp System.map /boot`  

* __OPTION B2__: Automatically move kernel to __/boot__ (and in certain distros, symlink the new kernel to __/boot/vmlinuz__ and update the bootloader configuration).  
`make install`  


### BUILD MODULES
* Compile individual files for each question you answered M during kernel config. The object code is linked against your freshly built kernel. (For questions answered __Y__, these are already part of __vmlinuz__, and for questions answered __N__ they are skipped). Modules end with __.ko__.  
`make -j<X> modules`  
* Copy generated kernel modules to __/lib/modules/<KERNEL_VERSION>/__.  
`make modules_install`  

__NOTE__: The __vmlinuz__ can be any name but that exact name has to be added to the configuration file of your bootloader of choice. Usually a version number is appended to the new kernel image. This has the advantage to avoid replacing a current kernel and having a fallback as backup to boot. You can set to boot from any image in the bootloader once you configure them in the bootloader.

## INITRD
The __initrd__ is used only while booting, unless you compile the kernel with the filesystem it resides on (__initfs__). There are three options.
* __OPTION 1__: Compile the kernel with support for the filesystem used in the __/boot__ partition (__initfs__).
* __OPTION 2__: Use __mkinitrd__.  
`mkinitrd -o /boot/initrd.img`  
* __OPTION 3__: Use __initramfs__.  
`update-initramfs -u`  


## MODULES
### COMPILE A SINGLE MODULE
* Only compile a module.  
`cd linux-<VERSION_NUMBER>/`  
* Create files required for compiling external modules.  
`make modules_prepare`  
* Compile modules.  
`make M=<DIRECTORY_WHERE_MODULE_IS_LOCATED>`  
* Move module to __<VERSION_NUMBER>__.  
`cp <DIRECTORY_WHERE_MODULE_IS_LOCATED>/<NAME_OF_MODULE>.ko /lib/modules/$(uname -r)/`  
* Or  
`cp <DIRECTORY_WHERE_MODULE_IS_LOCATED>/<NAME_OF_MODULE>.ko /lib/modules/`  
* Update the modules.  
`depmod -a`  


### DKMS
To update modules automatically when changing a kernel use __DKMS__. Requires the __dkms__ package and the proper module source code.
* Create a directory.  
`mkdir /usr/src/<MODULE>-<MODULE_VERSION>/`  
* Copy the source code of the module.  
`cp -a * <DIRECTORY_WHERE_MODULE_IS_LOCATED>`  
* Create a __dkms.conf__ file in the directory.  
`vi /usr/src/<MODULE>-<MODULE_VERSION>/dkms.conf`  
* Edit __dkms.conf__.  
`PACKAGE_NAME="<MODULE>"`  
`PACKAGE_VERSION="<MODULE_VERSION>"`  
`BUILT_MODULE_NAME[0]="<MODULE>"`  
`DEST_MODULE_LOCATION[0]="/kernel/<SECTION>/<MODULE>/"`  
`AUTOINSTALL="yes"`  
* Add __<MODULE>__ and __<MODULE_VERSION>__ to __DKMS__.  
`dkms add -m <MODULE> -v <MODULE_VERSION>`  
* Compile the module with __DKMS__.  
`dkms build -m <MODULE> -v <MODULE_VERSION>`  
* Install the module with __DKMS__.  
`dkms install -m <MODULE> -v <MODULE_VERSION>`  


## KERNEL PATCH
You can find patch files on the Linux Kernel Mailing List https://lkml.org/.

* Go to kernel source tree.  
`cd /usr/src/linux-<VERSION_NUMBER>`  
* Download the patch file there.
* Following options assume is __gzipped__.

You have three options to patch the kernel.

### OPTION 1: Git
Git can be used to fallback from the patch and revert to the upatched source.
* Uncompress patch file.  
`gunzip <PATCH_FILE>.gz`  
* Apply patch.  
`git am <PATCH_FILE>`  
* To revert a single patch.  
`git apply -R <PATCH_FILE>`  
* To revert several patches first see the __git log__.  
`git log --pretty=oneline --abbrev-commit`  
* Select the proper number from the first column.  
`git reset --hard <FIRST_COLUMN_NUMBER>`  

### OPTION 2: Patch command
* Uncompress patch file.  
`gunzip <PATCH_FILE>.gz`  
* The __-p__ flag specifies a number of leading directories to remove, location is at the top of the patch file filename and is relative to the current directory.  
`patch -p1 < <PATCH_FILE>`  

### OPTION 3: Patch with zcat
To use the uncrompressed file directly.  
`zcat <PATCH_FILE>.gz | patch -p1`  

Compile kernel with the patch now included.
