# ALTERNATIVES TO BLOATWARE

The list is built pointing to software that have alternatives with less dependencies, and addressing dependencies was the easy thing to do. One thing tho, some particular tools were included because they add less dependencies overall while keeping a system functional. One such example is imagemagick and ffmpeg, by which you can do a lot of work and replace many tools by just using those with scripts and replace something like a screenshot utility. TL;DR is about the unix principle and you can have a fully functional system pretty damn minimal with that.

Certainly it would be great to have a comparative on resource usage tho. Wanna help?

* __Terminal Pager__: less -> most

* __Chat Client__: Pidgin -> Finch (+ irssi mode) -> Centerim -> Bitlbee
* __E-Mail Client__: Thunderbird -> Alpine -> Mutt
* __RSS Feed and Podcast__: Liferea -> Newsbeuter -> Newsboat
* __IRC Client__: HexChat -> Weechat -> Irssi
* __VoIP__: Skype -> Mumble -> Linphone -> sscall

* __Application Launcher__: GNOME Do -> ratmenu -> dmenu -> pdmenu -> slmenu
* __Compositing Window Manager__: Compiz -> Compton -> Xcompmgr
* __Display Color Temperature__: flux -> Redshift -> sct
* __Graphical Settings__: Wpgtk -> LxAppearance -> GSettings -> xsettings
* __Keybinding__: Xbindkeys -> sxhkd -> loadkeys (+ keymaps)
* __Wallpaper Changer__: FEH -> hsetroot -> xsetroot -> imagemagick (but use 10MB more RAM than the others)

* __CD-DVD Burn and Copy__: K3b -> Brasero -> cdw
* __Device Management__: Udisks (+ udevil) -> pmount -> bashmount

* __Virtual Machine__: VirtualBox -> AQEMU + kvm -> Qemu + kvm

* __Batch Renamer__: GPRename -> qmv (renameutils)
* __Duplicate Files Removal__: dupeGuru -> Fdupes
* __File Archiver__: PeaZip -> Xarchiver -> Atool
* __File Manager__: SpaceFM -> Ranger -> Midnight Commander -> noice

* __File Scraper__: JDownloader -> youtube-dl -> cclive -> Plowshare
* __FTP Client__: FileZilla -> lftp
* __Torrent Client__: qBittorrent -> RTorrent -> transmission-daemon (+ transmission-remote-cli, or use the web interface that comes with transmission-daemon)

* __System Information__: zCI -> screenfetch -> inxi
* __Disk Usage__: QDirStat -> Baobab -> xdiskusage -> Ncdu -> df
* __System Monitor__: gnome-system-monitor -> Conky -> htop -> nmon -> top

* __Multiple Audio Streams__: pulseaudio -> apulse
* __Audio Editing__: Audacity -> SoX
* __Audio Mixer and Equalizer__: pavucontrol -> Qastools -> alsa-utils + Alsaequal
* __Metadata__: Easytag -> Beets -> ExifTool
* __Screenshots__: Shutter -> scrot -> maim -> ImageMagick
* __Screencasting__: Open Broadcaster Studio -> SimpleScreenRecorder -> FFmpeg
* __Video Transcoding__: HandBrake -> WinFF -> FFmpeg

* __DNS Resolution__: Unbound + NDS -> BIND9
* __Network Manager__: Wicd -> NetworkManager -> ConnMan -> SetNet

* __Ebook Viewer__: Calibre -> Zathura
* __Printers__: CUPS -> LPR
* __Word Processor__: Libreoffice Writter -> Abiword -> MinEd -> WordGrinder + pandoc
* __Spreadsheets__: Libreoffice Calc -> Gnumeric -> SC-IM + pandoc
* __Text Editor (and IDE)__: Emacs (nox) -> Vim -> Nano -> Vile -> xwpe -> GNU Zile

* __Disk Cleaner__: BleachBit -> bleachbit_cli -> shred
* __Storage Encryption__: VeraCrypt -> tcplay (TrueCrypt implementation) -> Keyringer -> Tomb
* __Password Manager__: KeePassX -> kpcli / pass (+ pass-tomb)

* __Version Control__: Git (+ tig) -> Fossil -> RCS

* __Configuration Management__: Puppet -> CFEngine -> cdist

* __CAD__: AutoCAD -> FreeCAD -> OpenSCAD
* __Graphing Calculator__: KAlgebra -> GraphMonkey -> Maxima + PLplot

* __Firewall__: gufw -> ufw -> iptables -> nftables

* __Cloud__: Google Drive -> Nextcloud -> vsftpd -> sftp
* __E-Mail Filtering (LDA)__: Dovecot -> procmail
* __E-Mail Server (MTA)__: Postfix -> Exim -> cmail
* __E-Mail Spam Filter__: DSPAM -> SpamAssassin
* __VPN__: OpenVPN -> WireGuard
* __Web Caching__: Decentraleyes on a web browser -> Squid
* __Web Filtering__: Ad blocker on a web browser -> Pi-hole -> Privoxy
* __Web Server__: Apache -> Nginx -> lighttpd -> darkhttpd -> Bucktooth (+ Bucky)

* __BIOS__: Coreboot -> Libreboot
* __Boot Loader__: GRUB 2 -> GRUB Legacy -> SYSLINUX -> LILO (or ELILO for UEFI)
* __Service Manager__: SysVinit + bum -> SysVinit + OpenRC -> sinit (+ daemontools-encore or perp)
* __IPC__: DBus -> ipcs


## ANDROID APPS

* __Launcher__: Silverfish
* __Facebook__: Tinfoil for Facebook
* __Twitter__*: Tinfoil for Twitter
* __YouTube__: NewPipe
* __E-Books__: Document Viewer
* __Notes__: miniNoteViewer

All apps are from F-Droid, may not be much but is a start.
