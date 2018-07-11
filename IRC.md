# IRC Rite

Here is the rite of passage for IRC in which you'll learn its arts and crafts. All these are completely optional steps, except for [most used commands](#step-5-most-used-commands) and [netiquette](#step-6-netiquette) of course, but will greatly improve your experience. For the purpose of this guide I will focus on typing commands as this way is compatible with most clients. In the examples, what is described between a "<" and an ">" is not literal but to be filled with the appropriate reference. The examples preceded by a "$" refer to the shell (command line), the rest which is preceded by a "/" is to be typed inside IRC clients. It is suggested you use between two clients:
* __Hexchat__: a GUI client, configuration is done by regular point ant click.
* __Irssi__: a more traditional unix client where interaction is done only by keyboard, great for people who enjoy scripting.

---

## TOC
1. [Step 1, Registration](#step-1-registration)  
2. [Step 2, Configure your client](#step-2-configure-your-client)  
2.1. [Option 1, SASL](#option-1-sasl)  
2.2. [Option 2, CertFP](#option-2-certfp)  
2.3. [Option 3, Use a free bouncer](#option-3-use-a-free-bouncer)  
3. [Step 3, Set a ZNC bouncer](#step-3-set-a-znc-bouncer)  
3.1. [Connect with CertFP](#connect-with-certfp)  
3.2. [Modules](#modules)  
4. [Step 4, Download files over IRC](#step-4-download-files-over-irc)  
4.1. [With another person](#with-another-person)  
4.2. [Using XDCC](#using-xdcc)  
4.3. [Using fserve](#using-fserve)  
5. [Step 5, Most used commands](#step-5-most-used-commands)  
5.1. [Help commands](#help-commands)  
5.2. [Network commands](#network-commands)  
5.3. [Bouncer commands](#bouncer-commands)  
5.4. [Channel commands](#channel-commands)  
5.5. [Chat commands](#chat-commands)  
5.6. [Filesharing commands](#filesharing-commands)  
6. [Step 6, Netiquette](#step-6-netiquette)  

---

## Step 1, Registration.
Optional, but in order to keep your nickname and have other options for concealing your host you have to register. Each example must be typed on your client.
1. Join a network: `/server -ssl <irc.network_name.net> 6697`  
2. Pick a nickname that is free (you'll have your nick changed until you choose one free): `/nick <your_nickname>`  
3. Request nickname registration (of your current nickname): `/msg NickServ REGISTER <your_password> <your@email.com>`  
4. Check your e-mail and confirm.  
4.1. On __Freenode__: `/msg NickServ VERIFY REGISTER <your_nickname> <confirmation_code_from_email>`  
4.2. On __Rizon__: `/msg NickServ CONFIRM <confirmation_code_from_email>`  
5. Hide your e-mail.  
5.1. On __Freenode__: `/msg nickserv set hidemail on`  
5.2. On __Rizon__: `/msg nickserv set hide email on`  
6. Enable other concealment options.  
6.1. On __Freenode__:  
6.1.1. Check for available staff: `/stats p`  
6.1.2. Message an available staff: `/msg <nickname_of_staff> Hello, may I have an unaffiliated cloak?`  
6.1.3. Wait until they give you the cloak.  
6.2. On __Rizon__:  
6.2.1. Request a vHost (pick an appropriate vhost): `/msg HostServ REQUEST <vhost.goes.here>`  
6.2.2. Wait until staff confirms.  
6.2.3. When confirmed type: `/msg HostServ ON`  

---

## Step 2, Configure your client
To connect using your nick you need to choose one of these options.

### Option 1, SASL
1. On __Hexchat__:  
1.1. Open the Network List (Ctrl + S)  
1.2. Find each network to connect in the list then click on Edit to enter the Edit menu  
1.3. On the Edit menu check "Use SSL..." and "Accept invalid SSL"  
1.4. On the Edit menu uncheck the use of global user identification  
1.5. On the Edit menu enter your nick in the Nick name and User name field  
1.6. On the Edit menu select SASL (username + password) in the Login method field  
1.7. On the Edit menu enter your password in the password field  
2. On __irssi__:  
2.1. Edit `~/.irssi/config` to change your nick and match the network nick to make auto registration.  
2.2. Inside irssi type:  
```  
/server add -auto -net <network_name> -ssl -ssl_verify <irc.network_name.net> 6697
/network add -sasl_username <your_nickname> -sasl_password <your_password> -sasl_mechanism PLAIN <network_name>
/save  
```

### Option 2, CertFP
* Open a command line and type (you will be asked some questions, the importance of filling these correctly may vary):  
```  
$ openssl req -x509 -newkey rsa:4096 -sha256 -days 365 -nodes -keyout Certificate.key -out Certificate.crt
$ cat Certificate.crt Certificate.key > Certificate.pem
$ rm Certificate.crt Certificate.key  
```
Before jumping to each client, note that for both clients the network and hostname should match (including the lower and uppercase) to what you already use.
1. On __HexChat__:  
1.1. Rename the pem file to the network you wish (`<Network_name>.pem`) and move it to `~/.config/hexchat/certs/`  
1.2. Open the Network List (Ctrl + S)  
1.3. Find each network to connect in the list then click on Edit to enter the Edit menu  
1.4. On the Edit menu select the boxes "Use SSL for all the servers on this network" and "Accept invalid SSL certificate"  
1.5. On the Edit menu select SASL EXTERNAL (cert) in the Login method field  
1.6. Connect to the network: `/server -ssl <network_name> 6697`  
1.7. Login: `/msg NickServ IDENTIFY <your_password>`  
1.8. Register your fingerprint (append FINGERPRINT if on Rizon): `/msg NickServ cert add`  
2. On __irssi__:  
2.1. Rename the pem file to the network you wish (`<network_name>.pem`) and move it to `~/.irssi/certs/`  
2.2. Edit `~/.irssi/config` to change your nick and match the network nick to make auto registration  
2.3. Remove the server (make sure to remove all instances): `/server remove <irc.network_name.net>`  
2.4. Add it again with the SSL flag: `/server add -ssl -ssl_cert ~/.irssi/certs/<network_name>.pem -network <network_name> <irc.network_name.net> 6697`  
2.5. Connect to the network (do not /reconnect): `/connect <network_name>`  
2.6. Login: `/msg NickServ IDENTIFY <your_password>`  
2.7. Register your fingerprint (use "`/msg NickServ access`" if on Rizon): `/msg NickServ cert add`  
2.8. Save changes: `/save`  

### Option 3, Use a free bouncer
Choose a network address (`<irc.network_name.net>`) from http://wiki.znc.in/Providers, and use steps provided by the service. After you sign to a bouncer configure your client.
1. On __Hexchat__:  
1.1. Open the Network List (Ctrl + S)  
1.2. Create a new network in the list then click on Edit to enter the Edit menu  
1.3. On the servers list add the BOUNCER address followed by the port: `<BOUNCER_address>/<BOUNCER_port_number>`  
1.4. On the Edit menu check "Use SSL..." and "Accept invalid SSL"  
1.5. On the Edit menu uncheck the use of global user identification  
1.6. On the Edit menu enter `<BOUNCER_username>/<network_name>` in the User name field  
1.7. On the Edit menu select SASL (username + password) in the Login method field  
1.8. On the Edit menu enter your `<BOUNCER_password>` in the password field  
2. On __irssi__:  
2.1. Add the BOUNCER name to your client: `/network add <BOUNCER_name>`  
2.2. Add the BOUNCER server: `/server add -net <BOUNCER_name> -ssl <BOUNCER_address> <BOUNCER_port_number> <BOUNCER_username>:<BOUNCER_password>`  
2.3. Save changes: `/save`  
2.4. Connect to the BOUNCER: `/connect <BOUNCER_name>`  
2.5. Login as you normally would.  

---

## Step 3, Set a ZNC bouncer
ZNC is a bouncer which means if you have a home server or a VPS you can have your own bouncer to keep track of the conversation and for a few more options. During the configuration wizard of ZNC you are prompt to some options, if is not mentioned here is safe to leave blank except for the modules so first check the modules you want. If you want a web interface to control ZNC on global modules choose the "webadmin" option.
1. Make sure you have `libicu-dev` for unicode characters and `libssl-dev` for SSL support (optional): `$ sudo <package_manager_installation_command> libicu-dev libssl-dev`  
2. Create a user for ZNC: `$ sudo adduser znc`  
3. Switch to that user: `$ su znc`  
4. Change to the user's home directory: `$ cd ~`  
5. Install ZNC on your server. You can install like any other application, but an EXTRA OPTIONAL manual installation from source is here described:  
5.1. Download: `$ wget -c http://znc.in/releases/znc-latest.tar.gz`  
5.2. Untar: `$ tar -xzvf znc-latest.tar.gz`  
5.3. Change to the unziped directory: `$ cd znc-<version>`  
5.4. Configure installation and path (choose whatever but preferably use "`$HOME/.bin`"): `$ ./configure --prefix="</path/to/znc/program>"`  
5.5. Make: `$ make`  
5.6. Install: `$ make install`  
6. Change back to znc home direcoty: `$ cd ~`  
7. Remove files you don't need: `$ rm -r znc-*`  
8. Change to where znc is installed: `$ cd </path/to/znc/program>`  
9. Launch the configuration wizard: `$ ./znc --makeconf`  
10. Add a port to run ZNC on (don't run in anything less than 1024): `<znc_port_number>`  
11. If you know you have openssl choose to connect with SSL to your server (you need this for certauth).  
12. Choose if you want to connect with ipv6 to your server (if you know your server supports it, otherwise choose "no").  
13. Add a user name for login to ZNC: `<znc_username>`  
14. Add a password for that login: `<znc_password>`  
15. Choose if you want that login be an administrator of ZNC.  
16. Add your IRC username: `<your_nickname>`  
17. When asks to setup a new server choose "yes".  
18. Add IRC server address:  `<irc.network_name.net>`  
19. Add a port to connect to the network, should be 6697 unless otherwise specified.  
20. If you want to tunnel through Tor use proxychains (optional):  
20.1. Install Tor and proxychains: `$ sudo <package_manager_installation_command> proxychains tor`  
20.2. Get ZNC process ID: `$ pkill znc`  
20.3. Start Tor (is recommended to run inside GNU Screen): `$ tor`  
20.4. Start ZNC under proxychains: `$ proxychains </path/to/znc/program>/znc`  
21. When done with the configuration exit the znc user just by pressing CTRL-d does the trick or you can type "exit".  
22. While still on the server add a cron job to autostart ZNC (if these don't work you are not using vixie cron).  
22.1. Start the cron daemon:  
22.1.1. With System V: `$ sudo update-rc.d cron enable`  
22.1.2. With systemd: `$ sudo systemctl enable cron.service`  
22.2. Add a cron job: `$ sudo crontab -e -u znc`  
22.3. Add the lines (if you DIDN'T do the manual install the location should be "`/usr/local/bin/znc`"): `@reboot </path/to/znc/program> >/dev/null 2>&1`  
22.4. If you use ZNC only in your local network add these lines too to set a tight firewall:  
```  
$ sudo iptables -I INPUT -p tcp --dport <znc_port_number> -s 192.168.18.0/24 -j ACCEPT
$ sudo iptables -A INPUT -p tcp --dport <znc_port_number> -j DROP  
```
23. Configure authentication of the irc client you use on your computer:  
23.1. On __Hexchat__:  
23.1.1. Open the Network List (Ctrl + S)  
23.1.2. Create a new network in the list then click on Edit to enter the Edit menu  
23.1.3. On the servers list add you ZNC server address followed by the port: `<znc_server_ip>/<znc_port_number>`  
23.1.4. On the Edit menu check "Use SSL..." and "Accept invalid SSL"  
23.1.5. On the Edit menu uncheck the use of global user identification  
23.1.6. On the Edit menu enter `<znc_username>/<network_name>` in the User name field  
23.1.7. On the Edit menu select SASL (username + password) in the Login method field  
23.1.8. On the Edit menu enter your `<znc_password>` in the password field  
23.2. On __irssi__:  
23.2.1. Remove the server (make sure to remove all instances): `/server remove <irc.network_name.net>`  
23.2.2. Add the ZNC server in its place. NOTE: You can use another name for the network and leave the normal name to connect directly without the bouncer such as znc_network_name:  
```  
/network add <znc_network_name>
/server add -net <znc_network_name> -ssl <znc_server_ip> <znc_port_number> <znc_username>/<network_name>:<znc_password>
/save  
```
23.2.3. Connect to ZNC pointing to the network: `/connect <znc_network_name>`  
23.2.4. Login as you normally would for each network you want ZNC to stay connected: `/msg NickServ IDENTIFY <your_password>`  

### Connect with CertFP
OPTIONAL but ADVISED as it will hide your password on your network.
1. Load the certauth module: `/msg *status LoadMod certauth`  
2. Copy your pem file to the server running ZNC and to `/home/znc/.znc/users/<znc_username>/networks/<network_name>/moddata/cert/user.pem`.  
3. Add your fingerprint to the ZNC server: `/msg *certauth add`  
4. Restart the ZNC server: `/msg *status Restart`  
5. Configure your client.  
5.1. On __HexChat__:  
5.1.1. Rename the pem file to the network you wish (`<znc_network_name>.pem`) and move it to `~/.config/hexchat/certs/`.  
5.1.2. Open the Network List (Ctrl + S).  
5.1.3. Create a new network in the list then click on Edit to enter the Edit menu.  
5.1.4. On the servers list add you ZNC server address followed by the port: `<znc_server_ip>/<znc_port_number>`  
5.1.5. On the Edit menu select the boxes "Use SSL for all the servers on this network" and "Accept invalid SSL certificate".  
5.1.6. On the Edit menu uncheck the use of global user identification.  
5.1.7. On the Edit menu enter `<znc_username>/<network_name>` in the User name field.  
5.1.8. On the Edit menu select SASL EXTERNAL (cert) in the Login method field.  
5.1.9. On the Edit menu enter your `<znc_password>` in the password field.  
5.1.10. Connect to ZNC pointing to the network: `/server -ssl <znc_network_name> <znc_port_number>`  
5.2. On __irssi__:  
5.2.1. Remove the server (make sure to remove all instances): `/server remove <znc_server_ip>`  
5.2.2. Add the server pointing to the pem file and without the password:  
```  
/server add -ssl -ssl_cert ~/.irssi/certs/<znc_network_name>.pem  -net <znc_network_name> <znc_server_ip> <znc_port_number> <znc_username>/<network_name>:
/save  
```
5.2.3. Connect to ZNC pointing to the network: `/connect <znc_network_name>`  
6. Confirm fingerprint for each network (requires "cert" module loaded).  
6.1. Login: `/msg NickServ IDENTIFY <your_password>`  
6.2. __FREENODE__  
6.2.1. To look for you fingerprint on FREENODE: `/msg NickServ cert list`  
6.2.2. Connect to FREENODE: `/msg NickServ cert add <fingerprint>`  
6.3. __RIZON__  
6.3.1. To look for you fingerprint on RIZON: `/msg NickServ access list`  
6.3.2. Connect to RIZON: `/msg NickServ access add fingerprint <fingerprint>`  
7. From now on just connect to ZNC pointing to the network: `/connect <znc_network_name>`  

### Modules
Some modules are required for further options.
* To list all available modules: `/msg *status ListAvailMods`  
* To load modules: `/msg *status LoadMod <znc_module_name>`  
Some modules you may want are:
* "chansaver": ZNC config up to date with channels you parted/joined so that you don't have to add them manually.  
* "dcc" and "bouncedcc": transfer files to and from ZNC, while using ZNC as a middle man.  
* "controlpanel": edit ZNC configuration through your IRC client.  
* "perform": keep a list of commands to be executed.  
* "sasl": authenticate to an IRC network with SASL, you will also need this for authenticating with a certificate.  
* "cert": authenticate to an IRC network with a certificate.  
* "certauth": required to use a certificate and hide your password from plain files.  

---

## Step 4, Download files over IRC
Certain channels have bots or fservers. IRC indexers are websites providing the channel name, bot/fserver name, and files available. Search on XDCC search engines and indexers for channels, available files and bots/fservers providing them. You can find some indexers https://en.wikibooks.org/wiki/Downloading_Files_from_IRC/XDCC_Bot_Guide#XDCC_Search_Engines.

### With another person
1. Make sure to start the DCC server: `/dcc server`  
2. Ask politely if you can share a file with that person.  
3. Send files to that person: `/DCC send <someone's_nickname> </path/to/file>`  
4. Or accept files: `/DCC get <someone's_nickname>`  

### Using XDCC
1. List bot contents: `/msg <bot_name> XDCC LIST`  
_If the previous displays a warning with a website you have to go to that website to get listings, or if it shows a command you need to type that command._
2. To show available bot commands: `/msg <bot_name> XDCC HELP`  
3. To search for inside the bot's contents: `/msg <bot_name> XDCC SEARCH <anything_goes_here>`  
4. To display information on the file: `/msg <bot_name> XDCC INFO <file>`  
5. To download a file (can use GET instead of SEND): `/msg <bot_name> XDCC SEND <file>`  
6. To download a file with a password (can use GET instead of SEND): `/msg <bot_name> XDCC SEND <file> <password>`  
7. To cancel current download: `/msg <bot_name> XDCC CANCEL`  
8. To download all files matching `<file_pattern>`: `/msg <bot_name> XDCC BATCH <file_pattern>`  
9. To download all files with a password matching `<file_pattern>`: `/msg <bot_name> XDCC BATCH <file_pattern> <password>`  
10. To download all files matching between `<file_pattern1>` and `<file_pattern3>`: `/msg <bot_name> XDCC BATCH <file_pattern1>-<file_pattern3>`  
11. To download all files with a password matching between `<file_pattern1>` and `<file_pattern3>`: `/msg <bot_name> XDCC BATCH <file_pattern1>-<file_pattern3> <password>`  
12. To remove a download from queue (if `<file>` is not given it will remove all): `/msg <bot_name> XDCC REMOVE <file>`  
13. To show download queue and estimated download time: `/msg <bot_name> XDCC QUEUE`  

### Using fserve
1. To request a file if you already know the name and location: `/dcc get <fserve_name> <folder/><file>`  
2. To connect to a bot and browse its file collection: `/ctcp <fserve_name> collection <number>`  
3. On the bot chat use different keywords for specific tasks, "`dir`" will list of all files and sub-directories, "`cd <directory>`" will change to desired directory (with "`cd ..`" changing to upper folder), "`get <file>`" will request a file, and "`exit`" will disconnect from bot chat.  
4. If the server displays numbers followed with letters then you can instead type those to enter folders or download files (e. "`1d`"): `<number><letter>`  

---

## Step 5, Most used commands
Anything that starts with a forward slash is an IRC client command. To login you need to either type these each time or configure your client to do it for you. To connect on Hexchat you can go to network list. Whenever you enter IRC you connect to a network but you are not immediately connected to a channel.

### Help commands
* To see the help from your IRC client (`<some_command>` is optional): `/help <some_command>`  
* To see network specific help (while in that network's window -`<some_command>` is optional-): `/msg NickServ help <some_command>`  

### Network commands
* To join a network: `/server -ssl <irc.network_name.net> 6697`  
* To join a network (after you set your client): `/server <network_name>`  
* To join a network without leaving the current network (on irssi): `/connect <network_name>`  
* To quit a network (while in a window from that network): `/discon`  
* To login with your nickname (if you didn't set your client): `/msg NickServ IDENTIFY <your_password>`  

### Bouncer commands
* To join the BOUNCER server (if you didn't set not your client): `/server -ssl <BOUNCER_address> <BOUNCER_port_number> <BOUNCER_username>:<BOUNCER_password>`  
* To join the BOUNCER server (if you set your client): `/connect <BOUNCER_name>`  
* To join the ZNC server (if you set ZNC but not your client): `/server -ssl <znc_server_ip> <znc_port_number> <znc_username>:<znc_password>`  
* To join the ZNC server (if you set ZNC and certauth, but not your client): `/server -ssl <znc_server_ip> <znc_port_number> <znc_username>:`  
* To join the ZNC server (if you set ZNC and your client): `/connect <znc_network_name>`  

### Channel commands
* To search for channels: `/list *<pattern>*`  
* To search for channels (on __Freenode__): `/msg alis LIST *<pattern>*`  
* To join a channel: `/join #<some_channel>`  
* To quit a channel (when you are in that channel): `/part`  
* To change the channel's topic: `/msg ChanServ TOPIC #<some_channel> <topic_goes_here>`  

### Chat commands
* To describe yourself in third person (mostly describing an action): `/me <does_something>`  
* To send a message to a single individual: `/msg <someone's_nickname> <some_message>`  
* To open a chat window with a single individual: `/query <someone's_nickname>`  
* To close a chat window of a single individual (in the window of that individual): `/q`  

### Filesharing commands
* To send files to someone: `/DCC send <someone's_nickname> </path/to/file>`  
* To accept files from someone: `/DCC get <someone's_nickname>`  
* To start the DCC server: `/dcc server`  
* To close the DCC server: `/dcc close server <port>`  
* To list all bots and fservers on the current channel: `!list`  
* To search for any number of files on any number of bots or fservers on the current channel: `@find <anything_goes_here>`  
* To add a bot/fserve/nick to whitelist: `/set dcc_autoget_masks <bot/fserve/nick_name>`  
* To set to accept everything (not advised): `/set dcc_autoget`  

---

## Step 6, Netiquette
Netiquette refers to etiquete on IRC.
* Always check the topic on each channel.  
* Familiarize with jargon. Although not all communities make use of abbreviations, strange terminology and inside jokes, some IRC users sometimes makes heavy use, learn them. Be careful not to be in a community were your own is misunderstood. Make sure to check twice what it means for that specific community.  
* Don't abuse capslock. Entire words in capslock is like yelling, try to limit or straight eliminating its use.  
* Make questions the smart way. Be polite if you want to ask for something, also be precise, concise and informative, and have patience.  
* Lurk! You see people join an IRC channel, say something, and then leave 2 minutes later because they haven't been replied to yet. The speed of IRC conversations can be realtime, but sometimes can also be much slower than that. You should be willing to leave your IRC program running 24/7 so you can participate in longer-timescale conversations. This is also the best way to guarantee that you get questions answered.  

