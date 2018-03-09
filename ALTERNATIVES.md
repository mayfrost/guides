The list is built pointing to software that have alternatives with less dependencies, and addressing dependencies was the easy thing to do. One thing tho, some particular tools were included because they add less dependencies overall while keeping a system functional. One such example is imagemagick and ffmpeg, by which you can do a lot of work and replace many tools by just using those with scripts and replace something like a screenshot utility. TL;DR is about the unix principle and you can have a fully functional system pretty damn minimal with that.

Certainly it would be great to have a comparative on resource usage tho. Wanna help?

Terminal Pager: less -> most

Chat Client: Pidgin -> Finch (+ irssi mode) -> Centerim -> Bitlbee
E-Mail Client: Thunderbird -> Alpine -> Mutt
RSS Feed and Podcast: Liferea -> Newsbeuter -> Newsboat
IRC Client: HexChat -> Weechat -> Irssi
VoIP: Skype -> Mumble -> Linphone -> sscall

Application Launcher: GNOME Do -> ratmenu -> dmenu -> pdmenu -> slmenu
Compositing Window Manager: Compiz -> Compton -> Xcompmgr
Display Color Temperature: flux -> Redshift -> sct
Graphical Settings: Wpgtk -> LxAppearance -> GSettings -> xsettings
Keybinding: Xbindkeys -> sxhkd -> loadkeys (+ keymaps)
Wallpaper Changer: FEH -> hsetroot -> xsetroot -> imagemagick (but use 10MB more RAM than the others)

CD-DVD Burn and Copy: K3b -> Brasero -> cdw
Device Management: Udisks (+ udevil) -> pmount -> bashmount

Virtual Machine: VirtualBox -> AQEMU + kvm -> Qemu + kvm

Batch Renamer: GPRename -> qmv (renameutils)
Duplicate Files Removal: dupeGuru -> Fdupes
File Archiver: PeaZip -> Xarchiver -> Atool
File Manager: SpaceFM -> Ranger -> Midnight Commander -> noice

File Scraper: JDownloader -> youtube-dl -> cclive -> Plowshare
FTP Client: FileZilla -> lftp
Torrent Client: qBittorrent -> RTorrent -> transmission-daemon (+ transmission-remote-cli, or use the web interface that comes with transmission-daemon)

System Information: zCI -> screenfetch -> inxi
Disk Usage: QDirStat -> Baobab -> Ncdu -> df
System Monitor: gnome-system-monitor -> Conky -> htop -> nmon -> top

Multiple Streams: pulseaudio -> apulse
Audio Editing: Audacity -> SoX
Audio Mixer and Equalizer: pavucontrol -> Qastools -> alsa-utils + Alsaequal
Metadata: Easytag -> Beets -> ExifTool
Screenshots: Shutter -> scrot -> maim -> ImageMagick
Screencasting: Open Broadcaster Studio -> SimpleScreenRecorder -> FFmpeg
Video Transcoding: HandBrake -> WinFF -> FFmpeg

DNS Resolution: Unbound + NDS -> BIND9
Network Manager: Wicd -> NetworkManager -> ConnMan -> SetNet

Ebook Viewer: Calibre -> Zathura
Printers: CUPS -> LPR
Word Processor: Libreoffice Writter -> Abiword -> WordGrinder + pandoc
Spreadsheets: Libreoffice Calc -> Gnumeric -> SC-IM + pandoc
Text Editor (and IDE): Emacs (nox) -> Vim -> Nano -> Vile -> xwpe -> GNU Zile

Disk Cleaner: BleachBit -> bleachbit_cli -> shred
Storage Encryption: VeraCrypt -> tcplay (TrueCrypt implementation) -> Keyringer -> Tomb
Password Manager: KeePassX -> kpcli / pass (+ pass-tomb)

Version Control: Git (+ tig) -> Fossil -> RCS

Configuration Management: Puppet -> CFEngine -> cdist

CAD: AutoCAD -> FreeCAD -> OpenSCAD
Graphing Calculator: KAlgebra -> GraphMonkey -> Maxima + PLplot

Firewall: gufw -> ufw -> iptables -> nftables

Cloud: Nextcloud -> vsftpd -> sftp
E-Mail Filtering (LDA): Dovecot -> procmail
E-Mail Server (MTA): Postfix -> Exim -> cmail
E-Mail Spam Filter: DSPAM -> SpamAssassin
VPN: OpenVPN -> WireGuard
Web Caching: Decentraleyes on a web browser -> Squid
Web Filtering: Ad blocker on a web browser -> Pi-hole -> Privoxy
Web Server: Apache -> Nginx -> lighttpd -> darkhttpd -> Bucktooth (+ Bucky)

BIOS: Coreboot -> Libreboot
Boot Loader: GRUB 2 -> GRUB Legacy -> SYSLINUX -> LILO (or ELILO for UEFI)
Service Manager: SysVinit + bum -> SysVinit + OpenRC -> sinit (+ daemontools-encore or perp)
IPC: DBus -> ipcs
