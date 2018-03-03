# DISTROS

* __CRUX__: A ports based, BSD style init scripts, distro following true KISS principles (Keep It Simple).  
* __Source Mage GNU/Linux__: Without 3rd party patches, sensible defaults or masked packages, free from obfuscated and pre-configured code, use clean dependencies as they came from upstream developers and can also use flags.  

7. [CONFIGURATION ON CRUX](#configuration-on-crux)  
7.1. [ENABLE CONTRIB REPO](#enable-contrib-repo)  
7.2. [ADD EXTERNAL REPOS](#add-external-repos)  
7.3. [INSTALL XORG](#install-xorg)  
8. [CRUX COMMANDS](#crux-commands)  
8.1. [AUTOMATED INSTALLATION OF PORTS](#automated-installation-of-ports)  
8.2. [MANUAL DOWNLOAD AND INSTALLATION](#manual-download-and-installation)  
9. [SOURCE MAGE GNU/LINUX COMMANDS](#source-mage-gnu/linu-commands)  

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
