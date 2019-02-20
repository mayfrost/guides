# WEB BROWSER

## GNU ICECAT
* Download from http://ftpmirror.gnu.org/gnuzilla/
* Unpack the tarball
* As ROOT, copy and rename the folder as /opt/icecat
* ln -s /opt/icecat/icecat /usr/bin/icecat

## ADDONS
These addons worked excellent to cover any fingerprinting, until Mozilla decided to break things since Firefox 52.
* (Cross-)Site Request, Anti-XSS, Trackers, Referer, Cookies: [uMatrix](https://addons.mozilla.org/en-US/firefox/addon/umatrix/)
* Security Settings: [Privacy Settings](https://addons.mozilla.org/en-US/firefox/addon/privacy-settings/)
* User-Agent: [Random Agent Spoofer](https://github.com/dillbyrne/random-agent-spoofer), [User-Agent JS Fixer](https://web.archive.org/web/20170915181027/https://addons.cdn.mozilla.net/user-media/addons/378075/user_agent_js_fixer-1.3-fx.xpi?filehash=sha256%3Ae2b49993dacb136ae791eac8ad31d497fd1a3b07994b49d6f94866266eaded91)
* Plugin Enumeration: [Disable plugin enum](https://github.com/dillbyrne/random-agent-spoofer/issues/283) (see Mechazawa's script, and install with greasemonkey)
* Content Delivery Blocker: [Decentraleyes](https://addons.mozilla.org/en-US/firefox/addon/decentraleyes/)
* URI Leak: [No Resource URI Leak](https://notabug.org/desktopd/no-resource-uri-leak)
* Canvas-Fingerprinting: [Canvas Defender](https://addons.mozilla.org/en-US/firefox/addon/no-canvas-fingerprinting/)
* SSL (strict HTTPS): [HTTPS by default](https://addons.mozilla.org/en-US/firefox/addon/https-by-default/)
* URL Deobfuscator: [Pure URL](https://addons.mozilla.org/en-US/firefox/addon/pure-url/)
* Google Redirection: [Google search link fix](https://addons.mozilla.org/en-US/firefox/addon/google-search-link-fix/)

## ABOUT\:CONFIG
These tips prevent overflow your root directory or getting constantly write and delete to try and kill your drive.
* Go to _about\:config_
* Put a 0 to everything that can write to the disk.
* Limit ram memory and also turn off syncing ect.
* Make it read only.
* If you need to save things have a seperate chroot with a seperate physical drive and make that your downloads folder.
