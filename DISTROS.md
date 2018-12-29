# DISTROS

* __CRUX__ (https://crux.nu): With a ports based system for installing software, BSD style init scripts favoring native configurations over configuration abstraction layers, follows true KISS principles (Keep It Simple) applied to the system and the development process. Simplicity over automation makes it easy to extend the system by yourself.  
* __Source Mage GNU/Linux__ (http://sourcemage.org): Without 3rd party patches, sensible defaults or masked packages, is free from obfuscated and pre-configured code, using clean dependencies as they came from upstream developers which provides immediate updates, and can also use flags and heal broken installs. With the package manager made in bash doesn't need obfuscated python libraries. Fully committed to GPL, uses only free software (as in freedom) in their main package, with even the documentation licensed as FDL.  
* __Harvey OS__ (https://harvey-os.org/):  Everything is a file, the hardware, environment variables, and settings are presented as "files". And with the Plan 9 file-sharing protocol the name space can mount from one computer to the other and act as a distributed service. Distributed under the GPL, is a member of the [Software Freedom Conservancy](https://sfconservancy.org/).  
* __FreeDOS__ (https://www.freedos.org): DOS-compatible, can play classic games and run legacy business software.

1. [CONFIGURATION ON CRUX](#configuration-on-crux)  
2.1. [ENABLE CONTRIB REPO](#enable-contrib-repo)  
2.2. [ADD EXTERNAL REPOS](#add-external-repos)  
2.3. [FINALIZING REPO CONFIGURATION](#finalizing-repo-configuration)  
3. [CRUX COMMANDS](#crux-commands)  
3.1. [AUTOMATED INSTALLATION OF PORTS](#automated-installation-of-ports)  
3.2. [MANUAL DOWNLOAD AND INSTALLATION](#manual-download-and-installation)  
4. [SOURCE MAGE GNU/LINUX COMMANDS](#source-mage-gnu/linu-commands)  

## CONFIGURATION ON CRUX
### ENABLE CONTRIB REPO
* Enable contrib for ports  
```  
cd /etc/ports
mv contrib.rsync.inactive contrib.rsync  
````
* Enable contrib for prt-get  
`nano /etc/prt-get.conf`
* Uncomment line "_prtdir /usr/ports/contrib_"

### ADD EXTERNAL REPOS
* Download httpup/rsync file and pub file from https://crux.nu/portdb/index.php?a=index  
```  
cd /etc/ports/
wget -c <URL>  
```
* Add repo location to "_/etc/prt-get.conf_" (order sets precedence)  
`nano /etc/prt-get.conf`
* Add line "_prtdir /usr/ports/\<REPO>_"

### FINALIZING REPO CONFIGURATION
* Enable pre-/post-install scripts in "_/etc/prt-get.conf_" (usually safe to run repeatedly, usually used to rebuild caches and add system users when installing certain software)  
`nano /etc/prt-get.conf`
* Uncomment line "_runscripts yes_"  

* Ignore footprint mismatches due to new files (usually not a bad thing)  
`nano /etc/pkgmk.conf`
* Set line "_PKGMK_IGNORE_NEW="yes"_"  
* Populate ports tree (is empty by default)  
`ports -u`

## CRUX COMMANDS
### AUTOMATED INSTALLATION OF PORTS
* Populate ports tree (is empty by default)  
`ports -u`
* Populate specific repo  
`ports -u <REPO>`
* Automatically download and build a package with its required dependencies ignoring signature mismatch  
`prt-get -is depinst <PORT>`
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
```  
cast smgl-setup
man smgl-setup  
```
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
