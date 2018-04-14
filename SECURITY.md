# SECURITY IN ORDERS OF DIFFICULTY

Not necessarily meant to be followed step by step, although it is recommended. Some steps are valid during all levels, others give way to better alternatives further on.

* __Level 1__: Avoid using your real name online and avoid giving away any personal information. You can use [The Random Identity Generator](http://rig.sourceforge.net/) (rig) to generate an online persona and/or login sites using passwords from [BugMeNot](http://bugmenot.com).
* __Level 2__: Don't save your passwords on plaintext or in some "cloud" service like Lastpass and don't save logins on your phone or web browser. Create and remember one good main password (must have lowercase, uppercase, numbers and symbols, be longer than 8 characters and be change bimonthly), use KeePassX (and I mean the one with an X) and use the option to generate different passwords for each account you have and keep the password database on a USB. Other password manager is [kpcli](https://github.com/alecsammon/kpcli) which works on the command line and is just a perl script (this is the best option).
* __Level 3__: When possible opt for IRC instead of non-publicly auditable chat networks. A good and easy IRC application is Hexchat, another is irssi (best option). You can use [BitlBee](https://wiki.bitlbee.org/) to access other chat networks through an IRC client if you need.
* __Level 4__: Use [Searx](https://github.com/asciimoo/searx/wiki/Searx-instances) instead of Google when in need to search on the web.
* __Level 5__: Use [Mastodon (GNU Social)](https://joinmastodon.org/) instead of non-publicly auditable social networks known to sell private information.
* __Level 6__ Use RSS for news and podcasts from sites you trust instead of Youtube (although Youtube has an RSS feed for their channels too, for now). Liferea is an easy and great application for RSS feeds, newsboat (newsbeuter) is a command line option.
* __Level 7__: Replace your e-mail provider with a more safe, more appropriate provider. A good option is [cock.li](https://cock.li/).
* __Level 8__: Use an e-mail client that can to block web beacons (tracking pixels). Thunderbird is easy and has a plugin for this, Mutt or Alpine are better options.
* __Level 9__: Encrypt your e-mails with GnuPG. Thunderbird has the Enigmail plugin for this, you can can script the use of GPG on Mutt.
* __Level 10__: Delete any metadata from files you share on the internet. ExifTool in combination with [renamer](https://github.com/CaptainBlacklace/Renamer) is a good option.
* __Level 11__: Anonymize your writting style on any text with anti stylometry software like [Anonymouth](https://github.com/psal/anonymouth) when you share documents.
* __Level 12__: Use your web browser with javascript, cookies and any telemetry (like "pocket", geolocation and WebRTC) disabled and reduce the browser fingerprinting. Enable javascript and cookies only on selected sites. GNU IceCat is the best option, Firefox works too.

### Start of medium level security

* __Level 13__: Install LineageOS on your phone and use F-Droid without gapps (Google app store), with IceCatMobile for web browser, KeePassDroid, AFWall+ and Android IMSI-Catcher Detector. Use Yalp Store or Aptoide (or download from apkmirror/apkpure) in combination with microG if you need a gapps app.
* __Level 14__: Use GNU/Linux on your computers, preferably free from "systemd". PCLinuxOS is an easy first choice, Devuan is a better option. Stay away from something called BSD.
* __Level 15__: Uninstall Avahi, CUPS (replace with Line Printer if needed), Telnet, the R-tools (rlogin, rsh, rcp, rwho, rexec), fingerd, and uninstall unused services like ssh/web/ftp/mail.
* __Level 16__: Use Uncomplicated Firewall to block inbound AND outbound network traffic, permitting only what you need.
* __Level 17__: Use Firejail or Bubblewrap to sandbox your applications.
* __Level 18__: When possible give your applications a separate user account and use sudo, chroot, fakeroot, ulimit and quota with them.
* __Level 19__: Use DNSCrypt to prevent DNS Leaking with an OpenNIC provider known to not save logs.
* __Level 20__: Use YaCy with collaborative database disabled when in need to search on the web.
* __Level 21__: Use the Tor Browser to navigate the internet through Tor.
* __Level 22__: Use cmail in your own server for e-mail. Exim with Dovecot is another option, as is OpenSMTPD.
* __Level 23__: Use Squid for caching websites.

### Measures that cost money

* __Level 24__: Buy a VPS in a non-extradition, privacy friendly country outside the Five Eyes under a different name and with a good way of not getting traced by payments, then set up your own VPN server so you can audit all the traffic.
* __Level 25__: Buy a phone with Replicant and libre firmware. Tehnoetic sells an S3 phone with Replicant and only libre firmware enabled, so far is the best option.
* __Level 26__: Buy a router compatible with LibreCMC and install LibreCMC, keep it up to date and give it a strong password.
* __Level 27__: Buy a computer compatible with the Libreboot firmware and the Linux-libre kernel, then install both or buy it preinstalled. Thinkpads model x200, t400 and t500 are the best options.

### Start of physical access measures

* __Level 28__: Set a BIOS password (DON'T FORGET THIS PASSWORD!).
* __Level 29__: Use USBGuard (to prevent Juice Jacking).
* __Level 30__: Use disk encryption with cryptsetup (dm-crypt), saving the key on a separate USB that you keep with yourself at all times.
* __Level 31__: Move your boot partition to a USB and encrypt it with cryptboot. Use the option on Libreboot too.

### Start of high level security

* __Level 32__: Use a source based distro, preferably without crypto libraries on its package manager (no Python). Source Mage is advised and it is easy to setup.
* __Level 33__: Set a tight configuration for iptables on each port open and drop packets for everything. Use nftables on newer kernels.
* __Level 34__: Use port forwarding and a port knocker on your router or server and unregister your reverse dns records.
* __Level 35__: Use the IRC, e-mail and torrent services available inside i2p, and use Tor as an outproxy for i2p when in need to access the regular web (only for browsing).
* __Level 36__: Use a command line browser like links2 to browse web pages.
* __Level 37__: Use Bastille Linux to harden your system.
* __Level 38__: Use Lynis to audit your system.
* __Level 39__: Use Arpalert/ArpON (for Man-In-The-Middle -MITM- Detection), [zapret](https://github.com/bol-van/zapret) (for Deep Packet Inspection -DPI- Block and Circumvention), and Suricata/Snort (for Network Intrusion Detection).
* __Level 40__: Use a complete host intrusion detection framework like Tiger, which can work with Samhain (for integrity check), Unhide/Chkrootkit/rkhunter (for rootkit detection), ClamAV/Linux Malware Detect and a system logger like sysklogd.
* __Level 41__: Use [RSBAC](https://www.rsbac.org/) (for RBAC) with AppArmor (for filesystem ACL).
* __Level 42__: Compile the kernel yourself and add only necessary features and selected modules. Enable KASLR and Capabilities on kernel configuration.

### Start of deterrent measures

* __Level 43__: Learn to hack yourself first.
* __Level 44__: Use only libre software (software "free as in freedom").
* __Level 45__: Reduce the amount of software installed in your computer.
* __Level 46__: Opt for text-based programs with less library dependencies than their GUI counterparts.
* __Level 47__: Support the GPL license as to prevent proprietary license wrapping (as with BSD/MIT/Apache licenses). GPLv3 in specific to prevent tivoization, a hardware level lockdown method.
* __Level 48__: Deduplicate efforts and converge strategies to achieve a "tight base system" in common (use the koan "if is not strictly necessary it should be strictly optional, but still optional"), and that means making things modular and avoiding unnecessary dependencies instead of trusting "crypto libraries" like in python.
* __Level 49__: Abandon "cloud computing" and traditional, non-publicly auditable, data mined networks and erase your online persona. Use exclusively peer-to-peer services with specific protocols instead of all-in-one networks. Use IRC for live chat, and NNTP for newsgroups (per topic forums, what "social media" should be).
* __Level 50__: Abandon the Internet. Participate in local mesh networks and collaborate with global scale meshnet projects like [gternet](https://mesh.gentoo.today/wiki/Main_Page).
* __Level 51__: Don't f\*ck up. Protip: you can't.
