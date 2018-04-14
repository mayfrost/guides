# ALTERNATIVES TO BLOATWARE

The list is built pointing to software that have alternatives with less dependencies, and addressing dependencies was the easy thing to do. One thing tho, some particular tools were included because they add less dependencies overall while keeping a system functional. One such example is imagemagick and ffmpeg, by which you can do a lot of work and replace many tools by just using those with scripts and replace something like a screenshot utility. TL;DR is about the unix principle and you can have a fully functional system pretty damn minimal with that.

Certainly it would be great to have a comparative on resource usage tho. Wanna help?


## TOC
1. [ANDROID APPS](#android-apps)  
2. [Command Line](#command-line)  
3. [Communication](#communication)  
3.1. [Desktop Client](#desktop-client)  
4. [Decentralized Networking](#decentralized-networking)  
5. [Desktop](#desktop)  
6. [Disk Tools](#disk-tools)  
7. [Emulation And Virtualization](#emulation-and-virtualization)  
8. [Enterprise](#enterprise)  
9. [File Utilities](#file-utilities)  
10. [Filesharing](#filesharing)  
11. [Forensics](#forensics)  
12. [Monitoring](#monitoring)  
12.1. [Benchmarking](#benchmarking)  
12.2. [System Information](#system-information)  
12.3. [System Monitoring](#system-monitoring)  
13. [Multimedia](#multimedia)  
13.1. [ASCii Art](#ascii-art)  
13.2. [Audio](#audio)  
13.3. [Image](#image)  
13.4. [Metadata](#metadata)  
13.5. [Video](#video)  
14. [Network Setup](#network-setup)  
15. [Office](#office)  
16. [Package Management](#package-management)  
17. [Pentesting](#pentesting)  
17.1. [Exploitables](#exploitables)  
17.2. [Network Scanner](#network-scanner)  
17.3. [Network Tampering](#network-tampering)  
17.4. [Password Cracking](#password-cracking)  
17.5. [Vulnerability Scanner](#vulnerability-scanner)  
18. [Privacy](#privacy)  
19. [Programming](#programming)  
20. [Remote Access](#remote-access)  
21. [Science And Engineering](#science-and-engineering)  
22. [Security](#security)  
22.1. [Containment](#containment)  
22.2. [Honeypots](#honeypots)  
22.3. [Host Intrusion](#host-intrusion)  
22.4. [Network Intrusion](#network-intrusion)  
23. [Server](#server)  
23.1. [Server Authentication](#server-authentication)  
24. [System Tools](#system-tools)  


## ANDROID APPS

* __Launcher__: Silverfish -> [KISS](http://kisslauncher.com/)
* __Facebook__: Tinfoil for Facebook
* __Twitter__: Tinfoil for Twitter
* __YouTube__: NewPipe
* __E-Books__: Document Viewer
* __Notes__: miniNoteViewer

All apps are from F-Droid, may not be much but is a start.

## Command Line
* __Command Line Cheatsheet__: [CLI Companion](https://launchpad.net/clicompanion) -> xman -> cheat / howdoi / clf / fu / bro -> [cheat.sh](https://github.com/chubin/cheat.sh)
* __Directory Browsing__: [fasd](https://github.com/clvv/fasd), [xd](https://github.com/fbb-git/xd), [fzy](https://github.com/jhawthorn/fzy)
* __Framebuffer Environment__: [Fbterm](https://code.google.com/archive/p/fbterm/) -> [yaft (because sixel)](https://github.com/uobikiemukot/yaft) -> [hterm (because regis)](https://github.com/new299/hackterm)
* __Hacker Culture__: ddate, fortune, The Hacker Test, The Jargon File
* __Multiplexer__: Tmux  -> Byobu -> GNU Screen (+[sixel patch](https://gist.github.com/saitoha/7546579))
* __Progress Viewers__: [progress](https://github.com/Xfennec/progress) -> [pv - Pipe Viewer](https://github.com/icetee/pv) -> [Advanced Copy](https://github.com/atdt/advcpmv)
* __Scripting__: [GNU Parallel](https://www.gnu.org/software/parallel/) (+ [GNU SQL](https://www.gnu.org/software/parallel/sql.html)), [empty](https://github.com/ierton/empty)
* __Shells__: Bash -> mksh -> [PC-DCL](https://github.com/MichelValentin/PC-DCL) -> [rc](https://github.com/rakitzis/rc)
* __Terminal Colorizer__: colout -> lolcat
* __Terminal Dropdown__: [tdrop](https://github.com/noctuid/tdrop) -> [YeahConsole](https://github.com/rduplain/yeahconsole), [alwaysontop](https://github.com/swirepe/alwaysontop)
* __Terminal Emulator__: PuTTY -> Terminology -> rxvt-unicode (a.k.a. urxvt) -> Termite -> UXTerm -> [Qodem](http://qodem.sourceforge.net/)
* __Terminal Pager__: less -> [most](http://www.jedsoft.org/most/)
* __Terminal Screensaver__: [bb](http://aa-project.sourceforge.net/bb/), [sl](https://github.com/mtoyoda/sl), cowsay (or cowthink), [tty-clock](https://github.com/xorg62/tty-clock), [NCMatrix](https://inconsolation.wordpress.com/2014/02/01/ncmatrix-the-original-with-a-twist/) / [terminal-screensaver](https://github.com/xiongchiamiov/terminal-screensaver), [Asciiquarium](https://github.com/cmatsuoka/asciiquarium), [rice](https://github.com/janbrennen/rice), [rickrollrc](https://github.com/keroserene/rickrollrc), [nyan.sh](https://gist.github.com/wting/5278321)

## Communication
* __BBS-MUD Client__: [TinTin++](http://tintin.sourceforge.net/features.php)
* __Bookmark Manager__: [bookmarks.public](https://github.com/skx/bookmarks.public) -> [bk_edit](http://www.vakuumverpackt.de/retiredprojects/bk_edit/) -> [b.](https://directory.fsf.org/wiki/B.)
* __Browser__: Pale Moon / Icecat -> luakit / vimb / surf (tabbed) / Uzbl (tabbed) -> [NetSurf](http://www.netsurf-browser.org/) -> Lynx -> [Links2](http://links.twibright.com/) -> [Netrik](http://netrik.sourceforge.net/) -> [Stallman.js](https://github.com/isdampe/Stallman.js/tree/master)
* __Browser (Gopher)__: [GopherVR](http://www.floodgap.com/software/gophervr/) -> [gopherfs](http://git.savannah.gnu.org/cgit/hurd/incubator.git/) -> [UMN Gopher client](https://github.com/jgoerzen/gopher) -> Lynx
* __Chat Client__: [Finch (Pidgin)](https://developer.pidgin.im/wiki/Using%20Finch) in [irssi mode](https://askubuntu.com/questions/442345/how-can-i-simplify-the-finch-interface) -> [Centerim](http://www.centerim.org/index.php/Main_Page) -> [Bitlbee](https://wiki.bitlbee.org/)
* __E-Mail Archiver__: [Lurker](http://lurker.sourceforge.net/)
* __E-Mail Client__: Thunderbird -> [SquirrelMail](http://www.squirrelmail.org/) -> Alpine -> Mutt -> [mailx](http://heirloom.sourceforge.net/mailx.html)
* __E-Mail Fetcher__: [Fetchmail](http://www.fetchmail.info/) -> [isync (mbsync)](http://isync.sourceforge.net/)
* __IRC Client__: HexChat -> Weechat -> Irssi
* __Online Radio__: [Nuvola Player](https://tiliado.eu/nuvolaplayer/)
* __RSS Feed and Podcast__: Liferea -> Newsbeuter -> Newsboat
* __Search Engine Scraper__: Googler -> [Surfraw](http://surfraw.alioth.debian.org/) (+ [dmenu](https://bbs.archlinux.org/viewtopic.php?id=228706))
* __Usenet Client (Newsreader)__: Pan -> [slrn](http://www.slrn.org/) ( + slrnpull + slrnface)
* __VoIP Client__: [Jitsi](https://jitsi.org/) -> [Finch (Pidgin)](https://developer.pidgin.im/wiki/vv)

### Desktop Client
* __4chan__: [ANSIchan](https://github.com/qqueue/ANSICHAN) / [yottu](https://github.com/yottu/yottu)
* __Booru__: [ahoviewer](https://github.com/ahodesuka/ahoviewer)
* __Facebook__: [FBCLI](https://github.com/danielduan/FBCLI) / [Facebook CLI](https://github.com/specious/facebook-cli)
* __General__: [Rambox](https://github.com/saenzramiro/rambox) / [Gwibber](http://gwibber.com/)
* __Google Drive__: [Grive2](https://github.com/vitalif/grive2)
* __Pastebin__: [pastebinit](https://github.com/skorokithakis/pastebinit)
* __Reddit__: [cReddit](https://github.com/Cotix/cReddit)
* __Slack__: [ScudCloud](https://github.com/raelgc/scudcloud) / [slackterm](https://github.com/rob05c/slackterm)
* __Twitter__: [Hotot](https://github.com/lyricat/Hotot) / [turses](https://github.com/louipc/turses)
* __Youtube__: [youtube-viewer](https://github.com/trizen/youtube-viewer)

## Decentralized Networking
* __Chat__: Tox -> Matrix (Matrix-Ircd, Riot) -> GNU Ring -> [nircd](https://github.com/Ronsor/nircd)
* __Darknet__: [autovpn](https://github.com/adtac/autovpn) -> Tor -> [AnoNet](http://anonet.org/) -> i2p
* __Digital Library__: [Aletheia](https://github.com/aletheia-foundation/aletheia-admin)
* __Distributed File Systems__: Samba -> NFS -> IPFS -> [GNUnet](https://gnunet.org/)
* __DNS Resolution__:  [OpenNIC](https://www.opennic.org/) -> [Namecoin](https://namecoin.org/) -> [KadNode](https://github.com/mwarning/KadNode)
* __E-Commerce__: [FIX Agora](http://fixagora.sourceforge.net/) + [OpenBazaar](https://github.com/OpenBazaar) + [Bitnation](https://github.com/Bit-Nation) + [GNU Taler](https://taler.net/en/)
* __Forum__: [Decentraland](https://decentraland.org/) -> [Mastodon (GNU Social)](https://joinmastodon.org/) -> [NNTPChan](https://github.com/majestrate/nntpchan)
* __Gossip Network (Network Service Discovery)__: [peernet](https://github.com/substack/peernet)
* __Grid Computing__: [BOINC](https://github.com/BOINC/boinc) (+ [boinctui](https://github.com/suleman1971/boinctui))
* __Media Sharing__: MediaGoblin -> PeerTube (WebTorrent) -> DTube -> [Alexandria](http://www.alexandria.io/) (watch [this video](https://www.youtube.com/watch?v=So4n2ZBSMxg) on how Alexandria works)
* __Mesh Network__: Tinc -> cjdns -> open80211s (802.11s) -> [B.A.T.M.A.N.](https://www.open-mesh.org/projects/open-mesh/wiki)
* __Monetary Incentives__: [Storj](https://storj.io/) + [Gridcoin](https://gridcoin.us/) + [Stream Token](https://streamtoken.net/)
* __Search Engine__: searx -> [Seeks](https://beniz.github.io/seeks/) -> [YaCy](https://www.yacy.net/en/) (truly decentralized, would be wonderful if searx/seeks could feed its data to YaCy)
* __Search Engine (Gopher)__: [Jugtail](http://www.nongnu.org/jugtail/)
* __Search Engine (Torrents)__: Magnetissimo -> [magnetico](https://github.com/boramalper/magnetico)
* __Streaming__: [Butter Project](http://butterproject.org/) -> [Livepeer](https://livepeer.org/) -> [BasicTV](https://github.com/dako300/basictv)
* __Version Control (Decentralized Github)__: [GitTorrent](https://github.com/mfyuce/GitTorrent)
* __VPN__:  [PeerVPN](https://github.com/peervpn/peervpn)
* __Wiki__: [ikiwiki](https://ikiwiki.info/tips/distributed_wikis/)

## Desktop
* __Application Launcher__: rofi -> ratmenu -> [dmenu](https://github.com/stilvoid/dmenu) -> [pdmenu](https://joeyh.name/code/pdmenu/) -> [iSelect](http://www.ossp.org/pkg/tool/iselect/) -> [slmenu](https://bitbucket.org/rafaelgg/slmenu)
* __Boot Screen__: Plymouth -> Splashy -> Fbsplash -> \<BOOTLOADERS>
* __Clipboard__: [CopyQ](https://github.com/hluk/CopyQ) -> [clipmenu](https://github.com/kaihendry/clipmenu) -> [snippy](https://github.com/gotbletu/shownotes/blob/master/snippy.sh) -> xclip / XSel
* __Compositing Window Manager__: Compiz -> Compton -> Xcompmgr
* __Cursor__: [keynav](https://github.com/jordansissel/keynav), GPM
* __Desktop Character__: [Kawari](https://sourceforge.net/projects/kawari/) + [Ninix-aya](https://directory.fsf.org/wiki/Ninix-aya) (for [Ukagaka](https://en.wikipedia.org/wiki/Ukagaka)) -> [Gnome KiSS](http://devel.tlrmx.org/kiss/) -> [Oneko](http://www.daidouji.com/oneko/) -> [xevilteddy](https://github.com/mjg59/xevilteddy) -> [Xteddy](https://xteddy.org/)
* __Display Color Temperature__: Redshift -> [sct](https://github.com/mgudemann/sct)
* __Display Settings__: DDCcontrol, xrandr
* __Graphical Settings__: [Wpgtk](https://deviantfero.github.io/wpgtk/) -> LxAppearance -> GSettings -> xsettings
* __Keybinding__: Xbindkeys -> sxhkd -> loadkeys (+ keymaps)
* __Keyboard Layout__: XKB -> xmodmap -> loadkeys (+ keymaps)
* __Login Manager__: SLiM -> [Qingy](http://qingy.sourceforge.net/)
* __Macro Recorder__: [Autokey](https://github.com/autokey/autokey) -> [Sikuli](https://github.com/sikuli/sikuli) -> [Easystroke](https://github.com/thjaeger/easystroke) -> [xdotool](http://www.semicomplete.com/blog/projects/xdotool/) -> [GNU Xnee](https://www.gnu.org/software/xnee/) 
* __Nested Display__: Xephyr -> Xnest
* __Notification Daemon__: dunst -> [slstatus](https://github.com/drkhsh/slstatus)
* __Notification Server__: Libcanberra + Libnotify -> xmessage
* __Panel__: Avant Window Navigator -> Global Menu -> Tint2
* __Screensaver__: XScreenSaver -> XLockmore -> i3lock -> [sxlock](https://github.com/lahwaacz/sxlock) -> slock
* __Status Bar Client__: Dzen -> [bevelbar](https://github.com/vain/bevelbar) -> Lemonbar
* __Status Bar Server__: monky -> i3status
* __Animated Wallpaper Changer__: Xphoon, xfireworks, Xsnow, xmountains, Xplanet, ImageMagick (animate)
* __Still Wallpaper Changer__: FEH -> [hsetroot](https://github.com/elmiko/hsetroot) -> [imagemagick](https://imagemagick.org/discourse-server/viewtopic.php?t=16735) (but use 10MB more RAM than the others)
* __Terminal As Wallpaper__: [root-tail](http://oldhome.schmorp.de/marc/root-tail.html) -> [xrootconsole](http://silicone.homelinux.org/projects/xrootconsole/)
* __Video Wallpaper Changer__: mpv -> VLC (nvlc) -> MPlayer
* __Window Manager__: [FVWM](https://directory.fsf.org/wiki/Fvwm) (+ [FvwmTabs](http://fvwm.sourceforge.net/documentation/manpages/unstable/FvwmTabs.php) and [4dwm theme](https://github.com/tonnerre/fvwm/blob/master/sample.fvwmrc/4Dwm.fvwmrc)) -> IceWM -> i3 -> [s3d](http://s3d.sourceforge.net/) (+ s3dfm, it's a 3D desktop!) -> [Amiwm](https://www.lysator.liu.se/~marcus/amiwm.html) -> [MWM](https://github.com/stackfield/mwm) -> [Ratpoison](http://ratpoison.wxcvbn.org/cgi-bin/wiki.pl) -> dwm (+ dwmstatus) -> [FrankenWM](https://github.com/sulami/FrankenWM) -> [TinyWM](http://incise.org/tinywm.html) -> [Twin](https://github.com/cosmos72/twin) -> [VWM](http://vwm.sourceforge.net/)
* __Window Manipulation__: QuickTile -> wmctrl -> wmutils
* __Worskpace Pager__: [3D-Desktop](http://desk3d.sourceforge.net/) -> [Skippy-XD](https://github.com/richardgv/skippy-xd)
* __X Event Display__: xprop -> xwininfo -> xev

## Disk Tools
* __CD-DVD Burn and Copy (Backends)__: cdrtools -> cdrkit -> [cdrskin](https://dev.lovelyhq.com/libburnia/web/wikis/cdrskin)
* __CD-DVD Burn and Copy (Frontends)__: K3b -> Brasero -> [cdw](http://cdw.sourceforge.net/)
* __CD-DVD Ripping__: Sound Juicer -> fre ac -> [cdparanoia](https://www.xiph.org/paranoia/) (+ [ABCDE](http://lly.org/~rcw/abcde/page/))
* __Custom Install CD__: Respin -> Remastersys -> Distroshare -> PinguyBuilder -> Customizer -> Ubuntu Customization Kit -> Mklivecd
* __Device Management__: Udisks (+ udevil) -> pmount -> [bashmount](https://github.com/jamielinux/bashmount/blob/master/INSTALL)
* __Disk Cloning and Writing__: dd -> dcfldd -> [dc3dd](https://sourceforge.net/projects/dc3dd/)
* __Live USB__: UNetbootin -> [MultiCD](https://multicd.us/)
* __Partitioning__: Gparted -> cfdisk -> GNU Parted -> fdisk / sfdisk
* __System Backup__: [Systemback](https://sourceforge.net/projects/systemback/) -> [Bacula](https://blog.bacula.org/) -> [FSArchiver](http://www.fsarchiver.org/) -> [CYA](https://www.cyberws.com/bash/cya/)

## Emulation And Virtualization
* __Containers__: chroot -> LXC -> [Linux-VServer](http://linux-vserver.org/Welcome_to_Linux-VServer.org)
* __Emulators__: Windows: Wine (+ [Wine Staging](https://github.com/wine-compholio/wine-staging)), Android: [Anbox](https://github.com/anbox/anbox), OS X: [Darling](https://www.darlinghq.org/), Atari: [Hatari](http://hatari.tuxfamily.org/), Commodore: [VICE](http://vice-emu.sourceforge.net/), DOS: DOSBox
* __Hypervisors__: Xen -> [NOVA](http://hypervisor.org/) -> KVM
* __Network Virtualization__: GNS3 -> [nsnam](https://github.com/nsnam/ns-3-dev-git)
* __Software Compatibility__: .NET: DotGNU -> Mono, Systemd/Linux: [systemd-shim](https://directory.fsf.org/wiki/Systemd-shim)
* __Video Game Console Emulation (ATARI)__: [Stella](https://stella-emu.github.io/)
* __Video Game Console Emulation (XBOX)__: [XQEMU](https://github.com/espes/xqemu)
* __Video Game Console Emulation (MULTI)__: Higan -> Mednafen -> RetroArch -> [MAME](https://github.com/mamedev/mame) -> [AdvanceMAME](https://github.com/amadvance/advancemame) [(framebuffer support)](https://forum.odroid.com/viewtopic.php?f=116&t=11662)
* __Video Game Console Emulation (NINTENDO)__: [DeSmuME (Nintendo DS)](https://github.com/TASVideos/desmume/), [Mupen64Plus (Nintendo 64)](https://github.com/mupen64plus/mupen64plus-core), [Dolphin (GameCube and Wii)](https://dolphin-emu.org/)
* __Video Game Console Emulation (SEGA)__: [Yabause (Sega Saturn)](https://github.com/Yabause/yabause), [Reicast (Dreamcast)](https://github.com/reicast/reicast-emulator)
* __Video Game Console Emulation (PLAYSTATION)__: [PPSSPP](https://github.com/hrydgard/ppsspp), [RPCS3](https://github.com/rpcs3/rpcs3/), [PCSX2](https://github.com/PCSX2/pcsx2)
* __Virtual Assembler__: [GNUSim8085](http://pages.cs.wisc.edu/~larus/spim.html), [spim](http://pages.cs.wisc.edu/~larus/spim.html)
* __Virtual Machine__: VirtualBox -> [AQEMU](https://github.com/tobimensch/aqemu) + kvm -> Qemu + kvm
* __Virtual Machine (IBM Mainframes)__: [Hercules](http://www.hercules-390.org/)
* __Virtual Machine (DEC)__: [SIMH](http://simh.trailing-edge.com/)

## Enterprise
* __Data Mining and Business Intelligence__: [JasperReports](https://sourceforge.net/projects/jasperserver/) -> [KNIME](https://directory.fsf.org/wiki/KNIME) -> [GNU Ferret](https://directory.fsf.org/wiki/Ferret) -> [GURGLE](https://directory.fsf.org/wiki/Gurgle)
* __Database (Datalog)__: [Datalog Educational System](http://des.sourceforge.net/), [Datalog](http://datalog.sourceforge.net/)
* __Database (Middleware)__: [Virtuoso Universal Server](https://virtuoso.openlinksw.com/) -> [Orbada](http://orbada.sourceforge.net/html/www_orbada_doc.html) -> [Autotable](https://directory.fsf.org/wiki/Autotable)
* __Database (NoSQL)__: [GZigZag](http://www.nongnu.org/gzz/), [RRDtool](https://oss.oetiker.ch/rrdtool/), [Redis](https://directory.fsf.org/wiki/Redis), [GNU Recutils](https://directory.fsf.org/wiki/Recutils)
* __Database (SQL)__: MySQL -> Percona -> [MariaDB](https://directory.fsf.org/wiki/MariaDB) -> [CUBRID](https://github.com/CUBRID/cubrid) -> [Ingres II](https://github.com/fosslc/Ingres)
* __Enterprise Resource Planning (ERP)__: [IDempiere](http://www.idempiere.org/) -> [LedgerSMB](https://directory.fsf.org/wiki/LedgerSMB) -> [SQL-Ledger](http://www.sql-ledger.com/)
* __Expert System__: [Flora-2](http://flora.sourceforge.net/), [CLIPS](http://clipsrules.sourceforge.net/)
* __Financial Markets Monitoring__: [JStock](https://github.com/yccheok/jstock) -> [QtTrader](https://github.com/e99majo/qttrader) -> [Qtstalker](http://qtstalker.sourceforge.net/)
* __Human Resource Management__: [OrangeHRM](https://github.com/turnkeylinux-apps/orangehrm)
* __Invoicing__: [Simple Invoices](https://github.com/simpleinvoices/simpleinvoices)
* __Project Management__: [GanttProject](http://www.ganttproject.biz/)

## File Utilities
* __Batch Renamer__: [GPRename](http://gprename.sourceforge.net/) -> [qmv (renameutils)](http://www.nongnu.org/renameutils/)
* __Duplicate Files Removal__: [dupeGuru](https://github.com/hsoft/dupeguru) -> [Fdupes](https://github.com/adrianlopezroche/fdupes)
* __File Archiver__: PeaZip -> Xarchiver -> [Atool](http://www.nongnu.org/atool/)
* __File Manager__: SpaceFM -> [Moxfm](https://github.com/ThomasAdam/moxfm) -> [File System Visualizer](https://github.com/mcuelenaere/fsv) ([“It’s a Unix system, I know this!”](https://www.youtube.com/watch?v=dxIPcbmo1_U)) -> Midnight Commander -> [vifm](https://wiki.vifm.info/index.php?title=How_to_preview_images) -> [FDclone](http://hp.vector.co.jp/authors/VA012337/soft/fd/) -> [Ytree](https://directory.fsf.org/wiki/Ytree) -> [nnn](https://github.com/jarun/nnn) -> [tree](https://directory.fsf.org/wiki/Tree)
* __File Search__: [DocFetcher](http://docfetcher.sourceforge.net/en/index.html) -> [ANGRYsearch](https://github.com/DoTheEvo/ANGRYsearch) -> [Puggle](http://puggle.sourceforge.net/) -> [regain](http://regain.sourceforge.net/index.php) -> find
* __File Synchronization__: [Unison](https://github.com/bcpierce00/unison) -> [git-annex](https://git-annex.branchable.com/) -> Rsync
* __Image Organizer__: hydrus network -> Shotwell -> GTKRawGallery -> digiKam -> gThumb (+ gphoto) -> [Mapivi](http://mapivi.sourceforge.net/mapivi.shtml) -> [BASH-Booru](https://github.com/ChristianSilvermoon/BASH-Booru)
* __RegEx Builder__: [regexxer](https://directory.fsf.org/wiki/Regexxer) -> [Visual REGEXP](http://laurent.riesterer.free.fr/regexp/) -> [txt2regex](https://github.com/aureliojargas/txt2regex)

## Filesharing
* __Direct Connect__: LinuxDC++ -> [ncdc](https://github.com/srijan/ncdc) -> [microdc2](http://corsair626.no-ip.org/microdc/)
* __Download Manager__: [giFT](https://sourceforge.net/projects/gift/) (+ [giFTcurs](http://www.nongnu.org/giftcurs/)) -> [aria2](https://aria2.github.io/) -> cURL -> Wget
* __File Scraper__: megatools -> [JDownloader](https://github.com/Bobmk/JDownloader) -> [Plowshare](https://github.com/mcrapet/plowshare)
* __FTP Client__: FileZilla -> [lftp](https://github.com/lavv17/lftp)
* __LAN Sharing__: NitroShare -> Dukto
* __Media Center__: Plex -> Emby -> Popcorn Time -> Kodi ("XBMC", + Sonarr)
* __Media Miner__: FlexGet -> [Sonarr](https://github.com/Sonarr/Sonarr)
* __Offline Reader__: [Kiwix](http://www.kiwix.org/) -> Darcy Ripper -> HTTrack -> Wget
* __Soulseek__: Nicotine Plus -> [Museek (mucous)](https://museek-plus.org/)
* __Stream Catcher__: Streamripper -> youtube-dl -> [cclive](https://github.com/legatvs/cclive) -> [youtube-pl](http://ronja.twibright.com/youtube-pl.php) -> [quvi](https://github.com/mogaal/quvi), [RTMPDump](https://github.com/mstorsjo/rtmpdump)
* __Torrent Client__: qBittorrent -> RTorrent -> transmission-daemon (comes with a [web interface](https://github.com/transmission/transmission/wiki/Web-Interface) by default but [other frontends](https://github.com/fagga/transmission-remote-cli) exist)
* __Torrent Tracker Scraper__: [Torrtux](https://github.com/l333k0/torrtux) -> [Torrench](https://github.com/kryptxy/torrench) -> [Jackett](https://github.com/Jackett/Jackett)
* __Usenet (File Grabber)__: LottaNZB -> SABnzbd -> [NZBGet](https://github.com/nzbget/nzbget) -> [nzb](https://directory.fsf.org/wiki/Nzb) -> [nzbperl](https://github.com/eghm/nzbperl)

## Forensics
* __Application Profiling__: Valgrind (+ Callgrind)
* __Data Recovery__: dvdisaster -> ddrescue -> TestDisk (PhotoRec)
* __Debugger__: DDD -> [CGDB](https://cgdb.github.io/) -> GDB
* __Virtual Memory Debugger__: scanmem & Gameconqueror -> [varedit](https://github.com/asherlie/varedit)
* __Java Debugger__: VisualVM
* __Browser Debugger__: Firebug
* __Forensic Analysis Framework__: The Sleuth Kit -> DFF -> Radare
* __Hex Editors__: [HT Editor](http://hte.sourceforge.net/) -> [dhex](https://directory.fsf.org/wiki/DHEX)
* __Sandbox__: [Cuckoo Sandbox](https://cuckoosandbox.org/)
* __Steganalysis__: [Virtual Steganographic Laboratory](http://vsl.sourceforge.net/) -> [Stegdetect](https://github.com/abeluck/stegdetect)

## Monitoring
### Benchmarking
* __Drive Profiling__: hdparm -> Smartmontools
* __Filesystem Benchmark__: [Bonnie++](https://www.coker.com.au/bonnie++/) -> [MBW](https://github.com/raas/mbw)
* __General Benchmarking__: [HPC Challenge Benchmark (hpcc)](http://icl.cs.utk.edu/hpcc/) -> [Sysbench](https://github.com/akopytov/sysbench)
* __Network Profiling__: [iperf](http://software.es.net/iperf/)
* __Power Management__: tpfancontrol -> thinkfan -> [apcupsd](http://www.apcupsd.org/) -> [TLP](https://github.com/linrunner/TLP) -> [PowerTOP](https://github.com/fenrus75/powertop) -> [Powertweak](https://directory.fsf.org/wiki/Powertweak-Linux)
* __Server Benchmark__: [Siege](https://github.com/JoeDog/siege)
* __System Tracing__: [strace](https://github.com/strace/strace) -> [trace-cmd](https://git.kernel.org/pub/scm/linux/kernel/git/rostedt/trace-cmd.git) (ftrace) -> perf
* __Undevolting and Power Saving__: [TurionPowerControl](https://code.google.com/archive/p/turionpowercontrol/) / [Linux-PHC](http://www.linux-phc.org/forum/) -> [cpufrequtils](https://mirrors.edge.kernel.org/pub/linux/utils/kernel/cpufreq/) -> [cpupower](https://github.com/torvalds/linux/tree/master/tools/power/cpupower)

### System Information
* __General Information__: [inxi](https://smxi.org/docs/inxi.htm)
* __Screenshot Information__: [Linux_Logo](https://github.com/KittyKatt/screenFetch) -> [Neofetch](https://github.com/dylanaraps/neofetch) -> [screenFetch](https://github.com/KittyKatt/screenFetch)
* __Hardware Information__: blkid -> lsblk -> [lspci](http://mj.ucw.cz/sw/pciutils/) -> [lshw](https://github.com/lyonel/lshw) -> [hwloc](https://www.open-mpi.org/projects/hwloc/) -> dmesg -> [dmidecode](http://dmidecode.nongnu.org/)
* __Software Information__: file -> ldd -> [vrms](https://vrms.alioth.debian.org/) -> lsb_release -> uname

### System Monitoring
* __Database Monitoring__: [Mytop](https://github.com/jzawodn/mytop)
* __Disk Usage__: QDirStat -> [Baobab](http://www.marzocca.net/linux/baobab/) -> xdiskusage -> XDU -> [Ncdu](https://dev.yorhel.nl/ncdu) -> df
* __Geolocation__: [Prey](https://github.com/prey/prey-bash-client)
* __Hardware Monitoring__: acpiclient -> Hddtemp -> lm-sensors (psensor for a GUI)
* __Log Monitoring__: lnav -> [Logcheck](http://logcheck.org/) -> [multiTail](https://github.com/flok99/multitail)
* __Log Visualizer__: glTail -> [Logstalgia](https://github.com/acaudwell/Logstalgia)
* __Network Flow__: Argos -> HFlow -> [nfdump](https://github.com/phaag/nfdump) ([nfsen](http://nfsen.sourceforge.net/))
* __Network Latency__: [SmokePing](https://github.com/oetiker/SmokePing) -> [bmon](https://github.com/tgraf/bmon)
* __Network Monitoring__: [iftop](http://www.ex-parrot.com/pdw/iftop/), [NetHogs](https://github.com/raboof/nethogs), [vnStat](https://github.com/vergoh/vnstat)
* __Port Monitoring__: [psad](https://directory.fsf.org/wiki/Port_Scan_Attack_Detector)
* __Process Monitoring__: [svsh](https://ido50.github.io/Svsh/), [lsof](https://people.freebsd.org/~abe/), [PSmisc](https://directory.fsf.org/wiki/Psmisc), fuser
* __Serial Monitoring__: [ttylog](https://github.com/rocasa/ttylog) -> [slsnif](https://github.com/aeruder/slsnif)
* __System Latency__: [LatencyTOP](https://github.com/namhyung/latencytop)
* __System Monitor__: gnome-system-monitor -> [psDooM](https://github.com/keymon/psdoom-ng) -> Conky -> htop -> [nmon](http://nmon.sourceforge.net/pmwiki.php) -> [Sysstat](https://directory.fsf.org/wiki/Sysstat) (sar, mpstat, pidstat, iostat, sadf) -> [procps](https://directory.fsf.org/wiki/Procps) (ps, free, vmstat, top, pmap, nice)
* __User Monitoring__: [wuzzah](https://www.cs.swarthmore.edu/~finney/proj/wuzzah/) -> [Whowatch](https://github.com/mtsuszycki/whowatch/) -> [acct](http://savannah.gnu.org/projects/acct/)
* __Web Log Analytics__: [AWStats](http://www.awstats.org/) -> [W3Perl](http://www.w3perl.com/) -> [Analog](http://www.web42.com/analog/) -> [pmacct](https://github.com/pmacct/pmacct)
* __Web State Monitor__: Nagios (+ NagVis) -> [sysmon](https://web.archive.org/web/20070602050243/http://pubpages.unh.edu/~pas/hacks/sysmon/)

## Multimedia
### ASCii Art
* __ANSI Drawing__: [cadubi](https://github.com/statico/cadubi) -> [SHPaint](http://bruxy.regnet.cz/web/linux/EN/ansi-art-sh-paint/) -> [MysticDraw](https://archive.org/details/tucows_8499_Mystic_Draw)
* __ANSi Viewer__: [ANSiMat](https://sourceforge.net/projects/ansimat/)
* __ASCii Animation__: blessed -> Durdraw -> drawille
* __ASCii Banner__: shellpic -> TOIlet -> FIGlet -> sysvbanner
* __ASCii Drawing__: JavE -> textdraw -> Aewan
* __ASCii Presentations__: wopr -> blessed-contrib
* __Image to ASCii__: jp2a
* __Video to ASCii__: libcaca -> AAlib

### Audio
* __Audio Editing__: Audacity -> [SoX](http://sox.sourceforge.net/)
* __Audio Effect Plugins__: [zam-plugins](http://www.zamaudio.com/?p=870) (LADSPA/LV2/VST/JACK), [LV2](http://lv2plug.in/) (x42-plugins), [LADSPA](http://ccrma.stanford.edu/planetccrma/software/ladspaworld.html) (tap-plugins), [DSSI](http://dssi.sourceforge.net/) (dssi-utils, dssi-vst)
* __Audio Encoding__: [LAME](http://lame.sourceforge.net/), [FLAC](https://xiph.org/flac/)
* __Background Sound__: GNU GTick -> Ambient Noise
* __Digital Audio Workstation__: Rosegarden -> Ardour -> LMMS
* __DJing__: Mixxx
* __Ear Training__: LenMus -> GNU Solfege
* __Multiple Audio Streams__: pulseaudio -> [apulse](https://github.com/i-rinat/apulse)
* __Music Player__: Audacious (+ [Winamp Classic skin](https://www.gnome-look.org/content/show.php/Winamp+Classic+skin+for+Audacious?content=135799) + GJay) -> [Open Cubic Player](http://stian.cubic.org/project-ocp.php) -> MPD (vimus/ncmpcpp) -> cmus -> [mp3blaster](http://www.mp3blaster.org/) (runs with "aoss mp3blaster" or compiled with ALSA) -> [MOC](http://moc.daper.net/) (+ moc-ffmpeg-plugin, [dmenu_mocp](https://github.com/pscha/dmenu_mocp))
* __Music Visualization__: [Spectrum3d](http://spectrum3d.sourceforge.net/) -> [Le Biniou](https://directory.fsf.org/wiki/Lebiniou) -> [projectM](http://projectm.sourceforge.net/) -> [cli-visualizer](https://github.com/dpayne/cli-visualizer)
* __Scorewriter__: MuseScore -> LilyPond
* __Software Sampler__: LinuxSampler -> orDrumbox -> [Hydrogen](http://www.hydrogen-music.org/hcms/)
* __Synthesizer__: AlsaModularSynth -> [ZynAddSubFX](http://zynaddsubfx.sourceforge.net/)
* __System Sound Extensions__: [WineASIO](https://sourceforge.net/projects/wineasio/), alsa-oss/oss-compat, ESound (esound-common), awesfx
* __System Sound Utilities__: pavucontrol (pulseaudio) -> JAMin (for Jack) -> Qastools -> [alsa-utils](https://github.com/gittup/alsa-utils) + [Alsaequal](https://directory.fsf.org/wiki/Alsaequal)
* __Tonal Feature Analysis__: [CLAM Chordata](http://clam-project.org/)
* __Tracker Editors__: [Schism](https://github.com/schismtracker/schismtracker) -> [MilkyTracker](https://github.com/milkytracker/milkytracker)
* __Trackers__: [SID-Wizard](http://csdb.dk/release/?id=131846) -> [GoatTracker](https://sourceforge.net/projects/goattracker2/)
* __Tray Icon__: Volume Icon -> Volti

### Image
* __Bitmaps to Vector Conversion__: AutoTrace -> [Potrace](https://directory.fsf.org/wiki/Potrace)
* __Diagram Editor__: Pencil Project -> Dia -> Graphviz
* __Bitmap Graphics Digital Drawing__: Krita -> MyPaint -> [XPaint](https://directory.fsf.org/wiki/Xpaint) -> [GrafX2](http://grafx2.chez.com/) / [uberpaint](https://github.com/trapd00r/uberpaint)
* __Coloring Digital Drawing__: STYLE2PAINTS
* __Fonts Digital Drawing__: FontForge
* __Vector Digital Drawing__: Inkscape -> [Xfig](http://mcj.sourceforge.net/)
* __Image Editing__: RawTherapee -> darktable -> Gimp + [G'MIC](https://github.com/dtschump/gmic) -> ImageMagick (display, import)
* __Image Optimizing__: pngcrush -> pngquant -> OptiPNG
* __Image Viewer__: Feh -> sxiv -> display (ImageMagick) -> [fim](http://www.nongnu.org/fbi-improved/) / [fbi (fbida)](https://github.com/fcarlier/fbida)
* __Plotting__: Gnuplot -> [PLplot](http://plplot.sourceforge.net/)
* __Screenshots__: Shutter -> scrot -> maim -> import (ImageMagick) -> [fbcat](https://github.com/jwilk/fbcat) (FBGrab)

### Metadata
* __Metadata__: [Easytag](https://wiki.gnome.org/Apps/EasyTAG) -> [Beets](https://github.com/beetbox/beets) -> [ExifTool](http://exiftool.sourceforge.net/)

### Video
* __Compositing__: [CinePaint](http://www.cinepaint.org/) -> [Natron](https://github.com/MrKepzie/Natron)
* __Datamoshing__: [Autodatamosh](https://github.com/grampajoe/Autodatamosh)
* __2D Digital Animation__: [Synfig](https://www.synfig.org/) -> [OpenToonz](https://github.com/opentoonz/opentoonz)
* __3D Digital Animation__: Blender
* __Screencasting__: Open Broadcaster Studio -> SimpleScreenRecorder -> [FFmpeg](https://www.linuxquestions.org/questions/linux-general-1/record-using-framebuffer-video-grabber-4175464119/) -> [ttyrec](https://github.com/mjording/ttyrec) (+ [seq2gif](https://github.com/saitoha/seq2gif))
* __Video Editing__: Kdenlive -> Cinelerra-cv -> OpenShot -> FFmpeg
* __Video Player__: MPV -> nvlc (VLC) -> [MPlayer](https://mplayerhq.hu)
* __Video to gif__: Video2Gif -> convert (ImageMagick) -> FFmpeg
* __Video Transcoding__: [HandBrake](https://handbrake.fr/) -> WinFF -> FFmpeg

## Network Setup
* __Bandwidth Shaping__: [Wondershaper](http://lartc.org/wondershaper/)
* __Bandwidth Testing__: [speedtest-cli](https://github.com/sivel/speedtest-cli) / [speed-test](https://github.com/sindresorhus/speed-test)
* __DHCP Client__: dhclient -> dhcpcd
* __DNS Encryption__: DNSSEC, DNSCrypt
* __DNS Resolution__: Unbound + NDS -> BIND9
* __MAC Manipulation__: [GNU MAC Changer](https://github.com/alobbs/macchanger)
* __Network Encryption__: OpenSSL -> [LibreSSL](https://directory.fsf.org/wiki/Libressl) -> GnuTLS -> IPsec / [SAE](https://github.com/cozybit/authsae) (802.11s)
* __Network Manager__: Wicd -> NetworkManager -> ConnMan -> [SetNet](http://kalos.mine.nu/setnet/)
* __Networking Tools__: iproute2 (ip, ss) -> [net-tools](https://github.com/ecki/net-tools) (ifconfig, netstat)
* __Wireless Tools__: [Wireless Tools for Linux](https://hewlettpackard.github.io/wireless-tools/Tools.html), [wpa_supplicant](https://w1.fi/wpa_supplicant/)

## Office
* __CHM Viewer__: xCHM -> [CHMLib](http://www.jedrea.com/chmlib/) (extract_chmLib)
* __Desktop Publishing__: Scribus
* __Document Processor__: Emacs (AUCTeX) -> LyX -> [GNU TeXmacs](http://texmacs.org/tmweb/home/welcome.en.html)
* __Ebook Viewer__: Calibre -> Okular -> Zathura -> [fimgs (fim)](http://www.nongnu.org/fbi-improved/) / [fbgs (fbida)](https://www.kraxel.org/blog/linux/fbida/)
* __Flashcards__: Anki
* __Gamification__: HabitRPG -> Habitica
* __Input Method Editor__: iBus -> Fcitx -> SCIM
* __Mind Mapping__: FreeMind
* __Office Suites__: LibreOffice -> [Siag Office](http://siag.nu/) -> [catdoc](https://github.com/petewarden/catdoc) (xls2csv, catppt, wordview)
* __Offline Dictionary__: Goldendict -> Artha -> [Dico](https://directory.fsf.org/wiki/Dico), [dict](http://www.dict.org/w/software/software)
* __Outliner__: [TreeSheets](https://github.com/aardappel/treesheets) -> Vault 3 -> GJots2 -> Emacs (Org-mode) -> Vim (Vimoutliner or Vim-orgmode) -> [hnb](http://hnb.sourceforge.net/Screen-shots/) -> [snb](https://github.com/drbig/snb)
* __PDF Editing__: [PDF SaM](https://github.com/torakiki/pdfsam) -> Poppler
* __Personal Accounting__: GnuCash -> [GNU Pem](https://www.gnu.org/software/pem/)
* __Personal Assistant__: [Mycroft](https://mycroft.ai/), [betty](https://github.com/pickhardt/betty), [Climate](https://github.com/adtac/climate), [Suicide Linux](https://qntm.org/suicide)
* __Personal Organizer__: Wyrd -> [calcurse](https://directory.fsf.org/wiki/Calcurse) -> when -> cal
* __Presentation__: Beamer -> Sozi -> [Text Presentation Program](https://github.com/akrennmair/tpp)
* __Printers__: CUPS -> [LPR](http://www.lprng.com/)
* __Repetitive Strain Injury__: [Workrave](https://directory.fsf.org/wiki/Workrave)
* __Speed Reading__: [speedread](https://github.com/pasky/speedread)
* __Spell Check__: [Aspell](https://directory.fsf.org/wiki/Aspell)
* __Spreadsheets__: Libreoffice Calc -> Gnumeric -> Oleo -> [SC-IM](https://github.com/andmarti1424/sc-im) + Pandoc
* __Text Editor (and IDE)__: Emacs (nox) -> Vim -> Nano -> Vile -> [xwpe](https://github.com/amagnasco/xwpe) (full IDE in the terminal) -> [GNU Zile](https://directory.fsf.org/wiki/GNU_Zile)
* __Text Formatting and Pretty Printing__: [unoconv](http://dag.wiee.rs/home-made/unoconv/) -> Pandoc, par -> fmt (Textutils)
* __Text-To-Speech__: Orca -> Gespeaker -> [eBook-speaker](https://directory.fsf.org/wiki/EBook-speaker) (+ pandoc) -> [eSpeak](https://github.com/espeak-ng/espeak-ng/)
* __Typesetting__: LaTeX -> Texinfo -> [groff (tbl, pic, eqn, chem, music, dpic, grohtml)](https://www.troff.org/prog.html)
* __Typing Training__: Klavaro -> nlkt -> [GNU Typist](https://www.gnu.org/software/gtypist/)
* __Weather Forecast__: AWeather -> [Weather Util](http://fungi.yuggoth.org/weather/) -> [rrdweather](https://github.com/tolecnal/rrdweather)
* __Word Processor__: Libreoffice Writter -> Abiword -> MinEd -> [WordGrinder](http://cowlark.com/wordgrinder/) + Pandoc

## Package Management
* __Gaming Platform__: [LGOGDownloader](https://github.com/Sude-/lgogdownloader) (GOG.com), [SteamCMD](https://linode.com/docs/game-servers/install-steamcmd-for-a-steam-game-server/) (Steam), [Lutris](https://github.com/lutris/lutris)
* __Portable Apps__: Flatpak -> Snappy -> [AppImage](https://github.com/AppImage)
* __Universal Package Managers__: [Alien](https://joeyh.name/code/alien/) -> pkgsrc -> GNU Guix

## Pentesting
### Exploitables
* __Distros__: [Security Scenario Generator (SecGen)](https://github.com/cliffe/SecGen) -> [Damn Vulnerable Linux](https://sourceforge.net/projects/virtualhacking/files/os/dvl/) -> [Metasploitable](https://www.offensive-security.com/metasploit-unleashed/Requirements/) -> [Kioptrix](http://www.kioptrix.com/blog/)
* __Web Apps__: [Mutillidae](https://sourceforge.net/projects/mutillidae/) -> [hackxor](http://hackxor.net/) -> [WebGoat](https://www.owasp.org/index.php/Category:OWASP_WebGoat_Project)

### Network Scanner
* __DNS Client__: [whois](https://github.com/rfc1036/whois), bind-tools (nslookup, host, dig), [dnsenum](https://github.com/fwaeytens/dnsenum), [dnstracer](https://directory.fsf.org/wiki/Dnstracer)
* __Link Scanner__: [Metagoofil](https://github.com/laramies/metagoofil) -> [Linklint](http://www.linklint.org/) (+ [linklint2dot](http://www.deltadevelopment.de/users/christoph/linklint2dot/))
* __Network Enumeration__: [SSLScan](https://github.com/rbsec/sslscan), [p0f](https://github.com/p0f/p0f), [PRADS](https://gamelinux.github.io/prads/)
* __Network File Retrieval__: [tcpxtract](http://tcpxtract.sourceforge.net/) -> [Driftnet](https://github.com/deiv/driftnet)
* __Network Mapping__: [Open Visual Traceroute](http://visualtraceroute.net/) -> [EtherApe](http://etherape.sourceforge.net/) -> [Xtract](https://sourceforge.net/projects/netxtract/) -> [weathermap4rrd](http://weathermap4rrd.tropicalex.net/) -> [Paris Traceroute](https://github.com/libparistraceroute/paris-traceroute-OLD) -> [MTR](https://www.bitwizard.nl/mtr/) -> Ping (iputils) -> [arping](https://github.com/ThomasHabets/arping)
* __OSINT__: [Creepy](https://github.com/ilektrojohn/creepy) -> [Netglub](http://www.netglub.org/)
* __Packet Sniffer__: [tcpflow](https://directory.fsf.org/wiki/Tcpflow) -> [Tshark (Wireshark TUI)](https://github.com/wireshark/wireshark) -> [tcpdump](https://directory.fsf.org/wiki/Tcpdump)
* __Reconnaissance Framework__: [dsniff](https://www.monkey.org/~dugsong/dsniff/) (urlsnarf, filesnarf, webspy, Tcpkill, macof, arpspoof) -> [Nmap](https://nmap.org/) -> [ngrep](https://github.com/jpr5/ngrep/)
* __WiFi Scanner__: [FLUXION](https://github.com/wi-fi-analyzer/fluxion) -> [Kismet](https://www.kismetwireless.net/)

### Network Tampering
* __General__: [Netsed](https://github.com/xlab/netsed) -> [cryptcat](http://cryptcat.sourceforge.net/) (Netcat) -> [socat](https://github.com/craSH/socat)
* __Man-in-the-middle Attack__: [Morpheus](https://github.com/r00t-3xp10it/morpheus) -> [sslstrip](https://github.com/moxie0/sslstrip) -> [Ettercap](https://github.com/Ettercap/ettercap)
* __Packet Crafting__: [Ostinato](https://github.com/pstavirs/ostinato) -> [hping](https://github.com/antirez/hping)
* __Traffic Generator__: [Mausezahn](https://github.com/uweber/mausezahn)
* __Traffic Replay__: [Tcpreplay](https://github.com/appneta/tcpreplay)

### Password Cracking
* __BIOS__: [CmosPwd](https://www.cgsecurity.org/wiki/CmosPwd)
* __Compressed Files__: [RarCrack](http://rarcrack.sourceforge.net/)
* __General__: [John the Ripper](https://github.com/magnumripper/JohnTheRipper) / [Hashcat](https://github.com/hashcat/hashcat)
* __PDF__: [pdfcrack](https://github.com/x2q/pdfcrack-ng)
* __Remote__: [THC Hydra](https://github.com/vanhauser-thc/thc-hydra)
* __WiFi__: [Reaver](https://code.google.com/archive/p/reaver-wps/) -> [Aircrack-ng](https://github.com/aircrack-ng/aircrack-ng)
* __Windows__: [Ophcrack](http://ophcrack.sourceforge.net/)
* __Wordlist Generator__: [CUPP](https://github.com/Mebus/cupp) -> [crunch](https://github.com/crunchsec/crunch)

### Vulnerability Scanner
* __Application Vulnerability__: [BCCF](https://github.com/joxeankoret/nightmare/blob/master/doc/blind_code_coverage_fuzzer.txt) -> [afl-fuzz](http://lcamtuf.coredump.cx/afl/)
* __Backdooring__: [Veil](https://github.com/Veil-Framework/Veil) -> [Cymothoa](http://cymothoa.sourceforge.net/) -> [Backdoor Factory](https://github.com/secretsquirrel/the-backdoor-factory) -> [Evilgrade](https://github.com/infobyte/evilgrade) - [EvilAbigail](https://github.com/GDSSecurity/EvilAbigail)
* __Cross-Scripting__: [xsser](https://github.com/epsylon/xsser)
* __Exploit Famework__: [WebSploit](https://github.com/websploit/websploit) -> [w3af](https://github.com/andresriancho/w3af)
* __Network Vulnerability__: [pytbull](http://pytbull.sourceforge.net/) -> [Yersinia](https://github.com/tomac/yersinia)
* __Post Exploitation__: [Empire](https://github.com/EmpireProject/Empire) -> [Post Exploitation Collection](https://github.com/mubix/post-exploitation) (Windows) -> [mimikatz](https://github.com/gentilkiwi/mimikatz) (Windows) -> [Post Exploitation Linux Toolkit](https://github.com/cys3c/PELT) -> [poet](https://github.com/mossberg/poet)
* __Social Engineering__: [Social Engineering Toolkit](https://github.com/trustedsec/social-engineer-toolkit)
* __SQL Injection__: [sqlmap](https://github.com/sqlmapproject/sqlmap)
* __SSH Denial__: [screwSSH](https://github.com/isislab/screwSSH)
* __Web Application Vulnerability__: [Nikto](https://github.com/sullo/nikto)
* __Windows Registry Editor__: [Offline NT Password & Registry Editor (chntpw)](http://pogostick.net/~pnh/ntpasswd/)

## Privacy
* __Anti Stylometry__: [Anonymouth](https://github.com/psal/anonymouth), [renamer](https://github.com/CaptainBlacklace/Renamer)
* __Disk Cleaner__: [Dban](https://sourceforge.net/projects/dban/) -> bleachbit_cli ([BleachBit](https://github.com/bleachbit/bleachbit)) -> shred (GNU Coreutils)
* __Boot Encryption__: [cryptboot](https://github.com/xmikos/cryptboot)
* __Disk Encryption__: [StegFS](https://www.mcdonald.org.uk/StegFS/), [cryptsetup (dm-crypt)](https://gitlab.com/cryptsetup/cryptsetup/wikis/DMCrypt)
* __File Encryption__: [GNU Privacy Assistant](https://www.gnupg.org/related_software/gpa/) -> ccrypt -> [GNU Privacy Guard](https://www.gnupg.org/)
* __Full Storage Encryption__: VeraCrypt -> [tcplay](https://github.com/bwalex/tc-play) (full TrueCrypt implementation and still minimalist) -> [Tomb](https://github.com/dyne/Tomb)
* __Encrypted Version Control__: [Keyringer](https://github.com/quarkslab/keyringer)
* __Identity Generator__: [The Random Identity Generator (rig)](http://rig.sourceforge.net/)
* __Password Generator__: [pwgen](https://github.com/jbernard/pwgen) -> [apg](https://github.com/Distrotech/apg)
* __Password Manager__: KeePassX -> [pass](https://www.passwordstore.org/) (+ [pass-tomb](https://github.com/roddhjav/pass-tomb), + [passmenu](https://github.com/cdown/passmenu)) -> [kpcli](https://github.com/alecsammon/kpcli)
* __Steganography__: [StegoShare](http://stegoshare.sourceforge.net/) -> [Steghide](https://github.com/StefanoDeVuono/steghide) -> [SNOW](http://www.darkside.com.au/snow/) -> [Steganoroute](https://sourceforge.net/projects/steganoroute/)

## Programming
* __Build Automation__: [Gradle](https://github.com/gradle/gradle), [Buildroot](https://github.com/buildroot/buildroot), [Open Build Service](http://openbuildservice.org/) -> [CheckInstall](https://directory.fsf.org/wiki/CheckInstall) -> Autotools ([Automake](https://directory.fsf.org/wiki/Automake), [Autoconf](https://directory.fsf.org/wiki/Autoconf), [Libtool](https://directory.fsf.org/wiki/Libtool)), [GNU make](https://directory.fsf.org/wiki/Make), [Gnulib](https://www.gnu.org/software/gnulib/)
* __Cache__: Memcached -> EnhanceIO -> dm-cache -> bcache
* __Code Beautifier__: [UniversalIndentGUI](https://github.com/danblakemore/universal-indent-gui), HTML Tidy
* __Compiler__: [IcedTea](https://icedtea.classpath.org/wiki/Main_Page) (Java), [GnuCOBOL](https://sourceforge.net/projects/open-cobol/), [GCC](https://directory.fsf.org/wiki/Gcc)
* __Compiling Speeding Up__: [distcc](https://github.com/distcc/distcc), [ccache](https://github.com/ccache/ccache)
* __Documentation Browser__: Devhelp -> [Zeal](https://github.com/zealdocs/zeal)
* __Documentation Generator__: perlpod, [bashdoc](https://github.com/ajdiaz/bashdoc), Doxygen
* __Issue Tracking System__: Bugzilla -> [GNATS](https://www.gnu.org/software/gnats/)
* __Linting__: [ShellCheck](https://github.com/koalaman/shellcheck), [GNU Source-highlight](https://www.gnu.org/software/src-highlite/)
* __Other Tools__: [GNU bison](https://directory.fsf.org/wiki/Bison) and [Flex](https://directory.fsf.org/wiki/Flex), [GNU m4](https://directory.fsf.org/wiki/M4), [AutoGen](https://directory.fsf.org/wiki/Autogen), [pkgconf](https://github.com/pkgconf/pkgconf), [Installwatch](https://github.com/ruxkor/checkinstall/tree/master/installwatch), [sysconftool](https://github.com/svarshavchik/courier/tree/master/sysconftool), [GNU Stow](https://directory.fsf.org/wiki/Stow)
* __[Program Transformation](https://en.wikipedia.org/wiki/Program_transformation)__: [Coccinelle](http://coccinelle.lip6.fr/), [FermaT](http://www.gkc.org.uk/fermat.html), [CIL](https://people.eecs.berkeley.edu/~necula/cil/), [Stratego/XT](http://strategoxt.org/)
* __Source Code Navigation__: [LXR: The Linux Cross Referencer](http://lxr.sourceforge.net/en/index.php) -> [GNU GLOBAL](https://www.gnu.org/software/global/) -> [cscope](http://cscope.sourceforge.net/) -> [Ctags](https://github.com/universal-ctags/ctags) -> [cgvg](https://github.com/uzi/cgvg) -> [ack](https://beyondgrep.com/) -> [ag](https://github.com/ggreer/the_silver_searcher)
* __[Source-to-Source Compiler](https://en.wikipedia.org/wiki/Source-to-source_compiler)__: [ROSE](https://github.com/rose-compiler/rose)
* __Version Control__: Git (+ [tig](https://github.com/jonas/tig)) -> [CVS](https://directory.fsf.org/wiki/CVS) (+ [CVSGraph](https://directory.fsf.org/wiki/CVSGraph)) -> [Fossil](https://www.fossil-scm.org/index.html/doc/trunk/www/index.wiki) -> [tla (GNU Arch)](https://directory.fsf.org/wiki/Gnu-arch) -> [RCS](https://www.gnu.org/software/rcs/)

## Remote Access
* __Configuration Management__: Puppet -> CFEngine -> [cdist](https://github.com/ungleich/cdist)
* __Control Panel__: [Webmin](https://github.com/webmin/webmin)
* __Diskless Booting__: iPXE -> [netboot](http://netboot.sourceforge.net/)
* __PC-Mobile Connection__: KDE Connect -> Wammu -> BitPim -> AndroidTools
* __Remote Desktop Client__: rdesktop -> Remmina -> [fbvnc](https://github.com/zohead/fbvnc)
* __Remote Desktop Server__: [xrdp](https://github.com/neutrinolabs/xrdp)
* __Remote Execution__: [pconsole](https://github.com/walterdejong/pconsole)
* __Remote File Manager__: [KodExplorer](https://github.com/kalcaddle/KodExplorer)
* __Remote Login__: Mosh -> OpenSSH -> [lsh](https://directory.fsf.org/wiki/Lsh)
* __Remote X Apps__: Xpra > X11 forwarding
* __Reverse Shell__: [icmpsh](http://inquisb.github.io/icmpsh/) -> [RevSh](https://directory.fsf.org/wiki/Reverse_Shell)
* __Serial Console__: Minicom -> [Picocom](https://directory.fsf.org/wiki/Picocom) -> Qodem / [GNU Screen](http://www.noah.org/wiki/Screen_notes#using_screen_as_a_serial_terminal)
* __Server Provisioning__: [FAI](http://fai-project.org/)
* __Wake-on-LAN__: [wakeonlan](https://github.com/jpoliv/wakeonlan)

## Science And Engineering
* __Artificial Intelligence__: [Arcade Learning Environment](https://github.com/mgbellemare/Arcade-Learning-Environment), [ETHNOS](http://ethnos.sourceforge.net/), [Conscious Artificial Intelligence](https://sourceforge.net/projects/cai/), [OpenCog](https://github.com/opencog/opencog), [OpenAI](https://github.com/openai)
* __Astronomy__: [SaVi satellite constellation visualizer](https://sourceforge.net/projects/savi/), Stellarium -> Celestia -> [SkyCat](https://github.com/Starlink/skycat)
* __Bioinformatics__: [OpenSim](https://simtk.org/projects/opensim/), [Cytoscape](http://www.cytoscape.org/), [BioJava](https://github.com/biojava/biojava) -> [EMBOSS](https://github.com/kimrutherford/EMBOSS) -> [SAMtools](https://github.com/samtools/samtools) -> [BioPerl](http://bioperl.org/)
* __CAD__: AutoCAD -> FreeCAD -> [OpenSCAD](https://github.com/openscad/openscad)
* __Chemistry__: [MolComp](http://molcomp.sourceforge.net/), [RasMol](https://directory.fsf.org/wiki/RasMol), [PerlMol](http://www.perlmol.org/)
* __Circuit Simulator__: [ngspice](http://ngspice.sourceforge.net/), [Gnucap](http://www.gnucap.org/dokuwiki/doku.php?id=gnucap:start)
* __Computational Fluid Dynamics__: [TELEMAC](http://www.opentelemac.org/) -> [FEATFLOW](http://www.featflow.de/en/index.html) -> [OpenFOAM](https://directory.fsf.org/wiki/OpenFOAM) -> [Gerris](http://gfs.sourceforge.net/wiki/index.php/Main_Page)
* __Computer Algebra System__: [Singular](http://www.singular.uni-kl.de/) -> [Axiom](http://www.axiom-developer.org/) -> [Maxima](http://maxima.sourceforge.net/) (+ PLplot)
* __Data Visualization__: [Mobility Testbed](https://github.com/agents4its/mobilitytestbed), [NetLogo](https://github.com/NetLogo/NetLogo/), [SocNetV](https://github.com/socnetv) -> [Gephi](https://github.com/gephi/gephi) -> [Tulip](http://tulip.labri.fr/TulipDrupal/)
* __Fractals__: [Mandelbulber](https://github.com/buddhi1980/mandelbulber2)
* __Geographic Information System__: [qGIS](https://github.com/qgis/QGIS)
* __Street Map__: [JOSM](https://github.com/openstreetmap/josm) -> [Osmosis](https://github.com/openstreetmap/osmosis)
* __Subway Map__: [qMetro](http://qmetro.sourceforge.net/maps/)
* __Virtual Globe__: [Marble](https://github.com/KDE/marble)
* __Graphing Calculator__: KAlgebra -> [TilEm](http://lpg.ticalc.org/prj_tilem/)
* __Multi-Agent (MA) Simulation__: [Mobility Testbed](https://github.com/agents4its/mobilitytestbed) -> [Galatea](http://galatea.sourceforge.net/Home.htm) -> [NetLogo](https://github.com/NetLogo/NetLogo/), [Golly](http://golly.sourceforge.net/) (Conway's Game of Life clone)
* __Physics Simulation__: [OpenModelica](https://www.openmodelica.org/) -> [CalculiX](http://www.calculix.de/) -> [Elmer](https://directory.fsf.org/wiki/Elmer) -> [MCSim](https://directory.fsf.org/wiki/Mcsim)
* __Semiconductor Modeling (TCAD)__: [GNU Archimedes](https://directory.fsf.org/wiki/Archimedes) (and [GNU Nano-Archimedes](https://directory.fsf.org/wiki/Nano-archimedes))
* __Software-defined radio (SDR)__: [GNU Radio](https://github.com/gnuradio) (+ [Gqrx](https://github.com/csete/gqrx)) -> [rtl-sdr](https://github.com/osmocom/rtl-sdr)
* __Statistical Package__: [SageMath](http://www.sagemath.org/) -> [gretl](http://gretl.sourceforge.net/) -> [PSPP](https://directory.fsf.org/wiki/Pspp)  (+ PSPP-Perl)
* __Theorem Prover__: Coq -> [Abella](https://github.com/abella-prover/abella) -> [Vampire](https://github.com/mayfrost/Vampire)

## Security
### Containment
* __Access Control__: SELinux -> Smack -> AppArmor + [RSBAC](https://www.rsbac.org/)
* __Authentication__: Polkit/ConsoleKit -> FakeRoot -> Sudo (visudo) -> Linux PAM
* __Resource Usage Control__: [Disk Quota](https://sourceforge.net/projects/linuxquota/) -> [quotatool](https://github.com/ekenberg/quotatool), ulimit, [cpulimit](https://github.com/opsengine/cpulimit)
* __Sandboxing__: [Firejail](https://github.com/netblue30/firejail) -> [Bubblewrap](https://github.com/projectatomic/bubblewrap)

### Honeypots
* __Client__: [HoneyC](https://projects.honeynet.org/honeyc), [Capture-HPC](https://projects.honeynet.org/capture-hpc)
* __Distro Bundle__: [HoneyDrive](https://sourceforge.net/projects/honeydrive/) -> [ADHD](https://adhdproject.github.io/#!index.md)
* __Server__: [Honeyperl](https://sourceforge.net/projects/honeyperl/) -> [Nova](https://github.com/DataSoft/Nova) -> [LaBrea](http://labrea.sourceforge.net/labrea-info.html)
* __Web-Based__: [HIHAT](http://hihat.sourceforge.net/)

### Host Intrusion
* __Anti Juice Jacking__: [usbkill](https://github.com/hephaest0s/usbkill), [USBGuard](https://github.com/USBGuard/usbguard)
* __Anti Malware__: ClamTk -> [ClamAV](https://github.com/Cisco-Talos/clamav-devel) -> [Linux Malware Detect (LMD)](https://github.com/rfxn/linux-malware-detect)
* __Host Intrusion Detection Framework__: [OSSEC](https://ossec.github.io/) -> [Tiger](http://www.nongnu.org/tiger/)
* __Host System Auditing__: [OpenVAS](http://www.openvas.org/) -> [Linux Security Auditing Tool (LSAT)](https://github.com/triode3/lsat) -> [Bastille](http://bastille-linux.sourceforge.net/) -> [Lynis](https://github.com/CISOfy/lynis)
* __Integrity Check__ AIDE -> [systraq](https://directory.fsf.org/wiki/Systraq) -> [Tripwire](https://github.com/Tripwire/tripwire-open-source) -> [Samhain](https://www.la-samhna.de/samhain/)
* __Rootkit Detection__: [rkhunter](http://rkhunter.sourceforge.net/), [Chkrootkit](http://www.chkrootkit.org/), [Unhide](http://www.unhide-forensics.info/)
* __System Logging__: [Syslog-ng](https://github.com/balabit/syslog-ng) -> [sysklogd](http://www.infodrom.org/projects/sysklogd/)

### Network Intrusion
* __Deep Packet Inspection (DPI) Block and Circumvention__: [zapret](https://github.com/bol-van/zapret)
* __Firewall__: gufw -> ufw -> iptables (+ [ipset](http://ipset.netfilter.org/)) -> [nftables](https://netfilter.org/projects/nftables/)
* __Man-In-The-Middle (MITM) Detection__: [ArpON](http://arpon.sourceforge.net/), [Arpalert](http://www.arpalert.org/arpalert.html)
* __Network Intrusion Detection__: Snort -> [Suricata](https://github.com/OISF/suricata)
* __Network Intrusion Prevention__: Fail2ban -> [Sshguard](https://www.sshguard.net/)

## Server
* __BBS Server__: [Citadel](http://www.citadel.org/doku.php) -> Synchronet -> [Mystic BBS](http://www.tinysbbs.com/files/prog/MSRC20B3.ZIP) -> [BBS100](https://directory.fsf.org/wiki/Bbs100)
* __Blog__: finger / [cfingerd](https://github.com/pld-linux/cfingerd)
* __Captcha__: [cool-php-captcha](https://github.com/josecl/cool-php-captcha)
* __Chat__:  [sshtalk](https://2ton.com.au/sshtalk/) -> [write, wall, mesg](http://www.unixpapa.com/write.html)
* __CMS__: WordPress -> [GetSimple CMS](https://github.com/GetSimpleCMS/GetSimpleCMS) -> [werc](http://werc.cat-v.org/)
* __Collaborative Real-Time Editor__: [Gobby](https://github.com/gobby/gobby) -> [EtherCalc](https://github.com/audreyt/ethercalc) -> [Cryptpad](https://github.com/xwiki-labs/cryptpad)
* __Direct Connect Server__: [uhub](https://www.uhub.org/)
* __DLNA__: [Universal Media Server](https://github.com/UniversalMediaServer/UniversalMediaServer) -> [ReadyMedia](http://minidlna.sourceforge.net/) (a.k.a. MiniDLNA)
* __Document Management System__: [OpenKM](https://github.com/openkm/document-management-system) -> [LogicalDOC](https://github.com/logicaldoc/document-management-software) -> [EPrints](https://github.com/eprints/eprints)
* __E-Mail Filtering (LDA)__: Dovecot -> [procmail](https://github.com/Distrotech/procmail)
* __E-Mail Indexing__: Archmbox -> Chewmail -> Notmuch -> [mairix](https://github.com/rc0/mairix)
* __E-Mail Mailing Lists__: Mailman -> [Sympa](https://github.com/sympa-community) -> [Dada Mail](https://github.com/justingit/dada-mail) -> [ezmlm](https://github.com/bruceg/ezmlm-idx)
* __E-Mail Notifier__: [mswatch](http://mswatch.sourceforge.net/)
* __E-Mail Server (MTA)__: [Mail-in-a-Box](https://mailinabox.email/) -> Postfix -> Exim -> [cmail](http://cmail.rocks/) -> [qpsmtpd](https://smtpd.github.io/qpsmtpd/) -> [qmail](https://en.wikipedia.org/wiki/Qmail)
* __E-Mail Spam Filter__: DSPAM -> [SpamAssassin](https://github.com/apache/spamassassin)
* __E-Mail Validation__: [OpenDKIM](http://opendkim.org/), [SPF](http://www.openspf.org/)
* __File Distribution__: [zsync](http://zsync.moria.org.uk/)
* __Forum__: [lainchan](https://github.com/lainchan/lainchan) -> [Akari-BBS](https://github.com/microsounds/akari-bbs) -> [sshchan](https://github.com/einchan/sshchan) -> [1436chan](https://github.com/kibook/1436chan)
* __File Server__: Google Drive -> Nextcloud -> WebDAV -> [Syncthing](https://github.com/syncthing/syncthing) -> [vsftpd](https://github.com/timonier/vsftpd) -> sftp / [SSHFS](https://github.com/libfuse/sshfs) (SSH)
* __Groupware__: [Alfresco](https://github.com/Alfresco) -> [eXo Platform](https://github.com/exoplatform) -> [Citadel/UX](http://www.citadel.org/doku.php)
* __IRC Bot__: [Seabattle](https://github.com/GamesLT/SeaBattle.tcl) (bot game), [Infobot](https://github.com/w3c/infobot), [Eggdrop](https://www.eggheads.org/) (IRC bot)
* __IRC Bouncer (BNC)__: [ZNC](https://github.com/znc/znc)
* __IRC Fileserver__: [iroffer](https://github.com/grimneko/iroffer-modDinoex)
* __IRC Server__: UnrealIRCd / Charybdis -> InspIRCd -> [ngIRCd](https://github.com/ngircd/ngircd)
* __Learning Management System__: [GnuTutor](https://sourceforge.net/projects/gnututor/) -> [OpenExpert](https://sourceforge.net/projects/law-expert/) -> [Syllog](https://sourceforge.net/p/syllog/wiki/Home/)
* __MUD Server__: [PennMUSH](https://github.com/pennmush/pennmush)
* __Paint chat__: [Drawpile](https://github.com/drawpile/Drawpile) -> [Collab](https://github.com/MoonGames/collab-desktop)
* __Pastebin__: Stikked -> Paste -> [PrivateBin](https://github.com/PrivateBin/PrivateBin)
* __Political__: [LittleSis](https://github.com/public-accountability/littlesis-rails), [Loomio](https://github.com/loomio/loomio)
* __Port Tunnel__: [stunnel](https://www.stunnel.org/) -> [knockd](https://github.com/jvinet/knock)
* __Proxy Server__: [Tinyproxy](https://tinyproxy.github.io/)
* __Service Manager__: [sslh](https://github.com/yrutschle/sslh), [xinetd](https://github.com/xinetd-org/xinetd), [TCP Wrappers](https://github.com/pexip/os-tcp-wrappers) (tcpd, tcpdchk)
* __Streaming__: [Peerflix](https://github.com/mafintosh/peerflix) (+ [Torrentflix](https://github.com/ItzBlitz98/torrentflix)) -> [Libresonic](https://github.com/Libresonic/libresonic) -> [Syncplay](https://github.com/Syncplay/syncplay) -> [VLC](https://www.howtogeek.com/118075/how-to-stream-videos-and-music-over-the-network-using-vlc/) -> [FFmpeg](https://gist.github.com/olasd/9841772)
* __Torrent Tracker__: [Ocelot](https://github.com/whatcd/ocelot) -> [Gazelle](https://github.com/WhatCD/Gazelle)
* __Tunneling__: [ProxyChains](https://github.com/rofl0r/proxychains-ng) -> [VPNEncap](https://github.com/whussup/vpnencap) -> [VPNCHAINS](https://sourceforge.net/p/vpnchains/wiki/Home/)
* __Tunneling VM__: [PIA Tunnel](https://www.privateinternetaccess.com/forum/discussion/1389/pia-tunnel-a-virtual-machine-vpn-tunnel), [Whonix](https://www.whonix.org/)
* __Usenet Server__: [InterNetNews](https://www.eyrie.org/~eagle/software/inn/) -> [Leafnode](http://www.leafnode.org/)
* __VoIP__:  Mumble -> [Linphone (linphonec)](https://www.linphone.org/) -> [sscall](https://github.com/Drakevr/sscall)
* __VPN__: OpenVPN (+ [PiVPN](http://www.pivpn.io/)) -> [WireGuard](https://github.com/WireGuard/wireguard-rs)
* __Web Caching__: Decentraleyes on a web browser -> [Squid](http://www.squid-cache.org/) (+ [SquidGuard](http://squidguard.org/) for Web Filtering)
* __Web Filtering__: Ad blocker on a web browser -> [Pi-hole](https://github.com/pi-hole/pi-hole) -> [Privoxy](http://www.privoxy.org/) -> [Hostsblock](https://github.com/gaenserich/hostsblock)
* __Web Server__: Apache -> Nginx -> lighttpd -> [GNU MyServer](https://directory.fsf.org/wiki/GNU_MyServer) -> [darkhttpd](https://github.com/ryanmjacobs/darkhttpd) -> [Bucktooth](http://gopher.floodgap.com/gopher/gw?gopher/1/buck) (Gopher) + [Bucky](https://github.com/kibook/bucky) (for HTTP exit)
* __Wiki__: [XWiki](https://github.com/xwiki/xwiki-platform) -> [ikiwiki](https://ikiwiki.info/)
* __Wireless Access Point__: [hostapd](https://github.com/OpenSecurityResearch/hostapd-wpe)
* __XMPP Server__: [Tigase](https://github.com/kontalk/tigase-server)

### Server Authentication
* __Domain Specific Authentication Server__: Ident (IRC), [SKS](https://bitbucket.org/skskeyserver/sks-keyserver/wiki/Home) (PGP)
* __Directory Service__: [OpenLDAP](https://www.openldap.org/) -> [NIS](http://www.linux-nis.org/nis/)
* __RADIUS__: [FreeRADIUS](https://github.com/FreeRADIUS) -> [GNU Radius](https://www.gnu.org/software/radius/)
* __SSO__: [GNU Shishi](https://www.gnu.org/software/shishi/) (Kerberos)
* __Suites__: [FreeIPA](https://github.com/freeipa/freeipa) -> [SSSD](https://github.com/SSSD/sssd)

## System Tools
* __BIOS__: Coreboot -> [Libreboot](https://libreboot.org/)
* __[Boot Loader](https://github.com/mayfrost/guides/blob/master/BOOTLOADER.md)__: GRUB 2 -> GRUB Legacy -> [SYSLINUX](http://www.syslinux.org/wiki/index.php?title=The_Syslinux_Project) -> [LILO](https://lilo.alioth.debian.org/) (or [ELILO](https://sourceforge.net/projects/elilo/) for UEFI)
* __Custom Initramfs__: mkinitcpio -> dracut -> [mkinitramfs](https://github.com/tokiclover/mkinitramfs-ll)
* __Filesystem__: XFS, Ext4, [JFS](http://jfs.sourceforge.net/), [Reiser4](https://reiser4.wiki.kernel.org/index.php/Main_Page), [Bcachefs](https://github.com/8l/Bcachefs)
* __Hibernation__: [TuxOnIce](https://github.com/NigelCunningham/tuxonice-kernel) -> [uswsusp](http://suspend.sourceforge.net/)
* __Init - Init Daemon__: [Upstart](https://code.launchpad.net/upstart) -> [SysVinit](https://github.com/slicer69/sysvinit) -> [Initng](https://github.com/initng/initng) -> [sinit](https://github.com/henrysher/sinit)
* __Init - Service Manager (to be used with an init)__: OpenRC (includes an optional own init) -> runit (includes an optional own init) -> [daemontools-encore](https://github.com/bruceg/daemontools-encore) -> [perp](https://github.com/jdavisp3/perp)
* __Init - Startup Scripts Manager__: [bum](https://launchpad.net/bum) -> [sysv-rc-conf](http://sysv-rc-conf.sourceforge.net/) -> [chkconfig](https://uni.edu/~prefect/devel/chkconfig/index.shtml)
* __IPC__: DBus -> ipcs (util-linux)
* __Job Scheduler__: [Slurm](https://github.com/SchedMD/slurm) -> [fcron](http://fcron.free.fr/) (Cron), [incron](http://inotify.aiken.cz/?section=incron&page=about&lang=en)
* __Load in RAM__: [E4rat](https://github.com/ShyPixie/e4rat-lite) -> readahead -> [preload](https://sourceforge.net/projects/preload/), [prelink](https://directory.fsf.org/wiki/Prelink)
* __Settings Manager__: [Linux Lite Control Center](https://github.com/linuxlite/litecontrolcenter) -> [Elektra](https://github.com/ElektraInitiative/libelektra) -> [Augeas](https://github.com/hercules-team/augeas)
* __Utilities__: Mtools -> GNU Coreutils -> BusyBox -> Asmutils and ARMutils
