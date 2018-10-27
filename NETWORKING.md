# NETWORKING

## SETUP

### /etc/network/interfaces
```
# use last 8 octets for hosts
255.255.255.0
```  

### WiFi

Use WiFi without a separate network manager with this simple guide. Needs "_dhcpcd_" or "_dhcpclient_", "_net-tools_" or "_iproute2_", "_wpa\_supplicant_", and the WiFi drivers for your wireless card (like "_iwlwifi_" and its "_ucode_"), which in part can be installed from a package usually named "_linux-firmware_", but they may not be complete (this provides "_ucode_" but not "_iwlwifi_").  
__NOTE__: The "_<DEVICE_NAME>_" can be either "_wlp3s0_" or "_wlan0_". Change accordingly the following commands to suit your needs.

* Create the configuration file (as "_root_", not "_sudo_"):  
`wpa_passphrase <NETWORK_NAME> <PASSWORD> > /etc/wpa_supplicant.conf`  
* Delete non hashed password from "_/etc/wpa_supplicant.conf_", but not the hashed one.  

Each time you need to connect type the following command (as "_root_" or with "_sudo_"):  

* __EXAMPLE 1__: With "_net-tools_" and "_dhcpcd_":  
```  
ifconfig <DEVICE_NAME> down
ifconfig <DEVICE_NAME> up
wpa_supplicant -B -i<DEVICE_NAME> -c /etc/wpa_supplicant.conf -Dwext
dhcpcd <DEVICE_NAME>  
```

* __EXAMPLE 2__: With "_iproute2_" and "_dhclient_":  
```  
ip link set <DEVICE_NAME> down
ip link set <DEVICE_NAME> up
wpa_supplicant -B -i<DEVICE_NAME> -c /etc/wpa_supplicant.conf -Dwext
dhclient <DEVICE_NAME>  
```

You can save either example in a script to activate the Wi-Fi whenever you want.  

* Note: As an educational tip, the name of a network is also called "_SSID_" in other places.

## TROUBLESHOOTING

### ufw
* Show status  
`sudo ufw status`  
* Enable firewall  
`sudo ufw enable`  
* Disable firewall  
`sudo ufw disable`  
* Deny all by default  
`sudo ufw default deny`  
* Allow all by default  
`sudo ufw default allow`  
* Allow everything for specific port by default  
`sudo ufw allow PORT_NUMBER`  
* Delete a rule  
`sudo ufw delete allow PORT_NUMBER`  
* Allow everything for a specific address  
`sudo ufw allow from IP_ADDRESS`  
* Allow a specific port for a specific address  
`sudo ufw allow from IP_ADDRESS to any port PORT_NUMBER`  

### tcpdump
* dump all  
`sudo tcpdump`  
* dump 5 packets  
`sudo tcpdump -c 5`  
* dump in ASCii format  
`sudo tcpdump -A`  
* dump in hexadecimal format  
`sudo tcpdump -xx`  
* dump from an specific interface  
`sudo tcpdump -i INTERFACE_NAME`  
* dump from a specific port  
`sudo tcpdump port PORT_NUMBER`  
* dump 5 packets in hexadecimal from an specific interface and a specific port  
`sudo tcpdump -c 5 -xx -i INTERFACE port PORT_NUMBER`  

### netstat
* show routing table, including gateway  
`netstat -nr`  
* show all ports  
`netstat -tulpn`  
* show network usage of devices  
`netstat -i`  
* show active connections  
`netstat -ta`  
* show active connections, but show ip addresses instead  
`netstat -tan`  

### traceroute
* show which route your connection takes between your computer to the destination  
`traceroute WEBNAME_OR_IP`  

### nmap
* scan a specific ip address (including devices)  
`nmap IP_NUMBER`  
* scan a specific website  
`nmap WEBSITE_NAME`  
* scan a specific ip address (including devices) with more information  
`nmap -v IP_NUMBER`  
* scan two ip address (including devices), 192.168.0.1 and 192.168.0.54  
`nmap 192.168.0.1,54`  
* scan a range of ip address (including devices), from 192.168.0.1 to 192.168.0.100  
`nmap 192.168.0.1-100`  
* scan all ip address (including devices) from network 192.168.0.0  
`nmap 192.168.0.*`  
* scan address from a file  
`nmap -il <FILE>`  
* scan address and identify OS and running services  
`nmap -A IP_NUMBER`  
* check if target is up  
`nmap -sP IP_NUMBER`  
* check reason for services states  
`nmap --reason IP_NUMBER`  
* show host interfaces  
`nmap --iflist IP_NUMBER`  

## REMOTE CONNECTION
### SSH
* login to remote host  
`ssh ADDRESS`  
* login to remote host as user USER  
`ssh USER@ADDRESS`  

## SERVER
* set ssh server configuration in /etc/ssh/sshd_config  
```
Port 22 # default port is 22, can be changed
PermitRootLogin without-password # change "without-password" to "no" to forbid root login
AllowUsers USER_NAME # by allowing a specific user it restricts the others
```
* restart "ssh" service to activate changes  
