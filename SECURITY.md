SECURITY TIPS in order of difficulty (not meant to be followed step by step, although it is recommended):

Level 1: Avoid using your real name online and avoid giving away any personal information. You can use The Random Identity Generator (rig) to generate an online persona and/or login sites using passwords from bugmenot.com.
Level 2: Don't save your passwords on plaintext or in some "cloud" service like Lastpass and don't save logins on your phone or web browser. Create and remember one good main password (must have lowercase, uppercase, numbers and symbols, be longer than 8 characters and be change bimonthly), use KeePassX (and I mean the one with an X) and use the option to generate different passwords for each account you have. Other option is kpcli which works on the command line and is just a perl script (the best option).
Level 3: When possible opt for IRC instead of non-publicly auditable chat networks. A good and easy IRC application is Hexchat, another is irssi (best option). You can use BitlBee to access other chat networks through an IRC client if you need.
Level 4: Use Searx instead of Google when in need to search on the web.
Level 5: When possible opt for Mastodon (GNU Social) instead of non-publicly auditable social networks known to sell private information.
Level 6: Replace your e-mail provider with a more safe, more appropriate provider. A good option is cock.li.
Level 7: Use an e-mail client that can to block web beacons (tracking pixels). Thunderbird is easy and has a plugin for this, Mutt or Alpine are better options.
Level 8: Encrypt your e-mails with GnuPG. Thunderbird has the Enigmail plugin for this, you can can script the use of GPG on Mutt.
Level 9: Delete any metadata from files you share on the internet. MAT is an easy tool for this, ExifTool is a better option.
Level 10: Anonymize your writting style on any text with anti stylometry software like Anonymouth when you share documents.
Level 11: Use your web browser with javascript, cookies and any telemetry (like "pocket", geolocation and WebRTC) disabled and reduce the browser fingerprinting. Enable javascript and cookies only on selected sites. GNU IceCat is the best option, Firefox works too
---Start of medium level security---
Level 12: Install LineageOS on your phone and use F-Droid without gapps (Google app store), with IceCatMobile for web browser, KeePassDroid, AFWall+ and Android IMSI-Catcher Detector. Use Yalp Store or Aptoide (or download from apkmirror/apkpure) with microG if you need a gapps app.
Level 13: Use GNU/Linux on your computers, preferably free from "systemd". PCLinuxOS is an easy first choice, Devuan is a better option. Stay away from something called BSD.
Level 14: Uninstall Avahi, CUPS (replace with Line Printer if needed), Telnet, the R-tools (rlogin, rsh, rcp, rwho, rexec), fingerd, and if unused uninstall services like ssh/web/ftp/mail.
Level 15: Use Uncomplicated Firewall to block inbound AND outbound network traffic, permitting only what you need.
Level 16: Use Firejail or Bubblewrap to sandbox your applications.
Level 17: When possible give your applications a separate user account and use sudo, chroot, fakeroot, ulimit and quota with them.
Level 18: Use DNSCrypt to prevent DNS Leaking with an OpenNIC provider known to not save logs.
Level 19: Use YaCy with collaborative database disabled when in need to search on the web.
Level 20: Use the Tor Browser to navigate the internet through Tor.
Level 21: Use cmail in your own server for e-mail. Exim with Dovecot is another option, as is OpenSMTPD.
Level 22: Use Squid for caching websites.
---Measures that cost money---
Level 23: Buy a VPS in a non-extradition, privacy friendly country outside the Five Eyes under a different name and with a good way of not getting traced by payments, then set up your own VPN server so you can audit all the traffic.
Level 24: Buy a phone with Replicant and libre firmware. Tehnoetic sells an S3 phone with Replicant and only libre firmware enabled, so far is the best option.
Level 25: Buy a router compatible with LibreCMC and install LibreCMC, keep it up to date and give it a strong password.
Level 26: Buy a computer compatible with the Libreboot firmware and the Linux-libre kernel, then install both or buy it preinstalled. Thinkpads model x200, t400 and t500 are the best options.
---Start of physical access measures---
Level 27: Set a BIOS password (DON'T FORGET THIS PASSWORD!).
Level 28: Use USBGuard (to prevent Juice Jacking).
Level 29: Use disk encryption with cryptsetup (dm-crypt), saving the key on a separate USB that you keep with yourself at all times.
Level 30: Move your boot partition to a USB and encrypt it with cryptboot. Use the option on Libreboot too.
---Start of high level security---
Level 31: Use a source based distro, preferably without crypto libraries on its package manager (no Python). Source Mage is advised and it is easy to setup.
Level 32: Set a tight configuration for iptables on each port open and drop packets for everything. Use nftables on newer kernels.
Level 33: Use port forwarding and a port knocker on your router or server and unregister your reverse dns records.
Level 34: Use the IRC, e-mail and torrent services available inside i2p, and use Tor as an outproxy for i2p when in need to access the regular web (only for browsing).
Level 35: Use a command line browser like links2 to browse web pages.
Level 36: Use Bastille Linux to harden your system.
Level 37: Use Lynis to audit your system.
Level 38: Use Arpalert/ArpON (for Man-In-The-Middle -MITM- Detection) and Suricata/Snort (for Network Intrusion Detection).
Level 39: Use a complete host intrusion detection framework like Tiger, which can work with Samhain (for integrity check), Unhide/Chkrootkit/rkhunter (for rootkit detection), ClamAV/Linux Malware Detect and a system logger like sysklogd.
Level 40: Use RSBAC (for RBAC) with AppArmor (for filesystem ACL).
Level 41: Compile the kernel yourself and add only necessary features and selected modules. Enable KASLR and Capabilities on kernel configuration.
---Start of deterrent measures---
Level 42: Learn to hack yourself first.
Level 43: Use only libre software (software "free as in freedom").
Level 44: Reduce the amount of software installed in your computer.
Level 45: Opt for text-based programs with less library dependencies than their GUI counterparts.
Level 46: Support the GPL license as to prevent proprietary license wrapping (as with BSD/MIT/Apache licenses). GPLv3 in specific to prevent tivoization, a hardware level lockdown method.
Level 47: Deduplicate efforts and converge strategies to achieve a "tight base system" in common (use the koan "if is not strictly necessary it should be strictly optional, but still optional"), and that means making things modular and avoiding unnecessary dependencies instead of trusting "crypto libraries" like in python.
Level 48: Abandon "cloud computing" and traditional, non-publicly auditable, data mined networks and erase your online persona. Use exclusively peer-to-peer services with specific protocols instead of all-in-one networks.
Level 49: Abandon the Internet. Participate in local mesh networks and collaborate with global scale meshnet projects like gternet.
Level 50: Don't f*ck up. Protip: you can't.
