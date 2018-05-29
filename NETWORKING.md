# NETWORKING

## WiFi

Use WiFi without a separate network manager with this simple guide. Needs "_dhcpcd_" or "_dhcpclient_", "_net-tools_" or "_iproute2_", "_wpa\_supplicant_", and the WiFi firmware for your wireless card (like "_iwlwifi_" and its "_ucode_").  
__NOTE__: The "_\<DEVICE_NAME>_" can be either "_wlp3s0_" or "_wlan0_". Change accordingly the following commands to suit your needs.

* Create the configuration file (as "_root_", not "_sudo_"):  
`wpa_passphrase <NETWORK_NAME> <PASSWORD> > /etc/wpa_supplicant.conf`  
* Delete non hashed password from "_/etc/wpa_supplicant.conf_", but not the hashed one.  

Each time you need to connect type the following command (as "_root_" or with "_sudo_"):  

* __EXAMPLE 1__: With "_net-tools_" and "_dhcpcd_":  
`ifconfig <DEVICE_NAME> down`  
`ifconfig <DEVICE_NAME> up`  
`wpa_supplicant -B -i<DEVICE_NAME> -c /etc/wpa_supplicant.conf -Dwext`  
`dhcpcd <DEVICE_NAME>`  

* __EXAMPLE 2__: With "_iproute2_" and "_dhclient_":  
`ip link set <DEVICE_NAME> down`  
`ip link set <DEVICE_NAME> up`  
`wpa_supplicant -B -i<DEVICE_NAME> -c /etc/wpa_supplicant.conf -Dwext`  
`dhclient <DEVICE_NAME>`  

You can save either example in a script to activate the Wi-Fi whenever you want.  

* Note: As an educational tip, the name of a network is also called "_SSID_" in other places.
