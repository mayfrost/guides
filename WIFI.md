# WiFi

Needs "_dhcpcd_" (or "_dhcpclient_"), "_wpa\_supplicant_", "_iproute2_" and wifi firmware (like "_iwlwifi_"). Meant to be run as "_root_" or with "_sudo_"  

* Create the configuration file (as root):  
`wpa_passphrase Your_SSID Your_passwd > /etc/wpa_supplicant.conf`  
* Delete non hashed password from /etc/wpa_supplicant.conf  

* To connect type the following command:  
`ip link set wlan0 down`  
`ip link set wlan0 up`  
`wpa_supplicant -B -iwlan0 -c /etc/wpa_supplicant.conf -Dwext`  
`dhcpcd wlan0`  


You can save the last step in a script.
