# X
Set xorg and a desktop environment fast.

1. [NO DE](#no-de)  
1.1. [XINITRC CONFIGURATION FILE](#xinitrc-configuration-file)  
1.2. [LAUNCH X](#launch-x)  
1.3. [LAUNCH X AT LOGIN](#launch-x-at-login)  
2. [RATPOISON](#ratpoison)  
2.1. [BASIC SHORTCUTS](#basic-shortcuts)  
2.2. [RATPOISONRC CONFIGURATION FILE](#ratpoisonrc-configuration-file)  
3. [XBINDKEYS](#xbindkeys)  
3.1. [GETTING KEYS INFORMATION](#getting-keys-information)  
3.2. [XBINDKEYSRC CONFIGURATION FILE](#xbindkeysrc-configuration-file)  
4. [TERMINAL EMULATOR](terminal-emulator)  
5. [SCREEN TEARING](#screen-tearing)  


## NO DE
To use a window manager without any desktop environment, or even a login manager, you can just install the applications mentioned here and edit the _".xinitrc"_ file with the appropriate changes and start _"X"_ from the terminal. The required applications are:
* Ratpoison
* Xbindkeys
* hsetroot or imagemagick (or replace it in _".xinitrc"_ with your preferred wallpaper changer)
* ImageMagick (or replace it in _".xinitrc"_ with your preferred screenshot program)
* FFmpeg or libav-tools (or replace it in _".xinitrc"_ with your preferred screencasting program)
* UXTerm or urxvt
* dmenu

### XINITRC CONFIGURATION FILE
Next is an example _".xinitrc"_ file which goes under your home directory:  
```
# load your preferred terminal settings
[[ -f ~/.Xresources ]] && xrdb -merge -I$HOME ~/.Xresources

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
This will automatically launch _"X"_ at the first _"tty"_ (_"virtual terminal"_). If you are confused, to switch between ttys press _"Ctrl-Alt-F<X>"_ (where _"X_" is a number).

## RATPOISON
Productive, automated, scriptable, and minimal, Ratpoison is a strict tiling window manager using bindings similar to GNU Screen. A few of its benefits are.
* No mouse used, all done by commands called by typing _"control"_ and _"t"_ at the same time, plus another key.
* You can set your own bindings in the file _".ratpoisonrc"_ which is extremely friendly.
* Extensible by scripts. The _"rpws"_ script for example adds multiple workspaces (comes by default), another script (_"expose.pl"_) gives a mozaic of current windows.
* Full manual available from the terminal:  
`info ratpoison`  
* Can temporarily switch to another window manager with the _"tmpwm"_ command for your comfort.

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
The next custom _".ratpoisonrc"_ file goes under your home directory and can be customized to your needs:
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

# expose-like switch window by using "Ctrl-t + ,". Get the script from http://ratpoison.wxcvbn.org/cgi-bin/wiki.pl/expose.pl
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

## XBINDKEYS
Custom keys can be added with the Xbindkeys program.

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
"import -window root png:$HOME/xwz_$(date "+%Y-%m-%d-%H:%M:%S").png"
  m:0x0 + c:107
  Print

# Record desktop with avconv (libav-tools) or install ffmpeg and replace avconv
"killall -INT avconv 2>/dev/null || avconv -f x11grab -r 25 -s 1280x720 -i :0.0 $HOME/output.webm &"
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

## TERMINAL EMULATOR
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
`xrdb -merge`

## SCREEN TEARING
To solve screen tearing you can use any of these config files in its appropriate directory.

* In the case you have Intel add these to _"/etc/X11/xorg.conf.d/20-intel.conf"_:
```
Section "Device"
   Identifier 	"Intel Graphics"
   Driver 	"intel"
   Option "TearFree" "true"
EndSection
```

* In the case you have AMD add these to _"/etc/X11/xorg.conf.d/20-amdgpu.conf_":
```
Section "Device"
   Identifier "AMD Graphics"
   Driver "amdgpu"
   Option "TearFree" "true"
EndSection
```

* Another way to add changes is in the _"/etc/X11/xorg.conf"_ file:
```
Section "Device"
   Identifier  "Intel Graphics"
   Driver      "intel"
   Option      "AccelMethod"  "uxa"
   Option      "TearFree" "true"
EndSection
```
