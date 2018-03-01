# WiFi

Use WiFi without a separate network manager with this simple guide. Needs "_dhcpcd_" (or "_dhcpclient_"), "_wpa\_supplicant_", "_iproute2_" and wifi firmware (like "_iwlwifi_").  

* Create the configuration file (as "_root_", not "_sudo_"):  
`wpa_passphrase <NETWORK_NAME> <PASSWORD> > /etc/wpa_supplicant.conf`  
* Delete non hashed password from /etc/wpa_supplicant.conf  

* Each time you need to connect type the following command (as "_root_" or with "_sudo_"):  
`ip link set wlan0 down`  
`ip link set wlan0 up`  
`wpa_supplicant -B -iwlan0 -c /etc/wpa_supplicant.conf -Dwext`  
`dhcpcd wlan0`  


You can save the last step in a script.  

* Note: The name of a network is also called "_SSID_".
