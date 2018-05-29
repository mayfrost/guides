# AUDIO

## PURE ALSA

Here is how to get sound on a minimal install without the insanity of pulseaudio:

1. Erase .asoundrc in your home directory and asound.conf in /etc. 

2. Purge pulseaudio. And when I mean purge, I mean it.

3. Identify your available devices in /proc/asound/modules, do:
`$ cat /proc/asound/modules`

As an example here is my /proc/asound/modules:
`0 snd_usb_audio`
`1 snd_hda_intel`

4. Select from the above and put them in the order you want in the file /etc/modprobe.d/alsa-base.conf, by assigning an index from -2 to 2, making the preferred output the lowest number. As I know I have two devices I want the one that says usb because that is my headphone, so in /etc/modprobe.d/alsa-base.conf I put:
`options snd_usb_audio enable=1 index=0`
`options snd_hda_intel index=1`

Notice the index.

5. Restart the computer.

6. To run Firefox without pulseaudio install apulse. Go to about:config and enter "__/dev/snd/__" under __security.sandbox.content.read_path_whitelist__ and __security.sandbox.content.write_path_whitelist;/dev/snd/__.  

7. To use firefox with this setting issue the command:
`$ apulse firefox`

8. Save it in a script or .desktop file to automate this.
