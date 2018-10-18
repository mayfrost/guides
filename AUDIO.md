# AUDIO

## PURE ALSA

Here is how to get sound on a minimal install without the insanity of pulseaudio:

1. Erase __.asoundrc__ in your home directory and __asound.conf__ in __/etc__.  

2. Purge pulseaudio. And when I mean purge, I mean it.  

3. Identify your available devices in __/proc/asound/modules__, do:  
`$ cat /proc/asound/modules`

Here is an example of what you will see in __/proc/asound/modules__:  
```  
0 snd_usb_audio
1 snd_hda_intel  
```

4. Select from the above and put them in the order you want in the file __/etc/modprobe.d/alsa-base.conf__, by assigning an index from -2 to 2, marking the preferred device as the lowest number.  

As an example if you have two devices and want the one that says usb because that is your headphone, on __/etc/modprobe.d/alsa-base.conf__ you will put:  
```  
options snd_usb_audio enable=1 index=0
options snd_hda_intel index=1  
```

Notice the index.  

5. Restart the computer.  

### Run Firefox without pulseaudio

1. Install  __[apulse](https://github.com/i-rinat/apulse)__.  
* Install _"cmake"_, _"libasound2-dev"_ and _"libglib2.0-dev"_ with your package manager.  
* Download _"apulse"_:  
`git clone --depth 1 --single-branch https://github.com/i-rinat/apulse.git`  
* Change to that directory:  
`cd apulse/src` 
* Build:  
```
$ cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release ..
$ make
# sudo make install
```  

2. On Firefox open __about:config__ and enter "__/dev/snd/__" under __security.sandbox.content.read_path_whitelist__ and __security.sandbox.content.write_path_whitelist;/dev/snd/__, IF they exist.  

3. Every time you want to use firefox with this setting issue the command:  
`$ apulse firefox`  
Alternatively save ___"apulse firefox"___ in a script or in a .desktop file for automation.
