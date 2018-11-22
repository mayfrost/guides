# SECURITY IN ORDERS OF DIFFICULTY

Not necessarily meant to be followed step by step, although it is recommended. Some steps are valid during all levels, others give way to better alternatives further on.

---
## TOC
1. [Basic Level Security](#basic-level-security)  
2. [Cautionary Level Security](#cautionary-level-security)  
3. [Medium Level Security](#medium-level-security)  
4. [High Level Security](#high-level-security)  
5. [Physical Access Counter-Measures](#physical-access-counter-measures)  
6. [Costly Counter-Measures](#costly-counter-measures)  
7. [Deterrent Counter-Measures](#deterrent-counter-measures)  
8. [Exit Level Security](#exit-level-security)  

---

## Basic Level Security
* __Level 1__: Don't save your passwords on plaintext or in some "cloud" service like Lastpass and don't save logins on your phone or web browser. Use KeePassX (and I mean the one with an X) and remember one good main password (must have lowercase, uppercase, numbers and symbols, be longer than 8 characters and be change bimonthly), then use the password manager's option to generate different passwords for each account you have and keep the password database on a USB stick. Other password manager is [kpcli](https://github.com/alecsammon/kpcli) which [works on the command line](https://www.youtube.com/watch?v=M448GtFa5Xs) and is just a minimalist perl script (this is the best option).
* __Level 2__: Remove file extensions from sensitive files such as .kdb for KeePass password databases, rename it, and keep it in encrypted folders to make it hard to sift through your disk. Better yet, keep it all in a USB stick and with backups only to a third drive disconnected from any network.
* __Level 3__: Use [Searx](https://github.com/asciimoo/searx/wiki/Searx-instances) instead of Google when in need to search on the web. You can get search engine plugins for your browser [from here](https://mycroftproject.com/search-engines.html?name=searx).
* __Level 4__: Use your web browser with javascript, cookies and any telemetry (like "pocket", geolocation, and WebRTC) disabled and reduce the browser fingerprinting. Enable javascript and cookies only on selected sites. [GNU IceCat](https://www.gnu.org/software/gnuzilla/) is the best option.
* __Level 5__: Replace your e-mail provider with a more safe, more appropriate provider. A good option is [Tutanota](https://tutanota.com/), another alternative is [cock.li](https://cock.li/).
* __Level 6__: Use an e-mail client that can block web beacons (tracking pixels). Thunderbird is easy and has a plugin for this. Mailx, Mutt or Alpine are better options.
* __Level 7__ Use RSS for news from sites you trust and to order your podcasts instead of Youtube (although Youtube has an RSS feed for their channels too, for now). Liferea is easy and a great application for RSS feeds, newsboat and newsbeuter are command line options.
* __Level 8__ Use [Peertube](https://instances.joinpeertube.org/instances) for podcasts instead of Youtube.
* __Level 9__: Use [Mastodon](https://joinmastodon.org/) or install [Pleroma](https://github.com/wimvanderbauwhede/limited-systems/wiki/Mastodon-and-Pleroma-on-the-Raspberry-Pi-3) (GNU Social) instead of non-publicly auditable social networks known to sell private information.
* __Level 10__: Choose IRC instead of non-publicly auditable chat networks. A good and easy IRC application is Hexchat, other options are irssi and WeeChat. You can use [BitlBee](https://wiki.bitlbee.org/) to access other chat networks through an IRC client if you need.
* __Level 11__: Use GNU/Linux on your computers, preferably free from "systemd". PCLinuxOS is an easy first choice, Devuan is a better option. Stay away from something called BSD.
* __Level 12__: Install LineageOS on your phone and use F-Droid without gapps (Google app store), with IceCatMobile for web browser, KeePassDroid, AFWall+ and Android IMSI-Catcher Detector. Use Yalp Store or Aptoide (or download from apkmirror/apkpure) in combination with microG if you need a gapps app.

## Cautionary Level
* __Level 13__: Delete any metadata from files you share on the internet. ExifTool is the best tool.
* __Level 14__: Avoid using your real name online and avoid giving away any personal information, if possible log into sites using donated passwords and accounts from [BugMeNot](http://bugmenot.com).
* __Level 15__: Use [The Random Identity Generator](http://rig.sourceforge.net/) (rig) to generate different online personas when you need to create accounts. Don't reuse usernames, email addresses, etc, for different sites and don't mention your other identities to avoid contamination.
* __Level 16__: Anonymize your writting style for any text and document you upload with anti-stylometry software like [Anonymouth](https://github.com/psal/anonymouth).
* __Level 17__: Encrypt your e-mails with GnuPG when possible. Thunderbird has the Enigmail plugin for this, you can script the use of GPG on Mutt and Mailx.

## Medium Level Security
* __Level 18__: Uninstall network facing services like Avahi (Bonjour), CUPS (replace with Line Printer if needed), Telnet, the R-tools (rlogin, rsh, rcp, rwho, rexec), fingerd, RPC services (D-Bus) and uninstall services if unused like ssh/web/ftp/mail. Also disable IPMI on BIOS.
* __Level 19__: Use YaCy with collaborative database disabled when in need to search on the web.
* __Level 20__: Use the Tor Browser to navigate the internet through Tor.
* __Level 21__: Use Firejail or Bubblewrap to sandbox your applications.
* __Level 22__: Use an [OpenNIC provider](https://servers.opennicproject.org/) known to not save logs together with DNSCrypt to prevent DNS Leaking.
* __Level 23__: Use Uncomplicated Firewall ("ufw") to block inbound AND outbound network traffic, permitting only what you need. The graphical version ("Gufw") is beginner-friendly.
* __Level 24__: Use [Bastille Linux](http://bastille-linux.sourceforge.net/source.htm) to harden your system.
* __Level 25__: Use a source based distro, preferably without crypto libraries on its package manager (no Python), and tweak the installation files to use the minimum required dependencies. Gentoo is one option, CRUX is another and it is easy, see [this link](https://github.com/mayfrost/guides/blob/master/INITIATION.md).

## High Level Security
* __Level 26__: Use a command line web browser like links2 and only browse web pages without javascript or cookies when possible.
* __Level 27__: Set a tight configuration for iptables on each port open and drop packets for everything. Use nftables on newer kernels.
* __Level 28__: Use [qmail](https://www.schneier.com/blog/archives/2007/11/thoughts_on_the.html) for your own e-mail server. Exim and cmail are other options.
* __Level 29__: Use Squid for caching websites.
* __Level 30__: Set [BIND9](https://unix.stackexchange.com/questions/270716/configure-bind-as-forwarder-only-no-root-hints-encrypted-rpz-blacklist-wh/270796#270796) for caching all DNS queries on your local DNS server.
* __Level 31__: Use port forwarding and a port knocker on your router or server if you have services running, and unregister your reverse dns records.
* __Level 32__: Use Arpalert/ArpON (for Man-In-The-Middle -MITM- Detection), [zapret](https://github.com/bol-van/zapret) (for Deep Packet Inspection -DPI- Block and Circumvention), and Suricata/Snort (for Network Intrusion Detection).
* __Level 33__: Compile the kernel yourself and add only necessary features and selected modules. Enable KASLR and Capabilities on kernel configuration.
* __Level 34__: When possible give your applications a separate user account and use chattr, sudo, chroot, fakeroot, ulimit and quota with them.
* __Level 35__: Use Lynis to audit your system.
* __Level 36__: Use a complete host intrusion detection framework like Tiger, which can work with Samhain (for integrity check), Unhide/Chkrootkit/rkhunter (for rootkit detection), ClamAV/Linux Malware Detect and a system logger like sysklogd.
* __Level 37__: Use [RSBAC](https://www.rsbac.org/) (for RBAC) with AppArmor (for filesystem ACL).

## Physical Access Counter-Measures
* __Level 38__: Set a BIOS password (DON'T FORGET THIS PASSWORD!).
* __Level 39__: Use USBGuard (to prevent Juice Jacking).
* __Level 40__: Use disk encryption with cryptsetup (dm-crypt), saving the key on a separate USB that you keep with yourself at all times.
* __Level 41__: Move your boot partition to a USB and encrypt it with cryptboot. Use the option on Libreboot too.

## Costly Counter-Measures
* __Level 42__: Buy a separate camera and microphone and physically remove any camera and microphone from your computer.
* __Level 43__: Buy a VPS in a non-extradition, privacy friendly country outside the Five Eyes under a different name and with a good way of not getting traced by payments, set all outgoing traffic through it, then set up your own VPN server so you can audit all the traffic.
* __Level 44__: Buy a phone with Replicant and libre firmware. Tehnoetic sells an S3 phone with Replicant and only libre firmware enabled, so far is the best option.
* __Level 45__: Buy a router compatible with LibreCMC and install LibreCMC, keep it up to date, give it a strong password, set to monitor all traffic, and use previous techniques such as caching, port-forwarding, etc.
* __Level 46__: Buy a computer compatible with the Libreboot firmware and the Linux-libre kernel, then install both or buy it preinstalled. Thinkpads model x200, t400 and t500 are the best options. Remember to check a compatible Wi-Fi card and physically remove cables connecting cameras and microphones.

## Deterrent Counter-Measures
* __Level 47__: Learn to hack yourself first.
* __Level 48__: Use only libre software (software "free as in freedom").
* __Level 49__: Reduce the amount of software installed in your computer.
* __Level 50__: Opt for text-based programs with less library dependencies than their GUI counterparts.
* __Level 51__: Support the GPL license as to prevent proprietary license wrapping (as with BSD/MIT/Apache licenses). GPLv3 in specific to prevent tivoization, a hardware level lockout method.
* __Level 52__: Deduplicate efforts and converge strategies to achieve a "tight base system" in common (use the koan "if is not strictly necessary it should be strictly optional, but still optional"), and that means making things modular and avoiding unnecessary dependencies instead of trusting "crypto libraries" like in Python.

## Exit Level Security
* __Level 53__: Abandon "cloud computing" and traditional, non-publicly auditable, data mined networks and erase your online persona. Use exclusively peer-to-peer services with specific protocols instead of all-in-one networks. Use IRC for live chat, e-mail for direct contact, and NNTP for newsgroups (per topic forums, what "social media" should be). IRC, e-mail and torrent services are available inside i2p, as it is NNTPChan. Tor can serve as an outproxy for i2p to reach the regular web.
* __Level 54__: Abandon the Internet. Participate in local mesh networks and collaborate with global scale meshnet projects like [gternet](https://mesh.gentoo.today/wiki/Main_Page).
* __Level 55__: [Don't f\*ck it up](https://www.youtube.com/watch?v=J1q4Ir2J8P8). Protip: you can't.
