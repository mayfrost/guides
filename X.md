# X
Set __X__ and a desktop environment fast.

1. [INSTALLING X](#installing-x)  
2. [CONFIGURING X](#configuring-x)  
2.1. [SCREEN RESOLUTION](#screen-resolution)  
2.2. [SCREEN TEARING](#screen-tearing)  
2.3. [FONTS](#fonts)  
3. [THEME](theme)  
4. [NO DE](#no-de)  
4.1. [XINITRC CONFIGURATION FILE](#xinitrc-configuration-file)  
4.2. [LAUNCH X](#launch-x)  
4.3. [LAUNCH X AT LOGIN](#launch-x-at-login)  
5. [KEY BINDINGS](#key-bindings)  
5.1. [GETTING KEYS INFORMATION](#getting-keys-information)  
5.2. [XBINDKEYSRC CONFIGURATION FILE](#xbindkeysrc-configuration-file)  
6. [CLIPBOARD](#clipboard)  
6.1. [CLIPBOARD BINDINGS](#clipboard-bindings)  
7. [WINDOW MANAGER](#window-manager)  
7.1. [BASIC SHORTCUTS](#basic-shortcuts)  
7.2. [RATPOISONRC CONFIGURATION FILE](#ratpoisonrc-configuration-file)  

## INSTALLING X
Generally it can be installed from the live _CD or DVD_ or afterwards with the package manager. For example on __CRUX__:
* Installing a minimal set of xorg and xorg dependent tools one by one (you must know which _"DRIVER"_ you use)  
`prtget depinst xorg-server xorg-xf86-video-<DRIVER> xorg-font-util xkeyboard-config xorg-xinit`  
* Alternatively just install the metapackage _"xorg"_  

## CONFIGURING X
__X__ can be configured for several things.

__OPTION 1__  
You can generate a general configuration file containing all sorts of options and that will appear on your home directory and later move it to _"/etc/X11/xorg.conf"_. You need to stop the __X__ server and have root privileges for creating it.  
* Create a new configuration file "xorg.conf.new"  
`Xorg -configure`  
* change it to _"/etc/X11/xorg.conf"_  
`mv /path/to/xorg.conf.new /etc/X11/xorg.conf`  
* on other X versions the commands are  
`XFree86 -configure`  
`XFree86 -xf86config /etc/X11/XF86Config.new`  

__OPTION 2__  
Or you can create specific configuration files under the _"/etc/X11/xorg.conf.d/"_ directory for particular cases.

### SCREEN RESOLUTION
To make changes you generally don't need to know supported resolutions but it helps using defaults.
* List supported resolutions  
`xrandr`  
* Generate a modeline  
`cvt <WIDTH> <HEIGHT> <REFRESH_RATE>`  
* Use that ouput to add changes on the configuration file  _"/etc/X11/xorg.conf"_  
```
Section "Device"
        Identifier   "<DEVICE_NAME>"
        Driver       "<DRIVER_NAME>"
EndSection

Section "Monitor"
        Identifier	"<MONITOR_NAME>"
        Modeline        "<CVT_OUTPUT>
        Option    	"PreferredMode" "<THE_RESOLUTION_YOU_WANT>"
        Option          "Enable" "True"
EndSection

Section "Screen"
        Identifier	"<DEFAULT_SCREEN>"
        Monitor   	"<MONITOR_NAME>"
        Device          "<DEVICE_NAME>"
   SubSection "Display"
      Modes	  "<RESOLUTION_YOU_WANT>"
   EndSubSection
EndSection
```  
In _"Modes"_ the resolution you want can contain a framerate appended but needs to be exactly the same from the modeline. A full example configuration follows:  
```
Section "Device"
    Identifier    "Device0"
    Driver        "Intel"
EndSection

Section "Monitor"
    Identifier    "HDMI1"
    Modeline "1280x720_60.00"   74.50  1280 1344 1472 1664  720 723 728 748 -hsync +vsync
    Option "PreferredMode" "1280x720"
    Option "Enable" "True"
EndSection

Section "Screen"
    Identifier     "Screen0"
    Monitor        "HDMI1"
    Device         "Device0"
    SubSection "Display"
        Modes       "1280x720_60.00"
    EndSubSection
EndSection

```  
Notice the framerate appended with an underscore in _"Mode"_, this comes from _"Modeline"_.

### SCREEN TEARING
To solve screen tearing you can use any of these config files in its appropriate directory.

* If you have Intel add these changes to _"/etc/X11/xorg.conf"_ or in the separate file _"/etc/X11/xorg.conf.d/20-intel.conf"_:
```
Section "Device"
   Identifier  "Intel Graphics"
   Driver      "intel"
   Option      "TearFree"  "true"
EndSection
```

* If you still have issues with Intel add a line with the option _UXA_:
```
Section "Device"
   Identifier  "Intel Graphics"
   Driver      "intel"
   Option      "AccelMethod"  "uxa"
   Option      "TearFree" "true"
EndSection
```

* If you have AMD add these changes to _"/etc/X11/xorg.conf"_ or in the separate file _"/etc/X11/xorg.conf.d/20-amdgpu.conf_":
```
Section "Device"
   Identifier  "AMD Graphics"
   Driver      "amdgpu"
   Option      "TearFree"  "true"
EndSection
```  

### FONTS
Fonts can be added to the database on _"/etc/X11/xorg.conf"_ or in the separate file _"/etc/X11/xorg.conf.d/fonts.conf_":
```
Section "Files"
        FontPath     "/path/to/fonts/"
        FontPath     "/path/to/another/fonts/"
EndSection
```  
Where _"/path/to/fonts/"_ can be the default _/usr/local/share/fonts/_, a directory under _/usr/local/share/fonts/_, or any directory of your choosing.

## THEME
To tweak the theme of your terminal emulator you need to tweak the _".Xresources"_ file.

Next is an example _".Xresources"_ file which goes under your home directory:
```
xterm*maximized:	true
xterm*background:	black
xterm*foreground:	grey
xterm*cursorColor:	green
xterm*cursorBlink:	false
xterm*faceName:	Fixedsys Excelsior 3.01:size=11:antialias=true
xterm*faceNameDoublesize:	WenQuanYi Zen Hei
xterm*termName:	xterm-256color
xterm*locale:	true
xterm*utf8Title:	true
xterm*dynamicColors: true
xterm*borderWidth: 0
xterm*eightBitInput:   false
xterm*metaSendsEscape: true
xterm*decTerminalID:	vt340


urxvt*maximized:	true
urxvt*background:	black
urxvt*foreground:	white
urxvt*cursorColor:	green
urxvt*cursorBlink:	false
urxvt*faceName:	GNU Unifont:size=12:antialias=true
urxvt*faceNameDoublesize:	WenQuanYi Zen Hei
urxvt*termName:	urxvt-256color
urxvt*locale:	true
urxvt*utf8Title:	true
urxvt*font: fixed
urxvt*boldFont: fixed
urxvt*dynamicColors: true
urxvt*borderWidth: 0
```  

To load changes run:  
`xrdb -merge ~/.Xresources`

## NO DE
To use a window manager without any desktop environment, or even a login manager, you can just install the applications mentioned here and edit the _".xinitrc"_ file with the appropriate changes and start _"X"_ from the command line. The required applications are:
* Ratpoison (or your preferred window manager in the _".xinitrc"_ file)
* Xbindkeys
* hsetroot or imagemagick (or replace with your preferred wallpaper changer in the _".xinitrc"_ file)
* ImageMagick (or replace with your preferred screenshot program in the _".xinitrc"_ file)
* FFmpeg or libav-tools (or replace with your preferred screencasting program in the _".xinitrc"_ file)
* UXTerm or urxvt (in the case you want to set the terminal emulator theme with the _".Xresources"_ file)
* dmenu

### XINITRC CONFIGURATION FILE
Next is an example _".xinitrc"_ file which goes under your home directory:  
```
# load your preferred terminal settings
xrdb -merge -I$HOME ~/.Xresources

# load your preferred keybindings
xbindkeys

# set the wallpaper (requires hsetroot to be installed)
hsetroot -fill ~/.wallpaper.jpg

# alternative way to set the wallpaper using imagemagick (DISABLED)
#display -size 1280x800 -window root ~/.wallpaper.png

# launch the window manager (needs to be done at the end)
exec dbus-launch --sh-syntax --exit-with-session ratpoison
```
### LAUNCH X
After the configuration file is properly set, you login and type on the terminal:  
`startx`  
whenever you want to start X.

### LAUNCH X AT LOGIN
To launch X at login, place the following at either your _".bash_profile"_ or _".bashrc"_ file:
```
if [ $(tty) = "/dev/tty1" ]
then
    startx > /dev/null 2>&1
fi
```
This will automatically launch _"X"_ at the first _"tty"_ (_"virtual terminal"_). If you are confused, to switch between ttys press _"Ctrl-Alt-F\<X>"_ (where _"\<X>_" is a number). So to change to the tty with xorg you'll press _"Ctrl-Alt-F1"_.

## KEY BINDINGS
Custom keys can be added with the __Xbindkeys__ program.

### GETTING KEYS INFORMATION
With the help of the default xev program you can check the keys you want:
* Start the program and type the key you want to see its information  
`xev > keys.txt`  
* Look for the line that says  
`keycode KEY_NUMBER (keysym INGORE_THIS, KEY_NAME)`  
* Now on _".xbindkeysrc"_ add the information for each bind:
```
"WHAT_YOU_WANT_HERE_GOES_HERE"
  m:0x0 + c:KEY_NUMBER
  KEY_NAME
```

### XBINDKEYSRC CONFIGURATION FILE
In the example below we'll have the modified keys:
* The "windows" key switch windows using dmenu pre-installed.
* The "menu" key brings an application launcher you type names into using dmenu.
* The "print screen" key takes a screenshot using imagemagick.
* The "scroll lock" key records the desktop using either libav-tools or ffmpeg.
* The "mute" button if available will mute/unmute volume.
* The "lower volume" button if available will lower volume.
* The "raise volume" button if available will raise volume.

Now the example _".xbindkeysrc"_ file which goes under your home directory:
```
# Enable "Scroll_Lock" for the next keybinding
keystate_scrolllock= enable

# Switch windows using the "windows key" (needs dmenu)
"ratpoison -c "select $(ratpoison -c "windows "%t"" | dmenu -nf gray -nb black -sf black -sb gray -b -l 20)""
  Super_L

# Launch application using the "menu key" (needs dmenu)
"dmenu_run -nf gray -nb black -sf black -sb gray -b"
  m:0x0 + c:135
  Menu

# Take screenshot using the "print screen key" (needs imagemagick)
"import -window root png:$HOME/x_$(date "+%Y-%m-%d-%H:%M:%S").png"
  m:0x0 + c:107
  Print

# Record desktop with avconv (libav-tools) or install ffmpeg and replace avconv
"killall -INT avconv 2>/dev/null || avconv -f x11grab -r 10 -s $(xrandr | grep '*' |  tr -s ' ' | cut -d ' ' -f2) -i :0.0 $HOME/x_$(date "+%Y-%m-%d-%H:%M:%S").mp4 &"
  m:0x0 + c:78
  Scroll_Lock

# Mute/unmute volume
"amixer set Master toggle"
  m:0x0 + c:121
  XF86AudioMute

# Lower volume
"amixer set PCM 5%-"
  m:0x0 + c:122
  XF86AudioLowerVolume

# Raise volume
"amixer set PCM 5%+"
  m:0x0 + c:123
  XF86AudioRaiseVolume
```

## CLIPBOARD
_"Xsel"_ with the help of _"GNU Screen"_ will be used as intermediary between the terminal and _"X"_. The following commands are examples we will replace by more simple bindings:
* To paste from _"X"_ clipboard  
`xsel -ob`  
* To copy to _"X"_ clipboard from inside _"GNU Screen"_  
`cat | xsel -ib`  
Then hit _"Ctrl-a + ]"_, then _"Enter"_, then _"Ctrl-d"_.  

### CLIPBOARD BINDINGS
For ease of use we will use _"GNU Screen's"_ configuration file _".screenrc"_ to save shortcuts for clipboard exchange instead of the above commands. Save these in your _".screenrc"_ file:
```
# Copy from "GNU Screen" to "X" clipboard automatically when using "GNU Screen's" copy selection
bindkey -m ' ' eval 'stuff \040' 'writebuf' 'exec sh -c "xsel -ib < /tmp/screen-exchange"'

# Copy from "X" to "GNU Screen" clipboard by pressing "Ctr-a + b" + "Ctrl-a + ]" on "GNU Screen's" normal mode
bind b eval 'exec sh -c "xsel -ob > /tmp/screen-exchange && screen -X readbuf"'
```  

## WINDOW MANAGER
Productive, automated, scriptable, and minimal, __Ratpoison__ is a strict tiling window manager using bindings similar to GNU Screen. A few of its benefits are.
* No mouse used, all done by commands called by typing _"control"_ and _"t"_ at the same time, plus another key.
* You can set your own bindings in the file _".ratpoisonrc"_ which is extremely friendly.
* Extensible by [scripts](http://ratpoison.wxcvbn.org/cgi-bin/wiki.pl/Scripts). The _"rpws"_ script for example adds multiple workspaces (comes by default with Ratpoison), another script (_"[expose.pl](http://ratpoison.wxcvbn.org/cgi-bin/wiki.pl/expose.pl)"_) gives a mozaic of current windows.
* Can temporarily switch to another window manager with the _"tmpwm"_ command for your comfort.
* Full manual available from the terminal:  
`info ratpoison`  

### BASIC SHORTCUTS
* Show the help cheatsheet:  
`Ctrl-t + ?`  
* Bring an application menu:  
`Ctrl-t + .`  
* Get time and date:  
`Ctrl-t + a`  
* Clear screen from help cheatsheet or menu:  
`Esc`  

* Show open windows:  
`Ctrl-t + w`  
* Close a window:  
`Ctrl-t + k`  
* Swith back between windows:  
`Ctrl-t + Ctrl-t`  
* Go to next window:  
`Ctrl-t + n`  
`Ctrl-t + Space`  
* Go to previous window:  
`Ctrl-t + p`  


* Split screen vertically:  
`Ctrl-t + s`  
* Split screen horizontally:  
`Ctrl-t + S`  
* Go to next frame:  
`Ctrl-t + Tab`  
* Go to previous frame:  
`Ctrl-t + Alt-Tab`  
* Make a window the only one visible:  
`Ctrl-t + Q`  

### RATPOISONRC CONFIGURATION FILE
The next custom _".ratpoisonrc"_ file goes under your home directory and can be customized to your needs. It adds several goodies through scripts like an expose-like effect showing all windows on the screen arranged in a mozaic which you can choose by pressing the number from its tag:
```
# text editor
bind e exec gjots2
bind E exec xterm -e elvis

# web browser
bind y exec icecat
# highlight an url in a window and the url is opened in a new tab
bind Y exec icecat -new-tab `$RATPOISON -c getsel`

# MOC as a music player, alsamixer as volume control
bind o exec xterm -e mocp
bind O exec xterm -e alsamixer

# file manager
bind d exec spacefm
bind D exec xterm -e vifm

# mail
bind g exec xterm -e mutt

# IRC
bind h exec xterm -e irssi

# RSS
bind j exec liferea
bind J exec xterm -e newsbeuter

# password manager
bind z exec xterm -e kpcli

# looks for the JDownloader program under the designated path
bind Z exec ~/jd2/JDownloader2

# expose-like switch window by using "Ctrl-t + ,"
bind comma exec ~/bin/expose.pl

# as colon invoke ratpoison commands, semicolon invoke shell commands ("Ctrl-t + ;")
bind semicolon exec

# no startup message announcing what the prefix keys are
startup_message off

# change font, color and position for messages
set font "Fixed-11"
set fgcolor gray
set bgcolor black
set bargravity c

# normal cursor
exec xsetroot -cursor_name left_ptr

# fix java swing, needs wmname from suckless
exec wmname LG3D

# multiple workspaces by using "Alt + FX" (where "FX" is from F1 to F4), needs rpws script
exec rpws init 4 -k

# get rid of the one pixel border around windows
set border 0
```
