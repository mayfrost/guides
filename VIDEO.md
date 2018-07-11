## MPLAYER ON THE TTY (FRAMEBUFFER)
These are settings for your MPlayer config file. 
```  
# framebuffer video ouput
vo=fbdev
# alsa device
ao=alsa:device=hw=0.0
# required to adjust screen without problem
fs=1
# fill screen
zoom = 1
# scale up or down as needed to framebuffer's width; it'll scale the height automatically
# high res
#xy = 1920
# low res
xy = 1420
# buffers x amount of data before playback starts
cache=8192
cache-min=99
# sync video and audio
mc=2
# smooth video play
sws=0
# optional accelaration
lavdopts=fast=1:skiploopfilter=all:threads=16
framedrop=1
# avoid the lirc error message
nolirc=yes
# don't clutter the console with output
really-quiet=1  
```
