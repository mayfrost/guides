# COMMUNICATION
Here lies several ways to communicate through different networks.

1. [BROWSER](#browser)  
1.1. [GNU ICECAT](#gnu-icecat)  
1.2. [ADDONS](#addons)  
1.3. [ABOUT CONFIG](#about-config)  
2. [E-MAIL](#e\-mail)  
2.1. [E-MAIL STORAGE FORMATS](#gnu-icecat)  
2.2. [MUTTRC](#addons)  
3. [USENET](#usenet)  
4. [I2P](#i2p)  
4.1. [INSTALLATION](#installation)  
4.2. [I2PD](#i2pd)  
4.3. [REMOTE ACCESS](#remote-access)  
4.4. [BASIC COMMANDS](#basic-commands)  
4.5. [BROWSING I2P EEPSITES](#browsing-i2p-eepsites)  
4.6. [YOUR OWN EEPSITE](#your-own-eepsite)  
4.7. [IRC](#irc)  
4.8. [TORRENTS](#torrents)  
4.8.1 [DOWNLOADING](#downloading)  
4.8.2 [CREATING](#creating)  
4.8.3 [CONFIGURATION](#configuration)  


## BROWSER

### GNU ICECAT
* Download from http://ftpmirror.gnu.org/gnuzilla/
* Unpack the tarball
* As ROOT, copy and rename the folder as /opt/icecat
* ln -s /opt/icecat/icecat /usr/bin/icecat

### ADDONS
These addons worked excellent to cover any fingerprinting, until Mozilla decided to break things since Firefox 52.
* (Cross-)Site Request, Anti-XSS, Trackers, Referer, Cookies: [uMatrix](https://addons.mozilla.org/en-US/firefox/addon/umatrix/)
* Security Settings: [Privacy Settings](https://addons.mozilla.org/en-US/firefox/addon/privacy-settings/)
* User-Agent: [Random Agent Spoofer](https://github.com/dillbyrne/random-agent-spoofer), [User-Agent JS Fixer](http://legacycollector.org/firefox-addons/378075/index.html)
* Plugin Enumeration: [Disable plugin enum](https://github.com/dillbyrne/random-agent-spoofer/issues/283) (see Mechazawa's script, and install with greasemonkey)
* Content Delivery Blocker: [Decentraleyes](https://addons.mozilla.org/en-US/firefox/addon/decentraleyes/)
* URI Leak: [No Resource URI Leak](https://notabug.org/desktopd/no-resource-uri-leak)
* Canvas-Fingerprinting: [Canvas Defender](https://addons.mozilla.org/en-US/firefox/addon/no-canvas-fingerprinting/)
* SSL (strict HTTPS): [HTTPS by default](https://addons.mozilla.org/en-US/firefox/addon/https-by-default/)
* URL Deobfuscator: [Pure URL](https://addons.mozilla.org/en-US/firefox/addon/pure-url/)
* Google Redirection: [Google search link fix](https://addons.mozilla.org/en-US/firefox/addon/google-search-link-fix/)

### ABOUT CONFIG
These tips prevent overflow your root directory or getting constantly write and delete to try and kill your drive.
* Go to _about\:config_
* Put a 0 to everything that can write to the disk.
* Limit ram memory and also turn off syncing ect.
* Make it read only.
* If you need to save things have a seperate chroot with a seperate physical drive and make that your downloads folder.

## E-MAIL

TODO:
* Set cock.li
* Configure mutt
* Create account.
* Set mutiple accounts
* Send mail
* Send attachment
* To cancel an action in mutt hit CTRL+g
* Use notmuch
* set i2p-bote

### E-MAIL STORAGE FORMATS
* MAILDIR = several files
* MBOX = one file for everything

### MUTTRC
Example config with cock.li and gmail. Not quite complete but can work if tweaked.
```
#---------------------------------------
# ~/.mutt/muttrc settings mutt 1.5.20
#---------------------------------------
#
#---------------------------------------
# One-Time Previous Steps
#---------------------------------------
# Generate keys with proper user
# $ gpg --gen-key
#
# Make proper directory with file:
# $ mkdir ~/.mutt && touch ~/.mutt/.passwd
#
# Put the following inside ~/.mutt/.passwd:
# set cock_pass="password"
# set gmail_pass="password"
#
# Encrypt with proper user:
# $ gpg -r USER1 -e ~/.mutt/.passwd
# $ shred ~/.mutt/.passwd
# $ rm -f ~/.mutt/.passwd
#
#---------------------------------------
# Process the password file first (the "|" pipes to Mutt)
#---------------------------------------
#source "gpg -d ~/.mutt/.passwd.gpg |"
#
#---------------------------------------
# Account Hooks
#---------------------------------------
account-hook . 'unset imap_user imap_pass' # unset first!
account-hook 'imaps://mail.cock.li:993/' "\
             set imap_user=USER1@cock.li imap_pass=`cat ~/.mutt/.cock ` " # imap_pass=$my_cock_pass "
#account-hook 'imaps://USER2@imap.gmail.com/' "\
#              set imap_user=USER2 imap_pass=$my_gmail_pass "
#
#----------------------------------------
# Folders, mailboxes and folder hooks
#----------------------------------------
#
# Setup for USER1:
#----------------------------------------
set folder = imaps://mail.cock.li:993/
mailboxes =Inbox =Sent =Junk =Trash
folder-hook 'imaps://mail.cock.li:993' " \
        set     folder=imaps://mail.cock.li:993/ \
                record=+Sent \
                smtp_url=smtps://$imap_user@mail.cock.li:465 \
                signature=~/.mutt/USER1.sig \
                from='USER1 <USER1@cock.li> ' \
                realname='USER1' "
#
#----------------------------------------
# Setup for USER2:
#----------------------------------------
#set folder="imaps://USER2@imap.gmail.com/"
#mailboxes =INBOX =[Gmail]/Drafts =[Gmail]/'Sent Mail' =[Gmail]/Spam
#folder-hook 'imaps://USER2@imap.gmail.com' " \
#        set     folder=imaps://USER2@imap.gmail.com/ \
#                postponed=+[Gmail]/Drafts \
#                record=+[Gmail]/'Sent Mail' \
#                smtp_url=smtps://USER2@smtp.gmail.com \
#                smtp_pass=$my_gmail_pass \
#                signature=~/.mutt/USER2.sig \
#                from='USER2 <USER2@gmail.com> ' \
#                realname='USER2' "
#
#----------------------------------------
# Macros to make life easier
#----------------------------------------
macro index <esc>1 "y1<return><return>" # ESC+1 takes to first INBOX
#macro index <esc>2 "y5<return><return>" # ESC+2 takes to the second
#
#---------------------------------------
# Mail-check preferences
#---------------------------------------
set timeout=60	#Check for mail every minute
set mail_check=5
#
#---------------------------------------
# Set preferred editor
#---------------------------------------
set editor='vim + -c "set textwidth=72" -c "set wrap" -c "set nocp" -c "?^$"'
# EOF
```  

## USENET
The software used is __slrn__ ( with __slrnpull__ and + __slrnface__).

* 1. Create slrn.rc:
```
set username "desired_username"
set hostname "desired_hostname.invalid"
set replyto "some_name <email@example.com>"
charset display utf8
charset outgoing utf8
setkey group "set_prefix_argument(4); () = select_group();" " "
```  

* 2. Set $NNTPSERVER to usenet provider (set in config file):  
`NNTPSERVER='server_name' && export NNTPSERVER`  

* 3. Set $EDITOR to preferred text editor (set in slrn.rc file):  
`set editor_command "vim '+set tw=72' +%d '%s'"`  

* 4. Create .jnewsrc  
`touch .jnewsrc`  

* 5. Create configuration
`slrn --create`  

* 6. Download a list of newsgroups  
`slrn -d`  

## I2P
__I2P__ is a darknet like __Tor__ but with more services like e-mail, IRC, torrents, and others. Once you install it you can configure it by its web interface at http://localhost:7657/home.


### INSTALLATION
* Make directory that will contain I2P  
`mkdir ~/.i2p`  

* Go to directory  
`cd ~/.i2p`  

* Download (replace <VERSION> with the newest version)  
`wget -c https://download.i2p2.de/releases/<VERSION>/i2pinstall_<VERSION>.jar`  

* Run the installer (and select options like the current path)  
`java -jar i2pinstall_<VERSION>.jar -console`  

To uninstall simply delete the directory.

### I2PD
__I2PD__ is a version of __I2P__ based on C++ instead of Java. Currently with limited support (no torrents). Therefore is __OPTIONAL__ and its funtion is separated from the rest of the guide.

* Dependencies:  
```
libboost
cmake
make
```  

* Download.  
`git clone https://github.com/PurpleI2P/i2pd.git`  
* Go to directory.  
`cd i2pd/build`  
* Build.  
```
cmake
make
```  
* Install  
```
mkdir $HOME/.i2pd
cp i2pd $HOME/.i2pd
cp -R contrib/certificates $HOME/.i2pd
cp contrib/i2pd.conf $HOME/.i2pd
cd $HOME/.i2pd
ulimit -n 4096  # optional file limit
```  
* To run:  
```
cd $HOME/.i2pd
./i2pd --datadir .
```  
* To stop:  
`kill -INT $( cat /var/run/i2pd/i2pd.pid )`  


### REMOTE ACCESS
To access your I2P router from another computer.

* On ~/.i2p/clients.config replace  
`clientApp.0.args=7657 ::1,127.0.0.1 ./webapps/`  
* with  
`clientApp.0.args=7657 ::1,127.0.0.1,<REMOTE_IP> ./webapps/`  
* where <REMOTE_IP> is the IP of the computer running I2P.  
* Restart I2P.  


### BASIC COMMANDS
* See status  
`~/.i2p/i2prouter status`  

* Start  
`~/.i2p/i2prouter start`  

* Stop  
`~/.i2p/i2prouter stop`  

* Stop nicely  
`~/.i2p/i2prouter graceful`  

* __NOTE__: In case you get an error, instead of all the above commands, you'll be able to start I2P using the next:  
`~/.i2p/runplain.sh`  

You can stop the program from inside the [web interface](http://localhost:7657/home).

### BROWSING I2P EEPSITES
Configuration to browse I2P eepsites. To be used with GNU IceCat. Make sure your list of peers is seeded on the web interface configuration page.  _Address Book_ is a list of eepsites.

_OPTION A_
* Go to "Preferences -> Advanced -> Network -> Connection (Settings)"
* Check "Manual proxy configuration"
* Fill with the address  
`127.0.0.1 and port 4444 for HTTP`  
`127.0.0.1 and port 4445 for HTTPS`  
`127.0.0.1 and port 4444 for FTP`  
* In the "No proxy for" add:  
`localhost, 127.0.0.1`  
* Mark "Proxy DNS when using SOCKS".  

_OPTION B_
* Download FoxyProxy.
* Click on the FoxyProxy icon.
* Click on "Add New Proxy".
* On the "General" tab add I2P as the name.
* Go to "Proxy Details" tab.
* In "Host or IP Address" field add _127.0.0.1_.
* In the "Port" field _4444_.
* Click on the "URL Patterns" tab.
* In the "Pattern Name" field add as I2P.
* In the "URL pattern" field enter _\*.i2p\*_.
* Click "OK".
* Right click on the FoxyProxy icon.
* Select "Use proxies baed on their predefined patterns".

### YOUR OWN EEPSITE
* Your own eepsite is already active but invisible, the directory located at:  
`~/.i2p/eepsite/docroot/`  

* The I2P Tunnel Manager contains the setting of your eepsite.

### IRC

* Add the I2P network  
`/server add -network i2p localhost 6668`  
* Connect  
`/connect i2p`  
* Save configuration  
`/save`  

* From now on, to connect simply type  
`/connect i2p`  

### TORRENTS
Normal torrents and i2p torrents are used with different clients. Can't use a regular torrent from a normal tracker.  

#### DOWNLOADING
* Visit a tracker like http://tracker2.postman.i2p and search for the torrent.

_OPTION A_:
* Place your mouse cursor over the magnet icon, right click to disply the menu and click “Copy Link Location".  
* Go to i2psnark in browser (http://localhost:7657/i2psnark/).  
* Paste the magnet URL on the field "From URL"  
* Start the torrent.  

_OPTION B_:
* Download the .torrent file.  
* Move torrent file it to destination ~/.i2p/i2psnark/.  
* Go to i2psnark in browser or refresh page (http://localhost:7657/i2psnark/).  
* Start the torrent


#### CREATING
* Place data in i2psnark directory.  
`mv <TORRENT_DATA> ~/.i2p/i2psnark/`  
* Go to i2psnark in browser or refresh page (http://localhost:7657/i2psnark/).  
* Fill in the fields.  
`Data to seed: ~/.i2p/i2psnark/<TORRENT_DATA>`  
`Tracker: <SELECT_TRACKER>`  
* Create torrent by clicking on "Create Torrent".  
* Start the torrent.  

#### CONFIGURATION
To automatically start torrents once they are added:
* Go to “Configuration”.
* Select “Auto start”.
* Select “Save configuration”.

To change more settings, like download destination for example:  
* Edit configuration file.  
`vi ~/.i2p/i2psnark.config.d/i2psnark.config`  
* Change field ("i2psnark.dir").  
`i2psnark.dir=<DOWNLOAD_DIRECTORY>`  
