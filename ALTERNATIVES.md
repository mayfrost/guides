# ALTERNATIVES TO BLOATWARE

The list is built pointing to software that has alternatives with less dependencies, and addressing dependencies was the easy thing. Some tools in particular were included because they add less dependencies overall while keeping a system functional. One such example is imagemagick and ffmpeg, by which you can do a lot of work and replace many tools by just using those with scripts and replace something like a screenshot utility. Certainly it would be great to have a comparative on resource usage. However, a new revision now includes software that was previously discarded for better comparison and featured recommendations will not be highlight for the moment.

TL;DR: is about the unix principle, having a fully functional system pretty damn minimal with that.

## TOC
1. [ANDROID APPS](#android-apps)  
2. [Command Line](#command-line)  
3. [Communication](#communication)  
3.1. [Desktop Client](#desktop-client)  
4. [Data](#data)  
5. [Decentralized Networking](#decentralized-networking)  
6. [Emulation And Virtualization](#emulation-and-virtualization)  
7. [File Utilities](#file-utilities)  
8. [Filesharing](#filesharing)  
9. [Forensics](#forensics)  
10. [Hardware](#hardware)  
11. [Monitoring](#monitoring)  
11.1. [Benchmarking](#benchmarking)  
11.2. [System Information](#system-information)  
11.3. [System Monitoring](#system-monitoring)  
12. [Multimedia](#multimedia)  
12.1. [ASCii Art](#ascii-art)  
12.2. [Audio](#audio)  
12.3. [Image](#image)  
12.4. [Metadata](#metadata)  
12.5. [Video](#video)  
13. [Network Setup](#network-setup)  
14. [Office](#office)  
15. [Package Management](#package-management)  
16. [Pentesting](#pentesting)  
16.1. [Exploitables](#exploitables)  
16.2. [Network Scanner](#network-scanner)  
16.3. [Network Tampering](#network-tampering)  
16.4. [Password Cracking](#password-cracking)  
16.5. [Vulnerability Scanner](#vulnerability-scanner)  
17. [Privacy](#privacy)  
18. [Programming](#programming)  
19. [Remote Access](#remote-access)  
20. [Science And Engineering](#science-and-engineering)  
21. [Security](#security)  
21.1. [Containment](#containment)  
21.2. [Honeypots](#honeypots)  
21.3. [Host Intrusion](#host-intrusion)  
21.4. [Network Intrusion](#network-intrusion)  
22. [Server](#server)  
22.1. [Server Authentication](#server-authentication)  
23. [System Utilities](#system-utilities)  
23.1. [Init](#init)  
23.2. [Job Scheduler](#job-scheduler)  
24. [X Desktop](#x-desktop)  


## ANDROID APPS
* __Launcher__: [Indistractable Launcher](https://play.google.com/store/apps/details?id=com.indistractablelauncher.android) (54MB) -> [A decluttered launcher](https://declutter.site/) (35MB) -> [OpenLauncher](https://github.com/OpenLauncherTeam/openlauncher) (8,3 MB) -> [Catapult](https://bitbucket.org/lenny_kano/catapult) (4,7 MB) -> [Lawnchair](https://lawnchair.info/) (3,1 MB) -> [Paper Launch](https://github.com/devmil/PaperLaunch) (2,8 MB) -> [Launch Time](http://quaap.com/D/LaunchTime) (2,5 MB) -> [Silverfish](https://github.com/stanipintjuk/Silverfish) (1,5 MB) -> [T-UI](https://github.com/Andre1299/TUI-ConsoleLauncher) (1,2 MB) -> [Search Based Launcher](https://github.com/vackosar/search-based-launcher/) (622 KB) -> [KISS](http://kisslauncher.com/) (431 KB) -> [Emerald Launcher](https://github.com/HenriDellal/emerald) (172 KB) -> [Hayai Launcher](https://github.com/seizonsenryaku/HayaiLauncher/blob/HEAD/README.md) (106 KB) -> [Fast](https://github.com/ligi/FAST) (76 KB) -> [Essential Launcher](https://clemensbartz.de/essential-launcher/) (26 KB) -> [Null Launcher](https://github.com/notriddle/null-launcher) (12 KB)
* __Facebook__: [FaceSlim](https://github.com/indywidualny/FaceSlim) (1,3 MB) -> [Tinfoil for Facebook](https://github.com/velazcod/Tinfoil-Facebook) (525 KB) -> [SlimSocial](https://github.com/rignaneseleo/SlimSocial-for-Facebook) (313 KB)
* __Twitter__: Tinfoil for Twitter -> [SlimSocial for Twitter](https://github.com/rignaneseleo/SlimSocial-for-Twitter) (699 KB)
* __YouTube__: [NewPipe](https://newpipe.schabi.org/) (5,0 MB) -> [SkyTube](http://skytube-app.com/) (4,9 MB) -> [WebTube](https://github.com/martykan/webTube/blob/HEAD/README.md) (2,1 MB) -> [MinTube](https://github.com/imshyam/mintube) (981 KB)
* __Photo Gallery__: [Simple Gallery](https://github.com/SimpleMobileTools/Simple-Gallery) (12 MB) -> [LeafPic](https://gitlab.com/HoraApps/LeafPic) (10/2016: 4.3 MB) -> [Cameraroll](https://github.com/kollerlukas/Camera-Roll-Android-App) (2.4 MB) -> [A Photo Manager](https://github.com/k3b/APhotoManager) (1.3MB)
* __E-Books__: [Document Viewer](https://f-droid.org/en/packages/org.sufficientlysecure.viewer/) (8.5 MB)
* __Notes__: [Orgzly](https://github.com/orgzly/orgzly-android) (3.9 MB) -> [Markor](https://github.com/gsantner/markor) (3 MB) -> [miniNoteViewer](https://github.com/monolifed/mininoteview) (452 KB)
* __Keyboards__: Hacker's Keyboard (1,2 MB) -> [Simple Keyboard](https://f-droid.org/en/packages/rkr.simplekeyboard.inputmethod/) (835 KB)
* __File Manager__: Amaze -> OI File Manager
* __Dictionary__: Quickdic
* __Firewall__: NetGuard -> AFWall+
* __E-Mail__: K-9 Mail

Most apps are from F-Droid, we are just starting.

## Command Line
* __Commands Cheatsheet__: [CLI Companion](https://launchpad.net/clicompanion) -> [xman](https://www.x.org/archive/X11R7.5/doc/man/man1/xman.1.html) -> [cheat](https://github.com/chrisallenlane/cheat) / [howdoi](https://github.com/gleitz/howdoi) / [clf](https://github.com/ncrocfer/clf) / [fu](https://github.com/samirahmed/fu) / [bro](http://bropages.org/) -> [curl cht.sh/PROGRAM](https://github.com/chubin/cheat.sh)
* __Copy and Move Progress Bar__: [progress](https://github.com/Xfennec/progress) -> [Advanced Copy](https://github.com/atdt/advcpmv)
* __Daemonize__: [dtach](https://github.com/crigler/dtach) -> [abduco](https://github.com/martanne/abduco) -> [GNU Screen](https://www.gnu.org/software/screen/)
* __Directory Bookmarks__: [Apparix](https://micans.org/apparix/) -> [fasd](https://github.com/clvv/fasd)
* __Framebuffer Environment__: [jfbterm](https://github.com/ruo91/jfbterm)/[Fbterm](https://code.google.com/archive/p/fbterm/) -> [yaft (because sixel)](https://github.com/uobikiemukot/yaft) -> [hterm (because regis)](https://github.com/new299/hackterm) -> [Fbpad](https://github.com/aligrudi/fbpad) -> [FramebufferUI](https://github.com/8l/fbui)
* __Hacker Culture__: [ddate](https://github.com/bo0ts/ddate), [fortune](https://github.com/ruanyf/fortunes), [The Hacker Test](https://packages.debian.org/source/unstable/purity), [The Jargon File](https://packages.debian.org/source/unstable/jargon)
* __[Login](https://en.wikipedia.org/wiki/Getty_(Unix))__: [fgetty](http://www.fefe.de/fgetty/) -> [mingetty](https://sourceforge.net/projects/mingetty/) -> stty (GNU Coreutils) -> agetty (util-linux)
* __Menu__: [pdmenu](https://joeyh.name/code/pdmenu/) -> [tmenu](https://github.com/dhamidi/tmenu) -> [iSelect](http://www.ossp.org/pkg/tool/iselect/) -> [pick](https://github.com/mptre/pick) -> [fzy](https://github.com/jhawthorn/fzy) -> [slmenu](https://bitbucket.org/rafaelgg/slmenu)
* __Multiplexer__: [Byobu](https://github.com/dustinkirkland/byobu) -> [Tmux](https://github.com/tmux/tmux) -> [GNU Screen](https://www.gnu.org/software/screen/) (+[sixel patch](https://gist.github.com/saitoha/7546579)) -> [dvtm](http://www.brain-dump.org/projects/dvtm/)
* __Notification__: [skroll](http://z3bra.org/skroll/)
* __Progress Bar__: [vramsteg](https://github.com/mogaal/vramsteg) -> [clpbar](http://clpbar.sourceforge.net/)- > [pv - Pipe Viewer](https://github.com/icetee/pv) -> [sob - simple output bar](http://git.codemadness.nl/sob/) -> [dbar](https://sites.google.com/site/gotmor/)
* __Scripting__: [Multipipe](http://multipipe.sourceforge.net/) -> [GNU Parallel](https://www.gnu.org/software/parallel/) (+ [GNU SQL](https://www.gnu.org/software/parallel/sql.html)) -> [execline](https://github.com/skarnet/execline) -> [Expect](https://core.tcl.tk/expect/index) -> [empty](https://github.com/ierton/empty)
* __Shells__: [Xonsh](https://github.com/xonsh/xonsh) -> [PowerShell](https://github.com/PowerShell/PowerShell) -> [Bash](https://www.gnu.org/software/bash/) (+ [bash-completion](https://github.com/scop/bash-completion) + [bash-completion-extras](https://git.eckner.net/Erich/bash-completion-extras)) -> [zsh](http://www.zsh.org/) -> [tcsh](https://github.com/tcsh-org/tcsh) -> [PC-DCL](https://github.com/MichelValentin/PC-DCL) -> [mksh](https://github.com/MirBSD/mksh) -> [dash](http://gondor.apana.org.au/~herbert/dash/) -> [rc](https://github.com/rakitzis/rc) -> [s](https://github.com/rain-1/s) -> [Danshell](http://danshell.sourceforge.net/)
* __Terminal Colorizer__: [colout](http://nojhan.github.io/colout/) -> [lolcat](https://github.com/busyloop/lolcat) -> [Bashish](https://github.com/arnognulf/bashish)
* __Terminal Dropdown__: [tdrop](https://github.com/noctuid/tdrop) -> [YeahConsole](https://github.com/rduplain/yeahconsole) -> [alwaysontop](https://github.com/swirepe/alwaysontop)
* __Terminal Emulator__: [PuTTY](https://www.putty.org/) -> [Cool Retro Term](https://github.com/Swordfish90/cool-retro-term) -> [Terminology](https://www.enlightenment.org/about-terminology) -> [rxvt-unicode](https://github.com/exg/rxvt-unicode) (a.k.a. urxvt) -> [Termite](https://github.com/thestinger/termite) -> [UXTerm](https://invisible-island.net/xterm/) (XTerm) -> [st](https://st.suckless.org/) -> [Qodem](http://qodem.sourceforge.net/)
* __Terminal Pager__: [most](http://www.jedsoft.org/most/) -> [less](http://www.greenwoodsoftware.com/less/) (+ [lesspipe](https://www-zeuthen.desy.de/~friebel/unix/lesspipe.html))
* __Terminal Screensaver__: [bb](http://aa-project.sourceforge.net/bb/), [sl](https://github.com/mtoyoda/sl), [tty-clock](https://github.com/xorg62/tty-clock), CMatrix, cowsay (or cowthink), [rice](https://github.com/janbrennen/rice), [Asciiquarium](https://github.com/cmatsuoka/asciiquarium), [pipes](https://github.com/pipeseroni/pipes.sh), [nyan.sh](https://gist.github.com/wting/5278321), [rickrollrc](https://github.com/keroserene/rickrollrc), [NCMatrix](https://github.com/mayfrost/NCMatrix), [terminal-screensaver](https://github.com/xiongchiamiov/terminal-screensaver), [No More Secrets](https://github.com/bartobri/no-more-secrets)

## Communication
* __BBS-MUD Client__: SyncTERM -> KildClient -> kbtin -> [TinTin++](http://tintin.sourceforge.net/features.php)
* __Bookmarks Manager__: [bookmarks.public](https://github.com/skx/bookmarks.public) -> [bk_edit](http://www.vakuumverpackt.de/retiredprojects/bk_edit/) -> [pmb](https://github.com/neoncortex/poor-man-s-bookmark) -> [b.](https://directory.fsf.org/wiki/B.)
* __Browser__: ungoogled-chromium -> Pale Moon -> [GNU IceCat](https://www.gnu.org/software/gnuzilla/) -> luakit / vimb / surf (tabbed) / Uzbl (tabbed) -> [NetSurf](http://www.netsurf-browser.org/) (works in the framebuffer too) -> Arachne (works in the framebuffer too)
* __Browser (Command Line)__: w3m (can display images) -> Lynx -> [Links2](http://links.twibright.com/) (can display images) -> [Netrik](http://netrik.sourceforge.net/) -> retawq
* __Browser (Gopher)__: [GopherVR](http://www.floodgap.com/software/gophervr/) -> [gopherfs](http://git.savannah.gnu.org/cgit/hurd/incubator.git/) -> [UMN Gopher client](https://github.com/jgoerzen/gopher) -> [sacc](https://git.fifth.space/sacc/log.html) -> [cgo](https://github.com/kieselsteini/cgo) -> Lynx
* __Chat Client__: [Finch (Pidgin)](https://developer.pidgin.im/wiki/Using%20Finch) in [irssi mode](https://askubuntu.com/questions/442345/how-can-i-simplify-the-finch-interface) -> [Centerim](http://www.centerim.org/index.php/Main_Page) -> [Bitlbee](https://wiki.bitlbee.org/)
* __E-Mail Archiver__: Hypermail -> [Lurker](http://lurker.sourceforge.net/)
* __E-Mail Client (MUA)__: Icedove/Thunderbird (+ Enigmail) -> [Mailspring](https://github.com/Foundry376/Mailspring) -> Emacs (Gnus) -> [SquirrelMail](http://www.squirrelmail.org/) -> Alpine -> Mutt -> mailutils ("mailx") -> [S-nail ("mailx")](https://www.sdaoden.eu/code.html) + Muttprint
* __E-Mail Fetcher__: [Fetchmail](http://www.fetchmail.info/) -> fdm -> [isync (mbsync)](http://isync.sourceforge.net/)
* __E-Mail MIME__: TNEF -> metamail
* __E-Mail SMTP Client__: nullmailer -> msmtp -> esmtp -> SSMTP
* __IPTV__: FreetuxTV -> iptvx
* __IRC Client__: HexChat -> BitchX -> Weechat -> Irssi -> ii -> sic
* __Media Center__: Plex -> Kodi ("XBMC", + Sonarr) -> Emby -> Popcorn Time -> [LittleWeeb](https://littleweeb.github.io/)
* __Offline Reader__: [Kiwix](http://www.kiwix.org/) -> Darcy Ripper -> HTTrack -> [Stallman.js](https://github.com/isdampe/Stallman.js/tree/master) -> Wget
* __Online Radio__: [Nuvola Player](https://tiliado.eu/nuvolaplayer/)
* __RSS Feed and Podcast__: gPodder -> Raggle -> Liferea -> Newsbeuter (+ Podbeuter) -> Newsboat -> [sfeed](https://codemadness.org/git/sfeed/file/README.html)
* __Search Engine Scraper__: Googler -> [Surfraw](http://surfraw.alioth.debian.org/) (+ [dmenu](https://bbs.archlinux.org/viewtopic.php?id=228706) or slmenu)
* __Streams Catcher__: Streamripper -> youtube-dl -> [cclive](https://github.com/legatvs/cclive) -> [youtube-pl](http://ronja.twibright.com/youtube-pl.php) -> [RTMPDump](https://github.com/mstorsjo/rtmpdump) -> [quvi](https://github.com/mogaal/quvi)
* __UPnP (DLNA) Client__: [djmount](https://github.com/Boxee/djmount)
* __Usenet Client (Newsreader)__: Pan -> [slrn](http://www.slrn.org/) ( + slrnpull + slrnface) -> Trn
* __VoIP Client__: Empathy -> [Jitsi](https://jitsi.org/) -> [Finch (Pidgin)](https://developer.pidgin.im/wiki/vv)
* __XMPP Client__: Profanity

### Desktop Client
* __4chan__: [ANSIchan](https://github.com/qqueue/ANSICHAN) / [yottu](https://github.com/yottu/yottu)
* __Booru__: [ahoviewer](https://github.com/ahodesuka/ahoviewer)
* __Facebook__: facy - > [FBCMD](https://github.com/dtompkins/fbcmd) (unmaintained) -> FBCLI -> [Facebook CLI](https://github.com/specious/facebook-cli)
* __General__: Weboob -> [Rambox](https://github.com/saenzramiro/rambox) -> [Gwibber](http://gwibber.com/)
* __Pastebin__: [pastebinit](https://github.com/skorokithakis/pastebinit)
* __Reddit__: Reddit Comment Finder -> Cortex -> PRAW -> [cReddit](https://github.com/Cotix/cReddit) -> rtv
* __Slack__: [ScudCloud](https://github.com/raelgc/scudcloud) -> [slackterm](https://github.com/rob05c/slackterm)
* __Telegram__: Telegram Desktop -> ncTelegram -> telegram-cli -> Telegram-Purple
* __Twitter__: [Hotot](https://github.com/lyricat/Hotot) -> turses -> [oysttyer](https://github.com/oysttyer/oysttyer)
* __Youtube__: mps-youtube -> [youtube-viewer](https://github.com/trizen/youtube-viewer)

## Data
* __Data Mining and Business Intelligence__: [JasperReports](https://sourceforge.net/projects/jasperserver/) -> [KNIME](https://directory.fsf.org/wiki/KNIME) -> [GNU Ferret](https://directory.fsf.org/wiki/Ferret) -> [GURGLE](https://directory.fsf.org/wiki/Gurgle)
* __Data Parsing__: intltool -> XMLStarlet -> Flat file extractor (ffe)
* __Database (Datalog)__: [Datalog Educational System](http://des.sourceforge.net/), [Datalog](http://datalog.sourceforge.net/)
* __Database (Middleware)__: MySQL Workbench -> [Virtuoso Universal Server](https://virtuoso.openlinksw.com/) -> [Orbada](http://orbada.sourceforge.net/html/www_orbada_doc.html) -> [Autotable](https://directory.fsf.org/wiki/Autotable)
* __Database (NoSQL)__: [GZigZag](http://www.nongnu.org/gzz/), [RRDtool](https://oss.oetiker.ch/rrdtool/), [Dgraph](https://github.com/dgraph-io/dgraph), [Redis](https://directory.fsf.org/wiki/Redis), [GNU Recutils](https://directory.fsf.org/wiki/Recutils)
* __Database (SQL)__: MySQL -> Percona -> [MariaDB](https://directory.fsf.org/wiki/MariaDB) -> [CUBRID](https://github.com/CUBRID/cubrid) -> [Ingres II](https://github.com/fosslc/Ingres) -> ShellSQL
* __Enterprise Resource Planning (ERP)__: [IDempiere](http://www.idempiere.org/) -> [LedgerSMB](https://directory.fsf.org/wiki/LedgerSMB) -> [SQL-Ledger](http://www.sql-ledger.com/)
* __Expert System__: [CLIPS](http://clipsrules.sourceforge.net/) -> [Flora-2](http://flora.sourceforge.net/)
* __Financial Markets Monitoring__: [JStock](https://github.com/yccheok/jstock) -> [QtTrader](https://github.com/e99majo/qttrader) -> [Qtstalker](http://qtstalker.sourceforge.net/)
* __Full-Text Search__: Xapian -> Tokyo Dystopia -> Groonga
* __Human Resource Management__: [OrangeHRM](https://github.com/turnkeylinux-apps/orangehrm)
* __Invoicing__: [Simple Invoices](https://github.com/simpleinvoices/simpleinvoices)
* __Project Management__: [GanttProject](http://www.ganttproject.biz/)

## Decentralized Networking
* __Backbone Framework__: GNUnet -> OSF DCE (Distributed Computing Environment)
* __Chat__: Tox -> Matrix (Matrix-Ircd, Riot) -> [GNU Jami](https://jami.net/) -> eircd -> P2PIRC -> [nircd](https://github.com/Ronsor/nircd)
* __Darknet__: [autovpn](https://github.com/adtac/autovpn) -> LibreVPN -> Tor -> [AnoNet](http://anonet.org/) -> i2p
* __Digital Library__: [Aletheia](https://github.com/aletheia-foundation/aletheia-admin)
* __Distributed File Systems__: Samba -> NFS (nfs-utils) -> davfs2 -> Upspin -> IPFS
* __Distributed File Systems (Samba)__: SMB for FUSE (FuseSmb) -> SMBNetFS -> CIFS (cifs-utils)
* __DNS Resolution__:  [OpenNIC](https://www.opennic.org/) -> [Namecoin](https://namecoin.org/) -> [KadNode](https://github.com/mwarning/KadNode)
* __E-Commerce__: [OpenBazaar](https://github.com/OpenBazaar) + [FIX Agora](http://fixagora.sourceforge.net/) + [Bitnation](https://github.com/Bit-Nation) + [GNU Taler](https://taler.net/en/)
* __E-Commerce (Bitcoin)__: Qt Bitcoin Trader (Bitcoin Trader), Abe (Block Chain Browser)
* __E-Commerce (Bitcoin Wallet)__: Armory -> Bitcoin Core -> Monero
* __E-Mail__: Notbit (Bitmessage)
* __Forum__: [Decentraland](https://decentraland.org/) -> GNU Social (Pleroma, Mastodon) -> Syndie -> [NNTPChan](https://github.com/majestrate/nntpchan)
* __Gossip Network (Network Service Discovery)__: [peernet](https://github.com/substack/peernet)
* __Grid Computing__: traceroute@home -> [BOINC](https://github.com/BOINC/boinc) (+ [boinctui](https://github.com/suleman1971/boinctui))
* __Media Hosting__: [MediaGoblin](https://mediagoblin.org/) -> [Alexandria](http://www.alexandria.io/) (not ready yet but [this how it works](https://www.youtube.com/watch?v=So4n2ZBSMxg)) -> [ipfs.pics](https://github.com/ipfspics/ipfspics-server)
* __Mesh Network__: Tinc -> cjdns -> BMX6 -> open80211s (802.11s) -> [B.A.T.M.A.N.](https://www.open-mesh.org/projects/open-mesh/wiki)
* __Monetary Incentives__: [Storj](https://storj.io/) + [Gridcoin](https://gridcoin.us/) + [Stream Token](https://github.com/streamproject/stream-chrome)
* __Network Block Device__: Usbredir -> nbd
* __Search Engine__: searx -> [Seeks](https://beniz.github.io/seeks/) -> [YaCy](https://www.yacy.net/en/) (truly decentralized, would be wonderful if searx/seeks could feed its data to YaCy)
* __Search Engine (Gopher)__: [Jugtail](http://www.nongnu.org/jugtail/)
* __Search Engine (Torrents)__: Magnetissimo -> [magnetico](https://github.com/boramalper/magnetico)
* __Streaming__: [Butter Project](http://butterproject.org/) -> [Livepeer](https://livepeer.org/) -> [PeerTube](https://instances.joinpeertube.org/instances)
* __Version Control (Decentralized Github)__: [git-annex](https://git-annex.branchable.com/) (+ git-annex assistant) -> [GitTorrent](https://github.com/mfyuce/GitTorrent)
* __VPN__:  n2n -> [PeerVPN](https://github.com/peervpn/peervpn)
* __Wiki__: [ikiwiki](https://ikiwiki.info/tips/distributed_wikis/)

## Emulation And Virtualization
* __Containers__: sandbox -> fakechroot -> FakeRoot -> PRoot -> chroot -> containerd -> OpenVZ -> User-mode Linux (UML) -> LXC -> [Linux-VServer](http://linux-vserver.org/Welcome_to_Linux-VServer.org) -> containers
* __Emulators__: Systemd/Linux: [systemd-shim](https://directory.fsf.org/wiki/Systemd-shim), Windows: Wine (+ [Wine Staging](https://github.com/wine-compholio/wine-staging)), Android: [Anbox](https://github.com/anbox/anbox), OS X: [Darling](https://www.darlinghq.org/), Atari: [Hatari](http://hatari.tuxfamily.org/) (16/32-bit) and [Atari800](https://atari800.github.io/) (8-bit), CP/M: cpm (+ cpmtool), Spectrum: FBZX, Commodore: [VICE](http://vice-emu.sourceforge.net/), DOS: DOSBox
* __Hypervisors__: Xen -> [NOVA](http://hypervisor.org/) -> KVM
* __Network Virtualization__: GNS3 -> [nsnam](https://github.com/nsnam/ns-3-dev-git)
* __Video Game Console Emulation (ATARI)__: [Stella](https://stella-emu.github.io/)
* __Video Game Console Emulation (XBOX)__: [XQEMU](https://github.com/espes/xqemu)
* __Video Game Console Emulation (MULTIPLE)__: Higan -> Mednafen -> RetroArch -> [MAME](https://github.com/mamedev/mame) -> [AdvanceMAME](https://github.com/amadvance/advancemame) [(framebuffer support)](https://forum.odroid.com/viewtopic.php?f=116&t=11662)
* __Video Game Console Emulation (NINTENDO)__: FCEUX/Citra, [DeSmuME (Nintendo DS)](https://github.com/TASVideos/desmume/), [Mupen64Plus (Nintendo 64)](https://github.com/mupen64plus/mupen64plus-core), [Dolphin (GameCube and Wii)](https://dolphin-emu.org/)
* __Video Game Console Emulation (SCUMM)__: ScummVM
* __Video Game Console Emulation (SEGA)__: Gens/GS, Exodus, [Yabause (Sega Saturn)](https://github.com/Yabause/yabause), Lxdream, [Reicast (Dreamcast)](https://github.com/reicast/reicast-emulator)
* __Video Game Console Emulation (PLAYSTATION)__: [PPSSPP](https://github.com/hrydgard/ppsspp), [RPCS3](https://github.com/rpcs3/rpcs3/), [PCSX2](https://github.com/PCSX2/pcsx2)
* __Virtual Assembler__: [GNUSim8085](http://pages.cs.wisc.edu/~larus/spim.html), [spim](http://pages.cs.wisc.edu/~larus/spim.html)
* __Virtual Machine__: VirtualBox -> [AQEMU](https://github.com/tobimensch/aqemu) + kvm -> Qemu + kvm -> Bochs
* __Virtual Machine (IBM Mainframes)__: [Hercules](http://www.hercules-390.org/)
* __Virtual Machine (DEC)__: [SIMH](http://simh.trailing-edge.com/)

## File Utilities
* __Batch Renamer__: Metamorphose -> [GPRename](http://gprename.sourceforge.net/) -> vidir -> [qmv (renameutils)](http://www.nongnu.org/renameutils/) -> mmv
* __Duplicate Files Removal__: [dupeGuru](https://github.com/hsoft/dupeguru) -> FSlint -> freedup -> fdmf -> dupmerge -> duff -> [Fdupes](https://github.com/adrianlopezroche/fdupes) -> jdupes -> rmlint
* __File Archiver__: PeaZip -> Xarchiver -> Patool -> dtrx -> [Atool](http://www.nongnu.org/atool/) -> dar -> tar -> pax
* __File Compression__: arj, Zstandard (Zstd), Zip, lzop, Plzip, pxz, ECM (Error Code Modeler), p7zip, lbzip2, lrzip, pigz
* __File Conversion__: nrg2iso, dmg2iso (dmg to iso), mdf2iso (mdf to iso), daa2iso (daa to iso), UIF2ISO (uif to iso), ccd2iso (img to iso), bin2iso (bin-cue to iso), [bchunk](http://he.fi/bchunk/) (bin-cue to iso), mpq-tools (MPQ or MoPaQ), Macutils
* __File De-Compression Only__: unace, cabextract, unrar, Lunzip, UnZip
* __File Manager__: PCManFM -> Xfe -> SpaceFM -> [File System Visualizer](https://github.com/mcuelenaere/fsv) ([“It’s a Unix system, I know this!”](https://www.youtube.com/watch?v=dxIPcbmo1_U)) -> Endeavour Mark II -> donnatella -> worker (+ imagemagick) -> [Moxfm](https://github.com/ThomasAdam/moxfm) -> Emacs (Dired Plus Mode, Sunrise Commander, ranger.el, Image-Dired, ThumbsMode) -> Ranger -> Midnight Commander -> [vifm](https://wiki.vifm.info/index.php?title=How_to_preview_images) -> [FDclone](http://hp.vector.co.jp/authors/VA012337/soft/fd/) -> [Ytree](https://directory.fsf.org/wiki/Ytree) -> rover -> CLEX -> [nnn](https://github.com/jarun/nnn) -> [tree](https://directory.fsf.org/wiki/Tree)
* __File Search__: Beagle -> [Puggle](http://puggle.sourceforge.net/) -> [ANGRYsearch](https://github.com/DoTheEvo/ANGRYsearch) -> Tracker -> [DocFetcher](http://docfetcher.sourceforge.net/en/index.html) -> [regain](http://regain.sourceforge.net/index.php) -> lightmediascanner -> find
* __File Synchronization__: [Unison](https://github.com/bcpierce00/unison) -> duplicity -> synk -> Rsync
* __Pictures Organizer__: hydrus network -> Shotwell -> GTKRawGallery -> digiKam -> gThumb (+ gphoto) -> [Mapivi](http://mapivi.sourceforge.net/mapivi.shtml) -> [BASH-Booru](https://github.com/ChristianSilvermoon/BASH-Booru)
* __RegEx Builder__: [regexxer](https://directory.fsf.org/wiki/Regexxer) -> [Visual REGEXP](http://laurent.riesterer.free.fr/regexp/) -> [txt2regex](https://github.com/aureliojargas/txt2regex)

## Filesharing
* __Direct Connect__: LinuxDC++ -> [ncdc](https://github.com/srijan/ncdc) -> [microdc2](http://corsair626.no-ip.org/microdc/)
* __Download Manager__: [JDownloader](https://github.com/Bobmk/JDownloader) -> [giFT](https://sourceforge.net/projects/gift/) (+ [giFTcurs](http://www.nongnu.org/giftcurs/)) -> [aria2](https://aria2.github.io/) -> cURL -> Wget -> snarf -> Axel
* __File Scraper__: [Grive2](https://github.com/vitalif/grive2) (Google Drive) -> megatools (Mega) -> [Rclone](https://github.com/ncw/rclone) -> [Plowshare](https://github.com/mcrapet/plowshare)
* __FTP Client__: FileZilla -> [lftp](https://github.com/lavv17/lftp) -> NcFTP
* __LAN Sharing__: NitroShare -> Dukto
* __Media Miner__: FlexGet -> [Sonarr](https://github.com/Sonarr/Sonarr)
* __Soulseek__: Nicotine Plus -> [Museek (mucous)](https://museek-plus.org/)
* __Torrent Client__: qBittorrent -> RTorrent -> transmission-daemon ([web interface](https://github.com/transmission/transmission/wiki/Web-Interface) by default, [other frontends](https://github.com/fagga/transmission-remote-cli) optional) -> CTorrent -> btpd + mktorrent
* __Torrent Tracker Scraper__: [Torrtux](https://github.com/l333k0/torrtux) -> [Torrench](https://github.com/kryptxy/torrench) -> [Jackett](https://github.com/Jackett/Jackett)
* __Usenet (File Grabber)__: LottaNZB -> SABnzbd -> [NZBGet](https://github.com/nzbget/nzbget) -> [nzb](https://directory.fsf.org/wiki/Nzb) -> [nzbperl](https://github.com/eghm/nzbperl)
* __x-y-zmodem__: lrzsz

## Forensics
* __Application Profiling__: CGprof -> Valgrind (+ Callgrind)
* __Browser Debugger__: Firebug
* __Debugger__: DDD -> [CGDB](https://cgdb.github.io/) -> OpenOCD -> GDB
* __Delta Encoding__: xdelta -> Bsdiff
* __Forensic Analysis Framework__: The Sleuth Kit -> DFF -> Radare
* __Hex Editors__: [HT Editor](http://hte.sourceforge.net/) -> biew -> [dhex](https://directory.fsf.org/wiki/DHEX) -> hexedit
* __Java Profiling__: VisualVM -> Quilt
* __Memory Scanner (Cheat Engine)__: scanmem & Gameconqueror -> [varedit](https://github.com/asherlie/varedit)
* __Sandbox__: [Cuckoo Sandbox](https://cuckoosandbox.org/)
* __Steganalysis__: [Virtual Steganographic Laboratory](http://vsl.sourceforge.net/) -> [Stegdetect](https://github.com/abeluck/stegdetect)

## Hardware
* __Cameras__: ZoneMinder (CCTV), Motion (motion detection), gPhoto (connecting digital cameras), ccdciel
* __Car (as in automobile)__: can-utils
* __CD-DVD Burn and Copy (Backends)__: cdrtools -> cdrkit -> [cdrskin](https://dev.lovelyhq.com/libburnia/web/wikis/cdrskin)
* __CD-DVD Burn and Copy (Frontends)__: K3b -> Brasero -> dvd+rw-tools -> xorriso -> [cdw](http://cdw.sourceforge.net/)
* __CD-DVD Cue Files__: cuetools -> cuecmd
* __CD-DVD Information__: cd-discid -> cdstatus
* __CD-DVD Ripping__: Sound Juicer -> fre ac -> [cdparanoia](https://www.xiph.org/paranoia/) (+ [ABCDE](http://lly.org/~rcw/abcde/page/))
* __Data Recovery__: fatcat -> ext3grep -> giis (gET iT i sAY) -> extundelete -> Magic Rescue -> dvdisaster -> TestDisk (PhotoRec) -> ddrescue 
* __Device Management (and module autoloader)__: evdev -> udev -> vdev
* __Disk Cloning and Writing__: devio -> dd -> dcfldd -> [dc3dd](https://sourceforge.net/projects/dc3dd/)
* __Display Color Temperature__: Redshift -> [sct](https://github.com/mgudemann/sct) -> luminous
* __Display Settings__: xrandr -> DDCcontrol -> fbset
* __Displays (Miracast)__: MiracleCast
* __Hardware Bus__: multipath-tools, I2C Tools (i2c-tools), IPMI Tool (ipmitool, ipmiutil) (IPMI DANGEROUS IF ENABLED)
* __Hardware RAID__: mdadm -> dmraid
* __Hibernation__: [TuxOnIce](https://github.com/NigelCunningham/tuxonice-kernel) -> [uswsusp](http://suspend.sourceforge.net/) -> pm-utils -> shutdownasap -> watchdog
* __Home Automation__: LinuxMCE
* __Keyboard Bindings__: Xbindkeys -> sxhkd -> bind (readline) -> loadkeys (+ keymaps)
* __Keyboard Input Language__: iBus -> SCIM -> Fcitx -> uim (+ Anthy)
* __Keyboard Layout__: XKB -> xmodmap -> KBD
* __Media Transfer Protocol (MTP)__: MTPfs -> jmtpfs -> simple-mtpfs
* __Microcontrollers__: AVRDUDE
* __Mounting__: AcetoneISO -> Udisks (+ udevil) -> Lightweight Device Mounter (ldm) -> USBmount -> pmount -> [bashmount](https://github.com/jamielinux/bashmount/blob/master/INSTALL) -> mount (.ISO files too) -> udev rules
* __Mouse__: xbanish -> [keynav](https://github.com/jordansissel/keynav) -> GPM
* __Power Management__: tpfancontrol -> tpacpi-bat -> thinkfan -> [TLP](https://github.com/linrunner/TLP) -> [PowerTOP](https://github.com/fenrus75/powertop) -> [Powertweak](https://directory.fsf.org/wiki/Powertweak-Linux)
* __Printers__: CUPS -> [LPR](http://www.lprng.com/)
* __Scanners__: Scanner Access Now Easy (SANE)
* __Software-defined radio (SDR)__: [GNU Radio](https://github.com/gnuradio) (+ [Gqrx](https://github.com/csete/gqrx)) -> [rtl-sdr](https://github.com/osmocom/rtl-sdr)
* __Telescope__: Talon
* __Tv (DVR)__: xawtv -> tvtime
* __Tv (Multicast)__: udpxy -> IGMPproxy
* __Undevolting and Power Saving__: [TurionPowerControl](https://code.google.com/archive/p/turionpowercontrol/) -> [Linux-PHC](http://www.linux-phc.org/forum/) -> [cpufrequtils](https://mirrors.edge.kernel.org/pub/linux/utils/kernel/cpufreq/) -> [cpupower](https://github.com/torvalds/linux/tree/master/tools/power/cpupower) -> schedtool
* __UPS__: egctl -> Network UPS Tools (NUT) -> [apcupsd](http://www.apcupsd.org/)

## Monitoring
### Benchmarking
* __Drive Profiling__: Smartmontools -> fio -> sdparm -> hdparm
* __Filesystem Benchmark__: IOzone -> [Bonnie++](https://www.coker.com.au/bonnie++/) -> [MBW](https://github.com/raas/mbw)
* __General Benchmarking__: collectd -> Phoronix Test Suite -> [HPC Challenge Benchmark (hpcc)](http://icl.cs.utk.edu/hpcc/) -> mcelog -> ProcBench -> [Sysbench](https://github.com/akopytov/sysbench)
* __Network Data Visualization__: [weathermap4rrd](http://weathermap4rrd.tropicalex.net/) (rrd) -> [Xtract](https://sourceforge.net/projects/netxtract/) (pcap)
* __Network Profiling__: [net-snmp](http://net-snmp.sourceforge.net/) -> [vnStat](https://github.com/vergoh/vnstat) -> [iperf](http://software.es.net/iperf/) -> bing
* __Server Benchmark__: [Siege](https://github.com/JoeDog/siege)
* __Sort Benchmark__: gensort
* __System Tracing__: SystemTap -> LTTng -> OProfile -> Sysdig -> dtrace -> [strace](https://github.com/strace/strace) -> [trace-cmd](https://git.kernel.org/pub/scm/linux/kernel/git/rostedt/trace-cmd.git) (ftrace) -> perf + FlameGraph

### System Information
* __General Information__: zCI -> [inxi](https://smxi.org/docs/inxi.htm)
* __Hardware Information__: vdpauinfo -> [lshw](https://github.com/lyonel/lshw) -> [hwloc](https://www.open-mpi.org/projects/hwloc/) -> lsscsi -> edac-utils -> [usbutils (lsusb)](https://github.com/gregkh/usbutils) -> [pciutils (lspci)](http://mj.ucw.cz/sw/pciutils/) -> util-linux (lsblk, blkid, dmesg) -> [acpitool](https://directory.fsf.org/wiki/AcpiTool) [dmidecode](http://dmidecode.nongnu.org/)
* __Screenshot Information (Bash)__: [Neofetch](https://github.com/dylanaraps/neofetch) -> [screenFetch](https://github.com/KittyKatt/screenFetch) -> envee
* __Screenshot Information (C)__: [Linux_Logo](https://github.com/deater/linux_logo)
* __Screenshot Information (Perl)__: screenfo -> alsi
* __Software Information__: [vrms](https://github.com/z411/vrms-gentoo) -> file -> ldd -> lsb_release -> os-prober -> uname (GNU Coreutils)

### System Monitoring
* __Database Monitoring__: [Mytop](https://github.com/jzawodn/mytop)
* __Disk Usage__: QDirStat -> [Baobab](http://www.marzocca.net/linux/baobab/) -> xdiskusage -> XDU -> dfc -> [Ncdu](https://dev.yorhel.nl/ncdu) -> ls++ -> tdu -> ncdt -> du + df (GNU coreutils)
* __Geolocation__: [Prey](https://github.com/prey/prey-bash-client)
* __Hardware Monitoring__: lm-sensors (psensor for a GUI) -> [CrazyDiskInfo](https://github.com/otakuto/crazydiskinfo) -> Hddtemp
* __Log Monitoring__: Webalizer -> lnav -> [Logcheck](http://logcheck.org/) -> [multiTail](https://github.com/flok99/multitail)
* __Log Visualizer__: glTail -> [Logstalgia](https://github.com/acaudwell/Logstalgia) -> ccze
* __Network Flow__: Argos -> HFlow -> [nfdump](https://github.com/phaag/nfdump) ([nfsen](http://nfsen.sourceforge.net/) for a GUI)
* __Network Latency__: [OpenNMS](https://github.com/OpenNMS/opennms) -> [SmokePing](https://github.com/oetiker/SmokePing) -> [bmon](https://github.com/tgraf/bmon)
* __Network Monitoring__: IPTraf -> tcptrack -> IPTState -> [NetHogs](https://github.com/raboof/nethogs) -> [iftop](http://www.ex-parrot.com/pdw/iftop/), [dnstop](http://dns.measurement-factory.com/tools/dnstop/)
* __Port Monitoring__: [psad](https://directory.fsf.org/wiki/Port_Scan_Attack_Detector)
* __Process Monitoring__: [lsof](https://people.freebsd.org/~abe/), [PSmisc](https://directory.fsf.org/wiki/Psmisc) (fuser, pkill, pstree)
* __Serial Monitoring__: [slsnif](https://github.com/aeruder/slsnif) -> interceptty -> [ttylog](https://github.com/rocasa/ttylog)
* __System Latency__: [LatencyTOP](https://github.com/namhyung/latencytop)
* __System Monitor__: gnome-system-monitor -> [psDooM](https://github.com/keymon/psdoom-ng) -> HardInfo -> GKrellM -> treeps -> Conky -> xosview -> Glances -> dstat -> atop -> htop -> [nmon](http://nmon.sourceforge.net/pmwiki.php) -> procinfo -> [Sysstat](https://directory.fsf.org/wiki/Sysstat) (sar, mpstat, pidstat, iostat, sadf) -> [procps](https://directory.fsf.org/wiki/Procps) (ps, free, vmstat, top, pmap, nice)
* __User Monitoring__: [wuzzah](https://www.cs.swarthmore.edu/~finney/proj/wuzzah/) -> [Whowatch](https://github.com/mtsuszycki/whowatch/) -> [acct](http://savannah.gnu.org/projects/acct/)
* __Web Log Analytics__: [AWStats](http://www.awstats.org/) -> [W3Perl](http://www.w3perl.com/) -> [Analog](http://www.web42.com/analog/) -> [pmacct](https://github.com/pmacct/pmacct)
* __Web State Monitor__: Nagios (+ NagVis) -> Sysmond -> [sysmon](https://web.archive.org/web/20070602050243/http://pubpages.unh.edu/~pas/hacks/sysmon/)
* __Wi-Fi Network Monitor__: wavemon

## Multimedia
### ASCii Art
* __ANSI Drawing__: [MysticDraw](https://archive.org/details/tucows_8499_Mystic_Draw) -> [SHPaint](http://bruxy.regnet.cz/web/linux/EN/ansi-art-sh-paint/)
* __ANSi Viewer__: [ANSiMat](https://sourceforge.net/projects/ansimat/)
* __ASCii Animation__: blessed -> Durdraw -> drawille
* __ASCii Banner__: shellpic -> TOIlet -> FIGlet -> sysvbanner
* __ASCii Drawing__: JavE -> Aewan -> cadubi -> [CAVE WALL](http://www-users.mat.umk.pl/~mckuk/cavewall/) -> textdraw
* __ASCii Presentations__: wopr -> blessed-contrib
* __Image to ASCii__: jp2a
* __Video to ASCii__: libcaca -> AAlib

### Audio
* __Audio Editing__: Audacity -> Snd -> [Ecasound](https://directory.fsf.org/wiki/Ecasound) -> [SoX](http://sox.sourceforge.net/)
* __Audio Effect Plugins__: awesfx (SoundFont), Vamp, [zam-plugins](http://www.zamaudio.com/?p=870) (LADSPA/LV2/VST/JACK), [LV2](http://lv2plug.in/) (x42-plugins), [LADSPA](http://ccrma.stanford.edu/planetccrma/software/ladspaworld.html) (tap-plugins), [DSSI](http://dssi.sourceforge.net/) (dssi-utils, dssi-vst), ALSA plugins (alsa-plugins)
* __Background Sound__: GNU GTick -> Ambient Noise -> ctronome
* __Digital Audio Workstation__: Rosegarden -> Ardour -> LMMS
* __DJing__: Mixxx
* __Ear Training__: LenMus -> GNU Solfege
* __Multiple Audio Streams__: pulseaudio -> [apulse](https://github.com/i-rinat/apulse) -> ALSA (aloop, Softvol, Dmix)
* __Music Player__: Audacious (+ [Winamp Classic skin](https://www.gnome-look.org/content/show.php/Winamp+Classic+skin+for+Audacious?content=135799) + GJay) -> Clementine -> [Open Cubic Player](http://stian.cubic.org/project-ocp.php) -> MPD (vimus/ncmpcpp) -> cmus -> [mp3blaster](http://www.mp3blaster.org/) (runs with "aoss mp3blaster" or compiled with ALSA) -> MikMod -> [MOC](http://moc.daper.net/) (+ moc-ffmpeg-plugin, [dmenu_mocp](https://github.com/pscha/dmenu_mocp)) -> simple audio daemon (sad)
* __Music Visualization__: [Spectrum3d](http://spectrum3d.sourceforge.net/) -> [Le Biniou](https://directory.fsf.org/wiki/Lebiniou) -> [projectM](http://projectm.sourceforge.net/) -> cava -> [cli-visualizer](https://github.com/dpayne/cli-visualizer)
* __Scorewriter__: MuseScore -> LilyPond -> eTktab -> Emacs (lyqi) -> Philip's Music Writer (pmw) -> ABCmidi (abcpp + abc2prt + abcm2ps)
* __Software Sampler__: LinuxSampler -> orDrumbox -> [Hydrogen](http://www.hydrogen-music.org/hcms/)
* __Synthesizer__: AlsaModularSynth -> [ZynAddSubFX](http://zynaddsubfx.sourceforge.net/) -> FluidSynth (+ SoundFonts)
* __System Sound Compatibility__: [WineASIO](https://sourceforge.net/projects/wineasio/), oss2jack, oss-compat, alsa-oss
* __System Sound Extensions__: pulseaudio -> Jack (jack, jack-audio-connection-kit) -> ESound (esound-common)
* __System Sound Utilities__: pavucontrol (pulseaudio) -> JACK Rack (for Jack) -> JAMin (for Jack) -> Qastools -> gnome-alsamixer -> aumix -> Rexima -> ALSA tools (alsa-tools, alsa-tools-gui) -> [Alsaequal](https://directory.fsf.org/wiki/Alsaequal) -> [alsa-utils](https://github.com/gittup/alsa-utils) (alsamixer, amixer, aplay, arecord)
* __Tonal Feature Analysis__: [CLAM Chordata](http://clam-project.org/) -> Sonic-> Spek -> Pause
* __Tracker Editors__: [MilkyTracker](https://github.com/milkytracker/milkytracker) -> [Schism](https://github.com/schismtracker/schismtracker)
* __Trackers__: [SID-Wizard](http://csdb.dk/release/?id=131846) -> [GoatTracker](https://sourceforge.net/projects/goattracker2/)
* __Tray Icon__: Volume Icon -> Volti

### Image
* __Bitmaps to Vector Conversion__: AutoTrace -> [Potrace](https://directory.fsf.org/wiki/Potrace)
* __Diagram Editor__: Pencil Project -> Dia -> Graphviz
* __Digital Drawing (Bitmap Graphics)__: Krita -> MyPaint -> Xournal -> [XPaint](https://directory.fsf.org/wiki/Xpaint) -> [GrafX2](http://grafx2.chez.com/) / [uberpaint](https://github.com/trapd00r/uberpaint)
* __Digital Drawing (Coloring)__: OpenColorIO -> deepcolor -> STYLE2PAINTS
* __Digital Drawing (Fonts)__: FontForge
* __Digital Drawing (Vector)__: Inkscape -> [Xfig](http://mcj.sourceforge.net/) -> gozer -> ImageMagick
* __Fonts Conversion__: bdftopcf, PSF Tools, pcf2bdf, otf2bdf, bdf2psf
* __Fractals and Random Computer Artwork__: [Mandelbulber](https://github.com/buddhi1980/mandelbulber2) -> Fyre -> Wassily
* __Image Editing__: RawTherapee -> darktable -> Gimp -> Netpbm -> [G'MIC](https://github.com/dtschump/gmic) -> GraphicsMagick -> ImageMagick (display, import) -> Gifsicle
* __Image Optimizing__: OptiPNG -> pngcrush -> pngquant
* __Image Viewer__: Feh -> sxiv -> zgv -> lsix -> sdump -> display (ImageMagick) -> [fim](http://www.nongnu.org/fbi-improved/) / [fbi (fbida)](https://github.com/fcarlier/fbida) -> idump
* __Plotting__: Gnuplot -> Ngraph-gtk -> ygraph -> [PLplot](http://plplot.sourceforge.net/) -> FRTPLOT -> Picviz
* __Screenshots__: Shutter -> scrot -> maim -> shot.sh -> import (ImageMagick) -> [fbcat](https://github.com/jwilk/fbcat) (FBGrab)

### Metadata
* __Metadata__: [Easytag](https://wiki.gnome.org/Apps/EasyTAG) -> [Beets](https://github.com/beetbox/beets) -> MAT -> Exiv2 -> MediaInfo -> viexif -> [ExifTool](http://exiftool.sourceforge.net/) -> exif

### Video
* __Compositing__: [CinePaint](http://www.cinepaint.org/) -> [Natron](https://github.com/MrKepzie/Natron)
* __Datamoshing__: [Autodatamosh](https://github.com/grampajoe/Autodatamosh)
* __Digital Animation (2D)__: [Synfig](https://www.synfig.org/) -> [OpenToonz](https://github.com/opentoonz/opentoonz)
* __Digital Animation (3D)__: Blender
* __Flash Player__: Lightspark -> Gnash
* __HDR (High-Dynamic-Range)__: pfstools
* __Screencasting__: Open Broadcaster Studio -> SimpleScreenRecorder -> XVidCap -> glc -> [FFmpeg](https://www.linuxquestions.org/questions/linux-general-1/record-using-framebuffer-video-grabber-4175464119/) -> [ttyrec](https://github.com/mjording/ttyrec) (+ [seq2gif](https://github.com/saitoha/seq2gif))
* __Video Editing__: Kdenlive -> Avidemux -> OpenShot -> Cinelerra-cv -> [Melt](https://www.mltframework.org/docs/melt/) -> [AvxSynth](https://github.com/avxsynth/avxsynth) -> blind -> FFmpeg
* __Video Effects Plugins__: Frei0r
* __Video Player__: nvlc (VLC) -> MPV -> [MPlayer](https://mplayerhq.hu) -> fbff -> ffplay
* __Video to gif__: Video2Gif -> QGifer -> convert (ImageMagick) -> FFmpeg
* __Video Transcoding__: [HandBrake](https://handbrake.fr/) -> WinFF -> FFmpeg / avconv

## Network Setup
* __Bandwidth Saver__: [Wondershaper](https://github.com/mayfrost/wondershaper)
* __Bandwidth Testing__: [speedtest-cli](https://github.com/sivel/speedtest-cli) -> [speed-test](https://github.com/sindresorhus/speed-test)
* __Bluetooth__: btmgmt -> Bluez-tools
* __DHCP Client__: dhclient -> dhcpcd
* __DNS Encryption__: DNSSEC, DNSCrypt
* __DNS Resolution__: dnsmasq -> Unbound + NDS -> BIND9 -> djbdns
* __MAC Manipulation__: [GNU MAC Changer (macchanger)](https://github.com/alobbs/macchanger)
* __Network Encryption__: OpenSSL -> [LibreSSL](https://directory.fsf.org/wiki/Libressl) -> GnuTLS -> IPsec / [SAE](https://github.com/cozybit/authsae) (802.11s)
* __Network Manager__: Wicd -> NetworkManager -> ConnMan -> [SetNet](http://kalos.mine.nu/setnet/)
* __Networking Tools__: WvDial -> [ethtool](https://mirrors.edge.kernel.org/pub/software/network/ethtool/) -> iproute2 (ip, ss) -> [net-tools](https://github.com/ecki/net-tools) (ifconfig, netstat)
* __Point-to-Point Protocol__: Point-to-Point Protocol daemon
* __Wireless Tools__: rfkill, iw -> [Wireless Tools for Linux](https://hewlettpackard.github.io/wireless-tools/Tools.html), iwd -> [wpa_supplicant](https://w1.fi/wpa_supplicant/)

## Office
* __Address book__: abook
* __Desktop Publishing__: Scribus
* __Dictionary__: Goldendict -> Artha -> [Dico](https://directory.fsf.org/wiki/Dico), [dict](http://www.dict.org/w/software/software) -> wtf
* __Document Format Conversion__: unoconv -> Pandoc -> Yodl -> GNU a2ps -> inf2manp
* __Document Processor__: Emacs (AUCTeX) -> LyX -> [GNU TeXmacs](http://texmacs.org/tmweb/home/welcome.en.html)
* __Ebook Utilities__: DeDRM_tools
* __Ebook Utilities (CHM)__: xCHM -> [CHMLib](http://www.jedrea.com/chmlib/) (extract_chmLib)
* __Ebook Utilities (Epub)__: Ebook Tools (ebook-tools)
* __Ebook Utilities (PDF)__: [PDF SaM](https://github.com/torakiki/pdfsam) -> Poppler -> PDFtk
* __Ebook Utilities (PostScript)__: PSUtils -> ghostscript
* __Ebook Viewer__: Calibre -> Okular -> Zathura -> JFBView / [fimgs (fim)](http://www.nongnu.org/fbi-improved/) / [fbgs (fbida)](https://www.kraxel.org/blog/linux/fbida/) / fbpdf
* __Flashcards__: awk flashcards -> Anki
* __Gamification__: HabitRPG -> Habitica
* __Mind Mapping__: FreeMind
* __Office Suites__: LibreOffice -> [Siag Office](http://siag.nu/) -> [catdoc](https://github.com/petewarden/catdoc) (xls2csv, catppt, wordview)
* __Outliner__: [TreeSheets](https://github.com/aardappel/treesheets) -> Vault 3 -> GJots2 -> TuDu -> Emacs (Org-mode) -> Vim (Vimoutliner or Vim-orgmode) -> [hnb](http://hnb.sourceforge.net/Screen-shots/) -> snb
* __Personal Accounting__: GnuCash -> Ledger -> [GNU Pem](https://www.gnu.org/software/pem/)
* __Personal Assistant__: [Mycroft](https://mycroft.ai/) -> Lucida (aka Sirius) -> [betty](https://github.com/pickhardt/betty)
* __Personal Organizer__: Task Coach -> Wyrd -> wtf -> Taskwarrior -> [calcurse](https://directory.fsf.org/wiki/Calcurse) -> todo.txt-cli -> when -> cal
* __Presentation__: Beamer -> Sozi -> [Text Presentation Program](https://github.com/akrennmair/tpp)
* __Repetitive Strain Injury__: [Workrave](https://directory.fsf.org/wiki/Workrave)
* __Speed Reading__: Flinks -> WordFlashReader -> GnomeRSVP -> spread0r -> [speedread](https://github.com/pasky/speedread)
* __Spell Check__: Ispell -> [Aspell](https://directory.fsf.org/wiki/Aspell)
* __Spreadsheets__: Libreoffice Calc -> Gnumeric -> Oleo -> [SC-IM](https://github.com/andmarti1424/sc-im)
* __Text Editor__: Vim -> Nano -> Neovim -> Kakoune -> vile -> mg -> [GNU Zile](https://directory.fsf.org/wiki/GNU_Zile) (minimalist Emacs clone) -> nvi -> [Elvis](https://github.com/mbert/elvis) (minimalist Vi clone) -> ed
* __Text Editor (IDE)__: Atom -> NetBeans -> Code Blocks -> Emacs (nox) -> Vim -> [xwpe](https://github.com/amagnasco/xwpe) (full IDE in the terminal)
* __Text Encoding__: fuse-convmvfs, Dos2Unix, ASCII
* __Text Formatting and Pretty Printing__: par -> fmt (Textutils) -> MSORT
* __Text-To-Speech__: Orca -> Gespeaker -> [eBook-speaker](https://directory.fsf.org/wiki/EBook-speaker) (+ pandoc) -> [eSpeak](https://github.com/espeak-ng/espeak-ng/)
* __Typesetting__: LaTeX -> Texinfo + Pinfo -> Discount (Markdown) -> AFT -> [groff (tbl, pic, eqn, chem, music, dpic, grohtml)](https://www.troff.org/prog.html)
* __Typing Training__: Klavaro -> nlkt -> [GNU Typist](https://www.gnu.org/software/gtypist/)
* __Word Processor__: LibreOffice Writer -> Abiword -> MinEd -> [WordGrinder](http://cowlark.com/wordgrinder/)

## Package Management
* __CD/USB (Custom Installer)__: Respin -> Remastersys -> Distroshare -> PinguyBuilder -> Customizer -> Ubuntu Customization Kit -> Mklivecd
* __CD/USB (Live)__: UNetbootin -> [MultiCD](https://multicd.us/)
* __Gaming Platform__: [LGOGDownloader](https://github.com/Sude-/lgogdownloader) (GOG.com), [SteamCMD](https://linode.com/docs/game-servers/install-steamcmd-for-a-steam-game-server/) (Steam), [Lutris](https://github.com/lutris/lutris), Gelide
* __Language Specific__: [bpkg](https://www.bpkg.sh/) (Bash scripts) -> CPAN (+ [Pinto](https://metacpan.org/release/Pinto)) (Perl) -> [clib](https://github.com/clibs/clib) (C)
* __Package Creation__: [OBS](http://openbuildservice.org/) (Open Build Service) -> src2pkg -> CheckInstall -> [GNU Stow](https://directory.fsf.org/wiki/Stow) -> lt
* __Portable Apps__: Flatpak -> Snappy -> [AppImage](https://github.com/AppImage)
* __System Backup__: [Systemback](https://sourceforge.net/projects/systemback/) -> [Bacula](https://blog.bacula.org/) -> [FSArchiver](http://www.fsarchiver.org/) -> [CYA](https://www.cyberws.com/bash/cya/)
* __Universal Package Managers__: [Alien](https://joeyh.name/code/alien/) -> LinuxBrew -> pkgsrc -> GNU Guix

## Pentesting
### Exploitables
* __Distros__: [Security Scenario Generator (SecGen)](https://github.com/cliffe/SecGen) -> [Damn Vulnerable Linux](https://sourceforge.net/projects/virtualhacking/files/os/dvl/) -> [Metasploitable](https://www.offensive-security.com/metasploit-unleashed/Requirements/) -> [Kioptrix](http://www.kioptrix.com/blog/)
* __Web Apps__: [Mutillidae](https://sourceforge.net/projects/mutillidae/) -> [hackxor](http://hackxor.net/) -> [WebGoat](https://www.owasp.org/index.php/Category:OWASP_WebGoat_Project)

### Network Scan
* __Bluetooth__: btscanner -> bluesniff
* __DNS Client__: [whois](https://github.com/rfc1036/whois), [dnsenum](https://github.com/fwaeytens/dnsenum), [dnstracer](https://directory.fsf.org/wiki/Dnstracer), slookup, bind-tools (nslookup, host, dig)
* __Link Scanner__: [Metagoofil](https://github.com/laramies/metagoofil) -> LinkChecker -> [Linklint](http://www.linklint.org/) (+ [linklint2dot](http://www.deltadevelopment.de/users/christoph/linklint2dot/))
* __Network Enumeration__: [SSLScan](https://github.com/rbsec/sslscan), xprobe2, [p0f](https://github.com/p0f/p0f), WhatWeb, [PRADS](https://gamelinux.github.io/prads/)
* __Network File Retrieval__: [Driftnet](https://github.com/deiv/driftnet) -> VoIPong -> [tcpxtract](http://tcpxtract.sourceforge.net/)
* __Network Mapping__: [Open Visual Traceroute](http://visualtraceroute.net/) -> [EtherApe](http://etherape.sourceforge.net/) -> [Paris Traceroute](https://github.com/libparistraceroute/libparistraceroute) -> [Dublin Traceroute](https://github.com/insomniacslk/dublin-traceroute) -> [MTR](https://www.bitwizard.nl/mtr/) -> Layer Four Traceroute (LFT) -> [tcptraceroute](https://directory.fsf.org/wiki/Tcptraceroute) -> iputils (Ping, traceroute, tracepath, arping) -> ipcalc -> GeoIP
* __OSINT__: SpiderFoot -> TheHarvester -> [Creepy](https://github.com/ilektrojohn/creepy) -> [Netglub](http://www.netglub.org/)
* __Packet Sniffer__: [Tshark (Wireshark TUI)](https://github.com/wireshark/wireshark) -> [tcpflow](https://directory.fsf.org/wiki/Tcpflow) -> [tcpdump](https://directory.fsf.org/wiki/Tcpdump) + tcpick
* __Reconnaissance Framework__: Recon-ng -> DMitry -> [dsniff](https://www.monkey.org/~dugsong/dsniff/) (urlsnarf, filesnarf, webspy, Tcpkill, macof, arpspoof) -> [Nmap](https://nmap.org/) -> [ngrep](https://github.com/jpr5/ngrep/)
* __WiFi Scanner__: [FLUXION](https://github.com/wi-fi-analyzer/fluxion) -> [Kismet](https://www.kismetwireless.net/)

### Network Tampering
* __General__: netcat -> ncat (nmap) -> [cryptcat](http://cryptcat.sourceforge.net/) (Netcat) -> [socat](https://github.com/craSH/socat) -> [Netsed](https://github.com/xlab/netsed)
* __Man-in-the-middle Attack__: [sslstrip](https://github.com/moxie0/sslstrip) -> [Morpheus](https://github.com/r00t-3xp10it/morpheus) -> evilginx2 -> bettercap -> [Ettercap](https://github.com/Ettercap/ettercap)
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
* __Application Vulnerability__: Fuzz -> [BCCF](https://github.com/joxeankoret/nightmare/blob/master/doc/blind_code_coverage_fuzzer.txt) -> [afl-fuzz](http://lcamtuf.coredump.cx/afl/)
* __Backdooring__: [Veil](https://github.com/Veil-Framework/Veil) -> [Cymothoa](http://cymothoa.sourceforge.net/) -> [Backdoor Factory](https://github.com/secretsquirrel/the-backdoor-factory) -> [Evilgrade](https://github.com/infobyte/evilgrade) -> [EvilAbigail](https://github.com/GDSSecurity/EvilAbigail)
* __Cross-Scripting__: [xsser](https://github.com/epsylon/xsser)
* __Exploit Famework__: Metasploit -> [Metasploit](https://github.com/metasploit/framework2) (Perl), [WebSploit](https://github.com/websploit/websploit) -> [w3af](https://github.com/andresriancho/w3af)
* __Network Vulnerability__: [pytbull](http://pytbull.sourceforge.net/) -> [Yersinia](https://github.com/tomac/yersinia)
* __Post Exploitation__: [Empire](https://github.com/EmpireProject/Empire) -> [Post Exploitation Collection](https://github.com/mubix/post-exploitation) (Windows) -> [mimikatz](https://github.com/gentilkiwi/mimikatz) (Windows) -> [Post Exploitation Linux Toolkit](https://github.com/cys3c/PELT) -> [poet](https://github.com/mossberg/poet)
* __SIP__: Sippts
* __Social Engineering__: [SET (Social Engineering Toolkit)](https://github.com/trustedsec/social-engineer-toolkit), [BeEF (The Browser Exploitation Framework Project)](https://github.com/beefproject/beef)
* __SQL Injection__: [sqlmap](https://github.com/sqlmapproject/sqlmap)
* __SSH Denial__: [screwSSH](https://github.com/isislab/screwSSH)
* __Web Application Vulnerability__: [Nikto](https://github.com/sullo/nikto)
* __Windows Registry Editor__: [Offline NT Password & Registry Editor (chntpw)](http://pogostick.net/~pnh/ntpasswd/)

## Privacy
* __Anti Stylometry__: [Anonymouth](https://github.com/psal/anonymouth)
* __Data Erasure__: [Dban](https://sourceforge.net/projects/dban/) -> bleachbit_cli ([BleachBit](https://github.com/bleachbit/bleachbit)) -> shred (GNU Coreutils)
* __Boot Encryption__: [cryptboot](https://github.com/xmikos/cryptboot)
* __Disk Encryption__: dislocker -> [cryptsetup (dm-crypt)](https://gitlab.com/cryptsetup/cryptsetup/wikis/DMCrypt)
* __File Encryption__: [GNU Privacy Assistant](https://www.gnupg.org/related_software/gpa/) -> MCrypt -> ccrypt -> [GNU Privacy Guard](https://www.gnupg.org/)
* __Filesystem Encryption__: eCryptfs -> EncFS -> [StegFS](https://github.com/albinoloverats/stegfs)
* __Folder Encryption__: VeraCrypt -> [Tomb](https://github.com/dyne/Tomb) -> [tcplay](https://github.com/bwalex/tc-play) (full TrueCrypt implementation and still minimalist)
* __Encrypted Version Control__: [Keyringer](https://github.com/quarkslab/keyringer)
* __Identity Generator__: [The Random Identity Generator (rig)](http://rig.sourceforge.net/)
* __Password Generator__: [pwgen](https://github.com/jbernard/pwgen) -> [apg](https://github.com/Distrotech/apg) -> upwgen -> randstr
* __Password Manager__: KeePassX / KeePassXC -> [pass](https://www.passwordstore.org/) (+ [pass-tomb](https://github.com/roddhjav/pass-tomb), + [passmenu](https://github.com/cdown/passmenu)) -> [kpcli](https://github.com/alecsammon/kpcli)
* __Password Sync__: KeySync
* __Steganography__: [StegoShare](http://stegoshare.sourceforge.net/) -> [Steghide](https://github.com/StefanoDeVuono/steghide) -> [SNOW (stegsnow)](http://www.darkside.com.au/snow/) -> UUDeview -> [Steganoroute](https://sourceforge.net/projects/steganoroute/)

## Programming
* __Build Automation__: Ninja -> mk -> [GNU make](https://directory.fsf.org/wiki/Make) -> bmake -> Icmake -> Jam, [Gnulib](https://www.gnu.org/software/gnulib/)
* __Build Script Generation__: [Gradle](https://github.com/gradle/gradle) -> Cmake (+ cmocka + ECM) -> Autotools ([Automake](https://directory.fsf.org/wiki/Automake), [Autoconf](https://directory.fsf.org/wiki/Autoconf) + GNU Autoconf Archive, [Libtool](https://directory.fsf.org/wiki/Libtool)) -> mk-configure
* __Code Beautifier__: TagSoup -> [UniversalIndentGUI](https://github.com/danblakemore/universal-indent-gui) -> HTML Tidy -> tidyp -> Indent
* __Compilers (Assembly)__: NASM -> Yasm -> as (GNU binutils)
* __Compilers (C)__: clang -> Tiny C Compiler (tcc)
* __Compilers (Java)__: Java SE (JDK) -> [IcedTea](https://icedtea.classpath.org/wiki/Main_Page) (OpenJDK) -> [GraalVM](https://www.graalvm.org/) (compile multiple languages into JVM) -> JamVM (JVM) -> FastJar (Compiler)
* __Compilers (Multiple languages)__: [GCC](https://directory.fsf.org/wiki/Gcc) ([GNU -native- Compiler for Java](https://gcc.gnu.org/wiki/GCJ), [GnuCOBOL](https://sourceforge.net/projects/open-cobol/), [GNU Fortran](https://gcc.gnu.org/wiki/GFortran)) + [colorgcc](https://github.com/colorgcc/colorgcc)
* __Compiling Speeding Up__: [distcc](https://github.com/distcc/distcc), [ccache](https://github.com/ccache/ccache)
* __Cross-compiler__: [Buildroot](https://github.com/buildroot/buildroot) -> Crosstool-NG -> dev86
* __Documentation Browser__: Devhelp -> [Zeal](https://github.com/zealdocs/zeal)
* __Documentation Generator__: perlpod, [bashdoc](https://github.com/ajdiaz/bashdoc), Doxygen, GNU help2man
* __Issue Tracking System__: Bugzilla -> [GNATS](https://www.gnu.org/software/gnats/)
* __Linting__: [ShellCheck](https://github.com/koalaman/shellcheck), [GNU Source-highlight](https://www.gnu.org/software/src-highlite/)
* __Memory Allocation__: jemalloc -> boehm-gc
* __Parser Generators__: ANTLR -> Ragel-> [AutoGen](https://directory.fsf.org/wiki/Autogen) -> [GNU bison](https://directory.fsf.org/wiki/Bison) and [Flex](https://directory.fsf.org/wiki/Flex) -> re2c + lemon -> [GNU m4](https://directory.fsf.org/wiki/M4)
* __[Program Transformation](https://en.wikipedia.org/wiki/Program_transformation)__: [FermaT](http://www.gkc.org.uk/fermat.html), [Coccinelle](http://coccinelle.lip6.fr/), [CIL](https://people.eecs.berkeley.edu/~necula/cil/), [Stratego/XT](http://strategoxt.org/)
* __Random Hacks__: patchelf, elfhacks, SWIG, Gengetopt
* __Source Code Count__: [Unified Code Count (UCC)](https://github.com/RMax2015/Unified_Code_Count) -> [CLOC](http://cloc.sourceforge.net/)
* __Source Code Navigation__: GNU idutils, cflow (+ cflow2dot), [LXR: The Linux Cross Referencer](http://lxr.sourceforge.net/en/index.php) -> [GNU GLOBAL](https://www.gnu.org/software/global/) -> [cscope](http://cscope.sourceforge.net/) -> [Ctags](https://github.com/universal-ctags/ctags) -> [cgvg](https://github.com/uzi/cgvg) -> [ack](https://beyondgrep.com/) -> [ag](https://github.com/ggreer/the_silver_searcher)
* __[Source-to-Source Compiler](https://en.wikipedia.org/wiki/Source-to-source_compiler)__: [ROSE](https://github.com/rose-compiler/rose)
* __System Query__: [sysconftool](https://github.com/svarshavchik/courier/tree/master/sysconftool), [Installwatch](https://github.com/ruxkor/checkinstall/tree/master/installwatch), [pkgconf](https://github.com/pkgconf/pkgconf)
* __Version Control__: Git (+ [tig](https://github.com/jonas/tig)) -> [CVS](https://directory.fsf.org/wiki/CVS) (+ [CVSGraph](https://directory.fsf.org/wiki/CVSGraph)) -> [Fossil](https://www.fossil-scm.org/index.html/doc/trunk/www/index.wiki) -> [tla (GNU Arch)](https://directory.fsf.org/wiki/Gnu-arch) -> [RCS](https://www.gnu.org/software/rcs/) + mr + quilt

## Remote Access
* __Configuration Management__: Puppet -> LCFG -> CFEngine -> [cdist](https://github.com/ungleich/cdist)
* __Control Panel__: ZPanel -> Vesta Control Panel -> [Webmin](https://github.com/webmin/webmin)
* __Diskless Booting__: iPXE -> [netboot](http://netboot.sourceforge.net/)
* __PC-Mobile Connection__: KDE Connect -> Wammu -> BitPim -> AndroidTools
* __Remote Desktop (Client)__: rdesktop -> Remmina -> [fbvnc](https://github.com/zohead/fbvnc)
* __Remote Desktop (Client and Server)__: X2Go
* __Remote Desktop (Server)__: [xrdp](https://github.com/neutrinolabs/xrdp)
* __Remote Execution__: PSSH -> [pconsole](https://github.com/walterdejong/pconsole) -> [DSH](https://www.netfort.gr.jp/~dancer/software/dsh.html.en)
* __Remote File Manager__: [KodExplorer](https://github.com/kalcaddle/KodExplorer)
* __Remote Login__: Mosh -> OpenSSH -> [lsh](https://directory.fsf.org/wiki/Lsh) -> Dropbear
* __Remote X Apps__: Xpra > X11 forwarding
* __Reverse Shell__: [icmpsh](http://inquisb.github.io/icmpsh/) -> [RevSh](https://directory.fsf.org/wiki/Reverse_Shell)
* __Serial Console__: Minicom -> [Picocom](https://directory.fsf.org/wiki/Picocom) -> Qodem -> [GNU Screen](http://www.noah.org/wiki/Screen_notes#using_screen_as_a_serial_terminal)
* __Server Provisioning__: [FAI](http://fai-project.org/)
* __Wake-on-LAN__: [wakeonlan](https://github.com/jpoliv/wakeonlan)

## Science And Engineering
* __Artificial Intelligence__: [Arcade Learning Environment](https://github.com/mgbellemare/Arcade-Learning-Environment), [ETHNOS](http://ethnos.sourceforge.net/), [Conscious Artificial Intelligence](https://sourceforge.net/projects/cai/), [OpenCog](https://github.com/opencog/opencog), [OpenAI](https://github.com/openai)
* __Astronomy__: Sky Chart (Cartes du Ciel) -> astroTools + evTools -> GNU Astronomy Utilities (Gnuastro)
* __Astronomy (Planetarium)__: Stellarium -> Celestia -> XEphem -> [SkyCat](https://github.com/Starlink/skycat)
* __Astronomy (Satelline Tracking)__: [SaVi satellite constellation visualizer](https://sourceforge.net/projects/savi/)
* __Bioinformatics__: [OpenSim](https://simtk.org/projects/opensim/), [Cytoscape](http://www.cytoscape.org/), [BioJava](https://github.com/biojava/biojava) -> [UGENE](http://ugene.net/) -> [EMBOSS](https://github.com/kimrutherford/EMBOSS) -> [SAMtools](https://github.com/samtools/samtools) -> [BioPerl](http://bioperl.org/)
* __CAD__: AutoCAD -> Blender -> FreeCAD -> LibreCAD -> [OpenSCAD](https://github.com/openscad/openscad)
* __Chemistry__: [MolComp](http://molcomp.sourceforge.net/), [RasMol](https://directory.fsf.org/wiki/RasMol), [PerlMol](http://www.perlmol.org/)
* __Circuit Simulator__: [KiCad](http://kicad-pcb.org/) -> [ngspice](http://ngspice.sourceforge.net/) -> [Gnucap](http://www.gnucap.org/dokuwiki/doku.php?id=gnucap:start)
* __Computational Fluid Dynamics__: [TELEMAC](http://www.opentelemac.org/) -> [FEATFLOW](http://www.featflow.de/en/index.html) -> [OpenFOAM](https://directory.fsf.org/wiki/OpenFOAM) -> [Gerris](http://gfs.sourceforge.net/wiki/index.php/Main_Page)
* __Computer Algebra System__: [Singular](http://www.singular.uni-kl.de/) -> [Axiom](http://www.axiom-developer.org/) -> [Maxima](http://maxima.sourceforge.net/) (+ PLplot) -> bc + GNU Units
* __Data Visualization__: [SocNetV](https://github.com/socnetv) -> [Gephi](https://github.com/gephi/gephi) -> [Tulip](http://tulip.labri.fr/TulipDrupal/)
* __Geography (Geographic Information System)__: [qGIS](https://github.com/qgis/QGIS) -> FWTools (OGDI, PROJ.4, GDAL/OGR, MapServer, OpenEV)
* __Geography (Street Map)__: [JOSM](https://github.com/openstreetmap/josm) -> [Osmosis](https://github.com/openstreetmap/osmosis)
* __Geography (Subway Map)__: [qMetro](http://qmetro.sourceforge.net/maps/)
* __Geography (Virtual Globe)__: [Marble](https://github.com/KDE/marble)
* __Graphing Calculator__: GraphMonkey -> Lybniz -> KAlgebra -> [TilEm](http://lpg.ticalc.org/prj_tilem/)
* __Multi-Agent (MA) Simulation__: [Mobility Testbed](https://github.com/agents4its/mobilitytestbed) -> [Galatea](http://galatea.sourceforge.net/Home.htm) -> [NetLogo](https://github.com/NetLogo/NetLogo/) -> [Golly](http://golly.sourceforge.net/) (Conway's Game of Life clone)
* __Physics Simulation__: [OpenModelica](https://www.openmodelica.org/) -> [CalculiX](http://www.calculix.de/) -> [Elmer](https://directory.fsf.org/wiki/Elmer) -> [MCSim](https://directory.fsf.org/wiki/Mcsim)
* __Semiconductor Modeling (TCAD)__: [GNU Archimedes](https://directory.fsf.org/wiki/Archimedes) (and [GNU Nano-Archimedes](https://directory.fsf.org/wiki/Nano-archimedes))
* __Statistical Package__: [SageMath](http://www.sagemath.org/) -> Physics Analysis WorkStation -> ROOT -> [gretl](http://gretl.sourceforge.net/) -> [PSPP](https://directory.fsf.org/wiki/Pspp)  (+ PSPP-Perl)
* __Theorem Prover__: Coq -> [Abella](https://github.com/abella-prover/abella) -> [Vampire](https://github.com/mayfrost/Vampire) -> [Metamath](http://metamath.org/)
* __Weather Forecast__: XTide -> AWeather -> My Weather Indicator -> wego -> [Weather Util](http://fungi.yuggoth.org/weather/) -> [rrdweather](https://github.com/tolecnal/rrdweather) -> [curl wttr.in/YOURCITY, YOURCOUNTRY](http://wttr.in/)

## Security
### Containment
* __Access Control (Kernel Patches)__: grsecurity + gradm -> Linux Intrusion Detection System -> SecurelLevel -> PaX -> [RSBAC](https://www.rsbac.org/)
* __Access Control (Linux Security Modules (LSM))__: SELinux -> TOMOYO Linux -> Smack -> AppArmor
* __Authentication__: Polkit -> ConsoleKit -> Sudo (visudo) -> Linux PAM -> checkpassword -> shadow
* __Extended File Attributes__: EVM -> IMA -> inotify
* __Resource Usage Control__: [cpulimit](https://github.com/opsengine/cpulimit) -> ulimit (Bash) -> [Disk Quota](https://sourceforge.net/projects/linuxquota/) -> [quotatool](https://github.com/ekenberg/quotatool)
* __Sandbox__: Arkose -> [Firejail](https://github.com/netblue30/firejail) -> nsjail -> [Bubblewrap](https://github.com/projectatomic/bubblewrap)

### Honeypots
* __Client__: [HoneyC](https://projects.honeynet.org/honeyc) -> [Capture-HPC](https://projects.honeynet.org/capture-hpc)
* __Distro Bundle__: [HoneyDrive](https://sourceforge.net/projects/honeydrive/) -> [ADHD](https://adhdproject.github.io/#!index.md)
* __Server__: [Honeyperl](https://sourceforge.net/projects/honeyperl/) -> [Nova](https://github.com/DataSoft/Nova) -> Honeyd -> [LaBrea](http://labrea.sourceforge.net/labrea-info.html)
* __Web-Based__: [HIHAT](http://hihat.sourceforge.net/)

### Host Intrusion
* __Anti Backdoor__: [rosenbridge](https://github.com/xoreaxeaxeax/rosenbridge), [me_cleaner](https://github.com/corna/me_cleaner)
* __Anti Juice Jacking__: [usbkill](https://github.com/hephaest0s/usbkill) -> [USBGuard](https://github.com/USBGuard/usbguard)
* __Anti Malware__: ClamTk -> [ClamAV](https://github.com/Cisco-Talos/clamav-devel) -> [Linux Malware Detect (LMD)](https://github.com/rfxn/linux-malware-detect)
* __Host Intrusion Detection Framework__: [OSSEC](https://ossec.github.io/) -> [Tiger](http://www.nongnu.org/tiger/)
* __Host System Auditing__: [Bastille](http://bastille-linux.sourceforge.net/) -> [OpenVAS](http://www.openvas.org/) -> [Linux Security Auditing Tool (LSAT)](https://github.com/triode3/lsat) -> [Lynis](https://github.com/CISOfy/lynis)
* __Integrity Check__: PaX Utilities -> AIDE -> [systraq](https://directory.fsf.org/wiki/Systraq) -> [Tripwire](https://github.com/Tripwire/tripwire-open-source) -> [Samhain](https://www.la-samhna.de/samhain/)
* __Rootkit Detection__: [rkhunter](http://rkhunter.sourceforge.net/), [Chkrootkit](http://www.chkrootkit.org/), [Unhide](http://www.unhide-forensics.info/)
* __System Logging__: socklog (runit) -> Rsyslog -> [Syslog-ng](https://github.com/balabit/syslog-ng) -> [sysklogd](http://www.infodrom.org/projects/sysklogd/)

### Network Intrusion
* __Deep Packet Inspection (DPI) Block (Layer 7 Firewall)__: ipp2p -> l7-filter -> OpenDPI
* __Deep Packet Inspection (DPI) Circumvention__: [zapret](https://github.com/bol-van/zapret)
* __Firewall__: ufw (Uncomplicated Firewall) + gufw (GUI) -> arptables -> ebtables -> iptables (+ [ipset](http://ipset.netfilter.org/)) -> [nftables](https://netfilter.org/projects/nftables/) + conntrack-tools
* __Man-In-The-Middle (MITM) Detection__: arpwatch -> [ArpON](http://arpon.sourceforge.net/) -> [Arpalert](http://www.arpalert.org/arpalert.html)
* __Network Intrusion Detection__: Snort -> [Suricata](https://github.com/OISF/suricata)
* __Network Intrusion Prevention__: Fail2ban -> [Sshguard](https://www.sshguard.net/)
* __Network Logging__: CoCaLoRes -> ulogd

## Server
* __BBS Server__: [Citadel](http://www.citadel.org/doku.php) -> Synchronet -> [Mystic BBS](http://www.tinysbbs.com/files/prog/MSRC20B3.ZIP) -> [BBS100](https://directory.fsf.org/wiki/Bbs100)
* __Bitcoin Miner__: BFGMiner
* __Blog__: finger / [cfingerd](https://github.com/pld-linux/cfingerd)
* __Bluetooth__: BlueALSA
* __Captcha__: [cool-php-captcha](https://github.com/josecl/cool-php-captcha)
* __Chat__:  [sshtalk](https://2ton.com.au/sshtalk/) -> util-linux (write, wall, mesg)
* __Cloud File Server__: Google Drive -> Nextcloud -> [Syncthing](https://github.com/syncthing/syncthing) -> sftp / [SSHFS](https://github.com/libfuse/sshfs) (SSH)
* __CMS__: WordPress -> [GetSimple CMS](https://github.com/GetSimpleCMS/GetSimpleCMS) -> [werc](http://werc.cat-v.org/)
* __Collaborative Real-Time Editor__: [Gobby](https://github.com/gobby/gobby) -> [EtherCalc](https://github.com/audreyt/ethercalc) -> [Cryptpad](https://github.com/xwiki-labs/cryptpad)
* __Direct Connect Server__: [uhub](https://www.uhub.org/)
* __DLNA__: [Universal Media Server](https://github.com/UniversalMediaServer/UniversalMediaServer) -> [ReadyMedia](http://minidlna.sourceforge.net/) (a.k.a. MiniDLNA) -> MiniUPnP
* __DNS Spam Detector__: DNS Flood Detector
* __Document Management System__: [OpenKM](https://github.com/openkm/document-management-system) -> [LogicalDOC](https://github.com/logicaldoc/document-management-software) -> [EPrints](https://github.com/eprints/eprints)
* __Dynamic DNS (DDNS)__: DDClient
* __E-Mail Filtering (LDA)__: Dovecot -> [procmail](https://github.com/Distrotech/procmail)
* __E-Mail Indexing__: Archmbox -> Chewmail -> Notmuch -> [mairix](https://github.com/rc0/mairix)
* __E-Mail Mailing Lists__: Mailman -> [Sympa](https://github.com/sympa-community) -> [Dada Mail](https://github.com/justingit/dada-mail) -> [ezmlm](https://github.com/bruceg/ezmlm-idx) -> mlmmj
* __E-Mail Notifier__: [mswatch](http://mswatch.sourceforge.net/)
* __E-Mail Server (MTA)__: [Mail-in-a-Box](https://mailinabox.email/) -> Kolab -> Sendmail -> Postfix -> Exim -> [cmail](http://cmail.rocks/) -> [qpsmtpd](https://smtpd.github.io/qpsmtpd/) -> OpenSMTPD -> [qmail](https://en.wikipedia.org/wiki/Qmail)
* __E-Mail Spam Filter__: Bogofilter -> DSPAM -> [SpamAssassin](https://github.com/apache/spamassassin) -> SpamProbe + Hashcash + rbldnsd
* __E-Mail Validation__: [OpenDKIM](http://opendkim.org/), [SPF](http://www.openspf.org/)
* __File Distribution__: [zsync](http://zsync.moria.org.uk/)
* __Forum__: [lainchan](https://github.com/lainchan/lainchan) -> vichan -> [Akari-BBS](https://github.com/microsounds/akari-bbs) -> [sshchan](https://github.com/einchan/sshchan) -> KrautBBS -> [1436chan](https://github.com/kibook/1436chan)
* __FTP Server__: CurlFtpFS -> [vsftpd](https://github.com/timonier/vsftpd)
* __Gopher Server__: Gophernicus -> [Bucktooth](http://gopher.floodgap.com/gopher/gw?gopher/1/buck) (Gopher) + [Bucky](https://github.com/kibook/bucky) (for HTTP exit)
* __Groupware__: Collabtive -> [Alfresco](https://github.com/Alfresco) -> [eXo Platform](https://github.com/exoplatform) -> [Citadel/UX](http://www.citadel.org/doku.php)
* __Image Hosting__: img.bi -> Up1
* __IRC Bot__: [Seabattle](https://github.com/GamesLT/SeaBattle.tcl) (bot game), [Infobot](https://github.com/w3c/infobot), [Eggdrop](https://www.eggheads.org/) (IRC bot)
* __IRC Bouncer (BNC)__: [ZNC](https://github.com/znc/znc) -> bip
* __IRC Fileserver__: [iroffer](https://github.com/grimneko/iroffer-modDinoex)
* __IRC Server__: UnrealIRCd -> Charybdis -> InspIRCd -> [ngIRCd](https://github.com/ngircd/ngircd)
* __Learning Management System__: [GnuTutor](https://sourceforge.net/projects/gnututor/) -> [OpenExpert](https://sourceforge.net/projects/law-expert/) -> [Syllog](https://sourceforge.net/p/syllog/wiki/Home/)
* __MUD Server__: LambdaMOO -> [PennMUSH](https://github.com/pennmush/pennmush)
* __Paint chat__: [Drawpile](https://github.com/drawpile/Drawpile) -> [Collab](https://github.com/MoonGames/collab-desktop)
* __Pastebin__: Stikked -> Paste -> [PrivateBin](https://github.com/PrivateBin/PrivateBin)
* __Political__: [LittleSis](https://github.com/public-accountability/littlesis-rails), [Loomio](https://github.com/loomio/loomio)
* __Port Tunnel__: [stunnel](https://www.stunnel.org/) -> [sslh](https://github.com/yrutschle/sslh)
* __Proxy Server__: [Tinyproxy](https://tinyproxy.github.io/)
* __Service Manager__: [xinetd](https://github.com/xinetd-org/xinetd) -> linetd -> inetd (GNU inetutils) -> [knockd](https://github.com/jvinet/knock) -> [TCP Wrappers](https://github.com/pexip/os-tcp-wrappers) (tcpd, tcpdchk) -> ucspi-tcp
* __Streaming__: [Syncplay](https://github.com/Syncplay/syncplay) -> [Peerflix](https://github.com/mafintosh/peerflix) (+ [Torrentflix](https://github.com/ItzBlitz98/torrentflix)) -> [Libresonic](https://github.com/Libresonic/libresonic) -> Icecast (+ DarkIce -> ezstream -> oggfwd) -> trx: Realtime audio over IP -> SRS -> [VLC](https://www.howtogeek.com/118075/how-to-stream-videos-and-music-over-the-network-using-vlc/) -> [FFmpeg](https://gist.github.com/olasd/9841772)
* __Torrent Tracker__: [Ocelot](https://github.com/whatcd/ocelot) -> [Gazelle](https://github.com/WhatCD/Gazelle) -> hefur
* __Tunneling__: HTTPTunnel -> VTun -> [ProxyChains](https://github.com/rofl0r/proxychains-ng) -> [VPNEncap](https://github.com/whussup/vpnencap) -> [VPNCHAINS](https://sourceforge.net/p/vpnchains/wiki/Home/)
* __Tunneling VM__: [PIA Tunnel](https://www.privateinternetaccess.com/forum/discussion/1389/pia-tunnel-a-virtual-machine-vpn-tunnel) -> [Whonix](https://www.whonix.org/)
* __Usenet Server__: [InterNetNews](https://www.eyrie.org/~eagle/software/inn/) -> [Leafnode](http://www.leafnode.org/)
* __VoIP__:  GNU SIP Witch -> GNU Gatekeeper -> Mumble -> [Linphone (linphonec)](https://www.linphone.org/) -> PJSIP -> [sscall](https://github.com/Drakevr/sscall)
* __VPN (Overlay)__: strongSwan -> Libreswan -> OpenVPN (+ [PiVPN](http://www.pivpn.io/)) -> [WireGuard](https://github.com/WireGuard/wireguard-rs)
* __VPN (Pseudo-wire)__: Tunneldigger -> OpenMesher
* __Web Caching__: Decentraleyes on a web browser -> [Squid](http://www.squid-cache.org/) (+ [SquidGuard](http://squidguard.org/) for Web Filtering)
* __Web Filtering__: Ad blocker on a web browser -> [Pi-hole](https://github.com/pi-hole/pi-hole) -> DansGuardian -> [Privoxy](http://www.privoxy.org/) -> [Hostsblock](https://github.com/gaenserich/hostsblock)
* __Web Server__: Apache -> Nginx -> lighttpd -> Hiawatha -> Monkey -> [GNU MyServer](https://directory.fsf.org/wiki/GNU_MyServer) -> webfs -> [darkhttpd](https://github.com/ryanmjacobs/darkhttpd) -> [Bucky](https://github.com/kibook/bucky) (Bucktooth HTTP exit)
* __Web Server Certificate__: Dehydrated -> acmetool
* __Wiki__: TWiki -> DokuWiki -> [XWiki](https://github.com/xwiki/xwiki-platform) -> [ikiwiki](https://ikiwiki.info/)
* __Wireless Access Point__: [hostapd](https://github.com/OpenSecurityResearch/hostapd-wpe)
* __XMPP Server__: [Tigase](https://github.com/kontalk/tigase-server)

### Server Authentication
* __Directory Service__: [OpenLDAP](https://www.openldap.org/) -> [NIS](http://www.linux-nis.org/nis/)
* __Domain Specific Authentication Server__: Ident (IRC), [SKS](https://bitbucket.org/skskeyserver/sks-keyserver/wiki/Home) (PGP)
* __RADIUS__: [FreeRADIUS](https://github.com/FreeRADIUS) -> [GNU Radius](https://www.gnu.org/software/radius/)
* __SSO__: krb5 (Kerberos) + keyutils -> [GNU Shishi](https://www.gnu.org/software/shishi/) (Kerberos)
* __Suites__: [FreeIPA](https://github.com/freeipa/freeipa) -> [SSSD](https://github.com/SSSD/sssd)

## System Utilities
* __BIOS__: efibootmgr -> SeaBIOS -> Coreboot -> [Libreboot](https://libreboot.org/)
* __[Boot Loader](https://github.com/mayfrost/guides/blob/master/BOOTLOADER.md)__: GRUB 2 -> GRUB Legacy -> [SYSLINUX](http://www.syslinux.org/wiki/index.php?title=The_Syslinux_Project) (+ Hardware Detection Tool -HDT-) -> [LILO](https://lilo.alioth.debian.org/) (or [ELILO](https://sourceforge.net/projects/elilo/) for UEFI) -> AiR-Boot -> Das U-Boot (u-boot-tools)
* __Boot Loaders (load on running machine)__: loadlin -> Kexec (kexec-tools)
* __Cache__: Memcached, EnhanceIO -> dm-cache -> bcache
* __Core Utilities__: moreutils -> Mtools -> util-linux -> GNU Coreutils -> BusyBox -> Asmutils and ARMutils
* __Custom Initramfs__: mkinitcpio -> dracut -> Genkernel -> [mkinitramfs](https://github.com/tokiclover/mkinitramfs-ll) -> umkinitramfs
* __Filesystem__: CP/M (cpmtools), HFS Utilities, SquashFS (squashfs-tools), fuseflt, UnionFS (unionfs-fuse), udftools (UDF), F2FS (f2fs-tools), exFAT (exfat-utils, fuse-exfat), FAT (dosfstools), Btrfs (btrfs-progs), XFS (xfsprogs, xfsdump), Ext4, [JFS](http://jfs.sourceforge.net/), [Reiser4](https://reiser4.wiki.kernel.org/index.php/Main_Page), [Bcachefs](https://github.com/8l/Bcachefs)
* __IPC__: DBus -> [ubus](https://wiki.openwrt.org/doc/techref/ubus) -> RPCBind -> ipcs (util-linux)
* __Kernel Modules__: NDISwrapper -> ibm-acpi-> kmod (lsmod, insmod, modprobe)
* __Kernel Patches__: V86 mode support, GoboHide, Kernel_gcc_patch, Linux-ck, Liquorix, Linux-rt, GNU Linux-libre, Linux Tiny
* __Kernels__: LUnix, Linux + Lux (kernel updater), GNU Mach, RTLinux, Muen, HiStar
* __Load in RAM__: [E4rat](https://github.com/ShyPixie/e4rat-lite) -> readahead -> [preload](https://sourceforge.net/projects/preload/), [prelink](https://directory.fsf.org/wiki/Prelink)
* __Logical Volume Management__: LVM2
* __Multiplexer Wrappers__: ucspi-unix, ucspi-ipc, [socket_wrapper](https://cwrap.org/socket_wrapper.html), [nss_wrapper](https://cwrap.org/nss_wrapper.html), [uid_wrapper](https://cwrap.org/uid_wrapper.html), [resolv_wrapper](https://cwrap.org/resolv_wrapper.html), [pam_wrapper](https://cwrap.org/pam_wrapper.html)
* __Network Time Protocol__: clockspeed -> Network Time Protocol daemon (ntpd) -> chrony -> OpenNTPD
* __OS Frameworks__: OpenStack -> Genode
* __Partitioning__: Gparted -> GNU Parted -> util-linux (cfdisk, fdisk, sfdisk, mkfs, mkswap, swapon, swapoff)
* __Partitioning Fixes__: u3_tool, ms-sys
* __Settings Manager__: Youker Assistant -> [Linux Lite Control Center](https://github.com/linuxlite/litecontrolcenter) -> [Elektra](https://github.com/ElektraInitiative/libelektra) -> [Augeas](https://github.com/hercules-team/augeas) -> Climate -> The Fuck -> Suicide Linux
* __Virtual Filesystem__: FuseIso -> Autofs -> AVFS -> afuse -> bindfs

### Init
* __Daemon__: [Upstart](https://code.launchpad.net/upstart) -> [SysVinit](https://github.com/slicer69/sysvinit) -> [Initng](https://github.com/initng/initng) -> Finit -> [sinit](https://github.com/henrysher/sinit)
* __Service Manager__: OpenRC (includes an optional own init) -> runit (includes an optional own init) -> Ignite -> [daemontools-encore](https://github.com/bruceg/daemontools-encore) -> [perp](https://github.com/jdavisp3/perp)
* __Startup Scripts Manager__: [bum](https://launchpad.net/bum) -> [svsh](https://ido50.github.io/Svsh/) -> [sysv-rc-conf](http://sysv-rc-conf.sourceforge.net/) -> [chkconfig](https://uni.edu/~prefect/devel/chkconfig/index.shtml)

### Job Scheduler
* __Event__: [incron](http://inotify.aiken.cz/?section=incron&page=about&lang=en) -> inotify-tools -> entr -> wendy -> ACPI event daemon (acpid) -> waitfordevice (w4d)
* __Queue__:  [Slurm](https://github.com/SchedMD/slurm) -> Task Spooler
* __Time__: Anacron -> [fcron](http://fcron.free.fr/) -> bcron -> dcron -> at

## X Desktop
* __Application Launcher__: ratmenu -> xcmd -> [dmenu](https://github.com/stilvoid/dmenu) -> nenu
* __Boot Screen__: Plymouth -> Splashy -> Fbsplash -> \<BOOTLOADERS>
* __Clipboard__: [CopyQ](https://github.com/hluk/CopyQ) -> [clipmenu](https://github.com/kaihendry/clipmenu) -> [snippy](https://github.com/gotbletu/shownotes/blob/master/snippy.sh) -> xclip -> XSel
* __Compositing Window Manager__: Compiz -> Compton -> Xcompmgr
* __Desktop Animated Character__: [Kawari](https://sourceforge.net/projects/kawari/) + [Ninix-aya](https://directory.fsf.org/wiki/Ninix-aya) (for [Ukagaka](https://en.wikipedia.org/wiki/Ukagaka)) -> [Gnome KiSS](http://devel.tlrmx.org/kiss/) -> [Oneko](http://www.daidouji.com/oneko/) -> [xevilteddy](https://github.com/mjg59/xevilteddy) -> [Xteddy](https://xteddy.org/)
* __Desktop Automation__: [Autokey](https://github.com/autokey/autokey) -> [Sikuli](https://github.com/sikuli/sikuli) -> [Easystroke](https://github.com/thjaeger/easystroke) -> [xdotool](http://www.semicomplete.com/blog/projects/xdotool/) -> [GNU Xnee](https://www.gnu.org/software/xnee/) 
* __Font Settings__: xfontsel + mkfontdir -> fontconfig -> /etc/X11/xorg.conf
* __Graphics Settings__: RiceDB -> [Wpgtk](https://deviantfero.github.io/wpgtk/) -> LxAppearance -> dconf -> Xset -> /etc/X11/xorg.conf
* __Login Manager__: SLiM -> [Qingy](http://qingy.sourceforge.net/)
* __Nested Display__: Xephyr -> Xnest
* __Notification (Daemon)__: dunst -> [slstatus](https://github.com/drkhsh/slstatus) -> SiND (Simple Notification Daemon)
* __Notification (Server)__: Libcanberra + Libnotify -> xmessage
* __Panel__: Avant Window Navigator -> Global Menu -> Tint2
* __Screensaver__: XScreenSaver -> XLockmore -> i3lock -> [sxlock](https://github.com/lahwaacz/sxlock) -> slock -> xset
* __Status Bar (Client)__: Dzen -> [bevelbar](https://github.com/vain/bevelbar) -> Lemonbar
* __Status Bar (Server)__: monky -> i3status
* __Wallpaper Changer (Animated)__: Xphoon, xfireworks, Xsnow, xmountains, Xplanet, ImageMagick (animate)
* __Wallpaper Changer (Still)__: FEH -> xsetroot -> [hsetroot](https://github.com/elmiko/hsetroot) -> [imagemagick](https://imagemagick.org/discourse-server/viewtopic.php?t=16735) (but using 10MB more RAM than the others)
* __Wallpaper Changer (Terminal As Wallpaper)__: xli -> [root-tail](http://oldhome.schmorp.de/marc/root-tail.html) -> [xrootconsole](http://silicone.homelinux.org/projects/xrootconsole/)
* __Wallpaper Changer (Video)__: VLC (nvlc) -> mpv -> MPlayer
* __Window Manager__: [FVWM](https://directory.fsf.org/wiki/Fvwm) (+ [FvwmTabs](http://fvwm.sourceforge.net/documentation/manpages/unstable/FvwmTabs.php) and [4dwm theme](https://github.com/tonnerre/fvwm/blob/master/sample.fvwmrc/4Dwm.fvwmrc)) -> IceWM (Windows XP-like) -> i3 -> [Amiwm](https://www.lysator.liu.se/~marcus/amiwm.html) (Amiga-like) -> [mlvwm](https://github.com/morgant/mlvwm) (Macintosh-Like) -> [MWM](https://github.com/stackfield/mwm) -> [Ratpoison](http://ratpoison.wxcvbn.org/cgi-bin/wiki.pl) -> dwm (+ dwmstatus) -> [FrankenWM](https://github.com/sulami/FrankenWM) -> [TinyWM](http://incise.org/tinywm.html) -> [s3d](http://s3d.sourceforge.net/) (+ s3dfm, it's a 3D desktop independent of X!) -> [Twin](https://github.com/cosmos72/twin) (independent of X) -> [VWM](http://vwm.sourceforge.net/) (independent of X)
* __Window Manipulation__: QuickTile -> wmctrl -> wmutils
* __Worskpace Pager__: [3D-Desktop](http://desk3d.sourceforge.net/) -> [Skippy-XD](https://github.com/richardgv/skippy-xd)
* __X Event Display__: xprop -> xwininfo -> xev
