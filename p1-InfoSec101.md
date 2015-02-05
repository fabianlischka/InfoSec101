---
layout: page
title: InfoSec101
---

More secure...

- [Passwords](#steps-passwords)
- [Disk Encryption](#steps-diskencr)
- [Browsing](#steps-browse)
- [Virtual Private Networks](#steps-vpns)
- [Chat and Voice Calls](#steps-chat)
- [Cloud Storage](#steps-cloud)
- [Email](#steps-email)


### PHD comics on: Security in your neighbourhood coffee shop

![PHD comics: Coffee Security](http://www.phdcomics.com/comics/archive/phd080913s.gif)

from: "Piled Higher and Deeper" by Jorge Cham at [www.phdcomics.com](http://www.phdcomics.com/comics.php?f=1618)

---

   
## <a name="steps-passwords"></a> Passwords
    
### First Steps: Passwords

- Overall strategy:
    - Use one strong master password, and a password manager
- Strong passwords
    - Good technique: Use the 1st letter of a passphrase: 
        - "Wo hěn xǐhuān HK, IT security, and (sometimes) 9 hours sleep" turns into `WhxHK,ITs&(st)9hs`
        - Use a creative, weird, unique passphrase, possibly multi-language.
        - (Keep in mind that you might encounter different keyboard layouts when using other computers, eg when traveling)
    - Don't use [weak passwords](https://en.wikipedia.org/wiki/Password_strength#Examples_of_weak_passwords)
    - Test your passwords
        - Password "quality test" routines are available
        - Password quality can be measured in "time it takes to crack" or in "bits of entropy" (the more the better)
        - Note: do NOT type you passwords into some unknown webpage. Load the page in a fresh browser, disconnect internet/wifi, then enter your passwords to test, finally close the browser session before you go back online
        - [Password Tester](https://www.bennish.net/password-strength-checker/) based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with some links for background info. Click "Break it down!" to see the components.
        - [Password Tester](https://www.cygnius.net/snippets/passtest.html), also based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with a few examples.
    - Set your computer up so that the screen saver kicks in after 3 minutes. You'll have to type your password many times a day, and you'll get really fast, and won't ever forget it
- Security questions: avoid, or give bogus random unguessable answers like `T$adf^VFBG(*&O(N%R^BHN*UOI` (Needless to say, this can complicate things when you DO forget your password.)
- Multi-factor authentication
    - using a phone (SMS, app), dongle, or some other item a user always has at hand 
    - advantage: more secure
    - disadvantage: need device, and maybe phone reception 
        - what if you travel and have a new SIM in your phone? (Note: that's potentially when the 2FA kicks in, because "you're in an unusual location")
        - what if you lose your phone?
- Enable notifications of changes
    - Apple's iCloud notifies you when you change your password or amend personal information
    - Facebook notifies you when you log in from an unknown device
    
---
#### xkcd on: Passwords

![xkcd on passwords](http://imgs.xkcd.com/comics/password_strength.png)

from: "xkcd" by Randall Munroe at [xkcd.com](https://xkcd.com/936/)

Note: the password tester linked above, indeed, estimates 

- `Tr0ub4dour&3` to be cracked in 22 hours (30 bits), and 
- `correct horse battery staple` in centuries (63 bits), and 
- `WhxHK,ITs&(st)9hs` billions of centuries (over 100 bits). 

A password based on a long, creative passphrase might really be the state of the art.


---


### Suggested Tools: Password Managers

- Password Managers allow you to use different (secure) passwords for different sites
- Password Managers store these passwords securely
    - Storage locally (better security, less convenience)
    - Storage in the Cloud (easier sync, automatic backup, less secure)
- Password Managers require one Master Password 
    - it better be good! (ideally not used elsewhere before)
    - you better don't forget it! (use regularly, maybe deposit one backup on paper in your mom's bank safety deposit box)
- Available on desktop and smart phones
- Recommended:
    - If you use Apple products (computer and phone), and want a simple solution:
      - **iCloud Keychain**: Password manager. Safari only (OS X & iOS). Local plus iCloud. Commercial. Closed. Safe and easy if you use only Safari.  [Link](http://support.apple.com/en-us/HT5813)
    - If you want a free, open source solution:
      - **Password Safe, pwSafe**: Password manager, most platforms. Local plus sync options (iCloud, Dropbox). Open Source. Designed by security doyen Bruce Schneier.  [Link](http://pwsafe.org) 
      - **KeePass**: Password manager, most platforms. Local plus sync options (Dropbox, Google Drive). Open Source. Powerful, complicated. [Link](http://keepass.info)
    - If you're happy to pay for a commercial solution with support:  
      - **1Password**: Password manager, most platforms. Local plus sync options (iCloud, Dropbox). Commercial, expensive (USD 50). Closed. [Link](https://agilebits.com/onepassword)
      - **LastPass**: Password manager, most platforms. Cloud only. Commercial, basic use free, 12 USD/a for smartphone use. Closed. [Link](https://lastpass.com)
- Also see [Password managers on Prism Break](http://prism-break.org/en/all/#password-managers)

## <a name="steps-diskencr"></a> Disk Encryption

### First Steps: Disk Encryption

- protects the content of your laptop 
    - when it's stolen
    - when it's in the hand of government/border control
- without Disk Encryption, can just take out the harddrive from your laptop (or start it up in "Target Mode") and copy everything from it
- when turned on initially, will run a few hours in the background to encrypt everything

### Suggested Tools: Disk Encryption

- Automatically enabled in iOS 8, and Android L. Can be set up for earlier Android versions (from HoneyComb onwards?)
- Recommended:
  - **FileVault**: Disk Encryption, OS X. Set up in System Preferences -> Security & Privacy. [Link](http://support.apple.com/en-us/HT4790)
  - Windows: ??
- Careful:
  - **TrueCrypt** appears to have some issues, the developers don't recommend its use anymore
- Also see [Disk Encryption on Prism Break](http://prism-break.org/en/all/#disk-encryption)

## <a name="steps-browse"></a> Browsing

### First Steps: Browsing

- Search engines and social networks collect a lot information about you (even while you visit other websites), and sell it. 
- Facebook is notified whenever you visit one of the millions of sites that has a "Like" button. Similarly for Twitter, Google, etc.
- For example, if you read an article in the NY Times about depression, or HIV treatment, or bankruptcy law, Facebook and Google will be notified that that is an interest of yours (and their Terms of Service will specify whether they're allowed to serve you related ads, save the information, or sell it - good luck finding out).
- How unique is your browser setup? Can you be uniquely identified by your browser alons? Find out with [Panopticlick](https://panopticlick.eff.org) from the EFF.
- From your IP address, your approximate location can be determined. See for example [IPLeak](http://ipleak.net).
- A few steps you can take:
    - Regularly delete all cookies/history
    - Browse in Private mode ("porn mode")
    - Use different browsers for different tasks (private/job/sensitive)
    - Install some of the tools in the next section
- If you ignore warnings about security certificates, MITM ("men in the middle") attackers could read all your traffic (incl. password)
- Always use HTTPS, if possible, as it encrypts your traffic. Some browser extensions do this for you automatically
- Some background:
    - ["Getting to know you"](http://www.economist.com/news/special-report/21615871-everything-people-do-online-avidly-followed-advertisers-and-third-party), The Economist, part of an insightful [Special Report: Advertising and Technology](http://www.economist.com/news/special-report/21615869-technology-radically-changing-advertising-business-profound-consequences).
    - ["Can't trust Uber"](http://www.nytimes.com/2014/12/08/opinion/we-cant-trust-uber.html?_r=0), in the NY Times
    - ["DEFCON 19: Tracking the Trackers: How Our Browsing History Is Leaking into the Cloud"](https://www.youtube.com/watch?v=BK_E3Bjpe0E), Youtube
    
    
### Suggested Tools: Secure Browsing - Search Engines
- Note: If you use DuckDuckGo, you can easily pull up other results:
    - append "!s" to be redirected to StartPage's results 
    - append "!g" to be redirected to Google's results (which will track you)
    - append "!v" to be redirected to Youtube (video search)
    - and [more](http://imlefthanded.com/my-favourite-duckduckgo-bangs/), [many more](https://duckduckgo.com/bang.html)
- Recommended Search Engines:
  - **DuckDuckGo**: Anonymous, unlogged web search. Can be set as default in many browsers, including Safari. [Link](https://duckduckgo.com)
  - **Ixquick**: Anonymous, unlogged web search, using non-Google sources. [Link](https://www.ixquick.com)
  - **StartPage**: Anonymous, unlogged web search, using Google as the source. [Link](https://startpage.com)
- Not recommended: Bing, Google, Yahoo
- Also see [Web Search on Prism Break](http://prism-break.org/en/all/#web-search)

### Suggested Tools: Secure Browsing - Browser Addons

- Recommended Tools:
  - **Adblock Plus**: Blocks ads when browsing. Android, Chrome, Firefox, IE, Opera, Safari. Lets “acceptable ads” through by default. [Link](https://adblockplus.org)
  - **AlwaysHTTPS**: Encrypts your browsing with many websites. Firefox, Chrome, Opera [Link](https://www.eff.org/https-everywhere)
  - **Ghostery**: Stops trackers when browsing. Uploads anonymized tracker data by default. Firefox, Chrome, Opera, Safari [Link](https://www.ghostery.com/en/)
  - **Privacy Badger**: Stops advertisers and trackers when browsing. Firefox, Chrome. From the EFF. [Link](https://www.eff.org/privacybadger)
    
- Alternatives:
  - **Adblock**: Blocks ads when browsing. Chrome, Firefox, Opera, Safari. “Pay what you want”. [Link](https://getadblock.com)
  - **Adblock Edge**: Blocks ads when browsing. Firefox. [Link](https://addons.mozilla.org/en-US/firefox/addon/adblock-edge/)


- Note: On Android, some of these apps are banned from the Play Store, because they  interfere with Google's business model. [Source: Disconnect Blog](https://blog.disconnect.me/blog/google-just-banned-our-new-android-app-before-it-even-launched-another-example-of-why-privacy-friendly-alternatives-for-android-app-distribution-are-critically-important)
- Also see [Browser Addons on Prism Break](http://prism-break.org/en/all/#web-browser-addons), and a [comparison](http://www.areweprivateyet.com)

### Advanced Steps: Browsing

- For further anonymity, use [TOR (The Onion Router)](https://www.torproject.org), a stand-alone application available for most platforms
- TOR routes all your traffic through a few extra hops, encrypted, so that the website you are visiting does not know who it's talking to, and interceptors near you don't know what websites you're visiting
- Note: the traffic from the final TOR node to your destination is not encrypted (unless you use HTTPS). The final TOR node might monitor it, and it might be run by three-letter-organisations.
    - It would not be sensible to divulge private information when using TOR
    - Don't log into any website (Facebook, etc.)
    - Don't use your real name, or google yourself
    - Don't open documents downloaded through Tor while online.
- The [TOR download page](https://www.torproject.org/download/download-easy.html.en) lists several security precautions; read them.


### Suggested Tools: Secure Browsing - TOR

- Recommended Tools:
  - **OnionBrowser**: Anonymous browsing (TOR) for iOS. Open source [Link](https://mike.tig.as/onionbrowser/)
  - **OrBot**: Anonymous browsing (TOR) for Android. [Link](https://guardianproject.info/apps/orbot/)
  - **TorBrowser**: Anonymous browsing (TOR) for Linux, OS X, Windows. [Link](https://www.torproject.org)
  
- Also see [Web Browser on Prism Break](http://prism-break.org/en/all/#web-browsers)

## <a name="steps-vpns"></a> Virtual Private Networks

### First Steps: VPNs

- "Virtual Private Network"
- secures the connection ...
    - from your device all the way...
    - to a specific exit node "somewhere" (you can choose)
- from the exit node, the traffic goes (normally) to its destination
- protects from interception "nearby" (Internet Cafe, your ISP, local gov't)
- allows to circumvent censorship, eg when traveling in China, Iran
    - have to enable SSL for that (or SSH tunnel, possibly)

### Suggested Tools: VPNs

- many providers, but there is no free lunch: expect to pay for good service (about USD 5/month). Some good providers:
    - **AirVPN**: Excellent VPN, strong commitment to security & privacy. Run by activists in Italy. Three connections per account. Unix, OS X, Win, iOS, Android. [Link](https://airvpn.org)
    - **ZenMate**: Browser add-on. Routes only browser through a VPN, NOT other apps (Mail, Messenger, etc.). Free. Chrome, FireFox, Opera. [Link](https://zenmate.com)
- to test whether the VPN works correctly, visit [IPLeak](http://ipleak.net), for example, and see what it thinks your IP address and location are.

## <a name="steps-chat"></a> Chat and Voice Calls

### First Steps: Secure Chat and Voice Calls

- Unfortunately, the most popular apps are spectacularly insecure
- Fortunately, there are some decent and free alternatives out there!
- Levels of security
    - Many apps don't encrypt content at all, or badly. Not recommended. Very dangerous, as your conversations could easily be intercepted or altered by:
        - the café whose Wifi you are using, 
        - your internet service provider, 
        - your government,
        - the company/provider.
    - Some apps encrypt the communication all the way to their server, and from there to the other device. Careful, only partial encryption! 
        - This is fairly secure against random hackers, or the café whose Wifi you are usin. 
        - However, nobody knows what happens on the server itself. 
        - Your government could have a pipe to there, or 
        - the company itself could spy on it, analyse it, sell it.
    - The most secure is end-to-end encryption, meaning only the two devices that are communicating know the keys, and NOBODY inbetween can decrypt what is happening. Recommended.
        - However, meta data (with whom do you chat how often how much) can still be seen with some of these.
- MITM (man in the middle attack)
    - One weakness of end-to-end encryption is the [man-in-the-middle attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack). 
    - To circumvent that, the software shows you something representing the key used, such as a two-word phrase, or a square pixely picture. You should compare with the person that you're communicating with, on a second independent channel, to ensure that you're both talking to each other without anyone in the middle.


### Suggested Tools: Secure Chat (Text)

(Note: The EFF score refers to the [EFF ScoreCard](https://www.eff.org/secure-messaging-scorecard) for secure messaging.)

- Recommended
  - **CryptoCat**: Anonymous chat. Just choose a topic, and tell your friends. End-to-end encrypted. Open source. EFF score 7/7. [Link](https://crypto.cat/)
  - **iMessage**: End-to-end encrypted. Closed source. Apple only. EFF score 5/7 [Link](https://www.apple.com/ios/messages/)
  - **Telegram**: End-to-end encrypted (“secret Chat” only!). Closed source. EFF score 5/7. Desktop versions available. [Link](https://telegram.org/)
  - **TextSecure**: End-to-end encrypted. Android, but iOS version on the way. Open source. EFF score 7/7. [Link](https://whispersystems.org/)
  - **Threema**: End-to-end encrypted. Closed source. EFF score 5/7 [Link](https://threema.ch/en)

- Recommended for advanced users:
  - **Adium**: OTR chat for OS X, EFF score 6/7. A bit clunky. [Link](https://www.adium.im)
  - **ChatSecure**: OTR chat for iOS, Android. A bit clunky. EFF score 7/7. [Link](https://chatsecure.org/)
  - **Pidgin + OTR**: OTR chat for Windows, EFF score 7/7 [Link](https://otr.cypherpunks.ca)

- Careful, only partial encryption: AIM, Blackberry Messenger, Facebook Chat, IRC, Line, Telegram non-secret and groups, WhatsApp, Yahoo Messenger
- Not recommended at all: Firechat, Google Hangout, Google Talk Talk, ICQ, Kik, Kaoko, QQ, Snapchat, Viber, WeChat, Whisper
- Not recommended at all: SMS

- Also see the [EFF ScoreCard](https://www.eff.org/secure-messaging-scorecard)
- Also see [Prism Break on Instant Messaging](http://prism-break.org/en/all/#instant-messaging)

### Suggested Tools: Secure Voice calls

  - **Signal/Redphone**: Free, encrypted calls. EFF score 7/7 [Link](https://whispersystems.org/blog/signal/)

- Careful, only partial encryption: Google Hangout (Voice/Video)
- Not recommended: Normal phone calls, Skype

- Also see [Prism Break on Video/Voice](http://prism-break.org/en/all/#video-voice)

## <a name="steps-cloud"></a> Cloud Storage

### Suggested Tools: Cloud Storage

- Careful, only partial encryption: Dropbox, Google Drive, iCloud
- Not recommended at all: 360 Cloud Disk, Baidu Cloud Disk, QQ Net Disk

- Also see [Prism Break on File Storage](http://prism-break.org/en/all/#file-storage-sync)

## <a name="steps-email"></a> Email

### Advanced Steps: Secure Email

- GPG allows secure sending of email including attachments
- However, meta data is NOT encrypted/protected
    - sender, recipient
    - subject line
    - length


### Suggested Tools: Secure Email

- The standard for asymmetric encryption is PGP/GPG
- (PGP = "Pretty Good Privacy" is the original implementation, OpenPGP is the open internet standard, and GPG = "Gnu Privacy Guard" is an open source implementation. Bottom line: all the same)
- For key management, consider [keybase.io](https://keybase.io)
- Recommended:
  - **GPG4Win**: GPG for Windows. [Link](http://www.gpg4win.org/)
  - **GPGTools**: not free. GPG on OS X Mail. EFF score 5/7. [Link](https://gpgtools.org)
  - **iPGMail**: not free. GPG for iOS Mail. Closed source. EFF score 4/7. [Link](https://ipgmail.com/)
- Not recommended at all for sensitive information: Normal email


## Miscellanous

### Phishing

- ie Emails that pretend to be from an official source, ie a bank or so, and goad you into "logging in" with your real credentials on a fake website
- Note:
    - a link can have some legitimate text (http://www.mybank.com), but point somewhere else (http://phishingsite.xyz). One can see where a link leads to by 
        - hovering over it (OS X)
        - tap-and-holding a link (iOS)
    - the server (whatever is before the first slash) must be read from right to left (so, this is not a good link: www.mybank.com.domain.bla.phishingsite.xyz/login.html)
- Prevention:
    - don't click on links in emails to "log in" somewhere
    - check the exact name of the website, and the "lock" symbol


### Malware

- a Trojan Horse is malicious software packaged to look like something desirable, tricking the user into actively installing it.
    - spammy websites claim that your computer is infected by a virus, and offer a free "virus scanner" for download. Actually, it is this "virus scanner" that is the malware.
    - a popular early Android app was a free flashlight app. However, it uploaded all the user's contact data, location, etc. to the provider, who sold it.

### Multiple Accounts

- consider having multiple separated accounts on your machine, for 
    - work
    - fun
    - private
    - sensitive projects etc.
- use shared folders to move information between them in a controlled matter
- a bit of inconvenience because you have to re-enter passwords etc., but it makes leaks of information much harder

### Defense in Depth

- Defense in Depths: the idea that multiple layers of protection might be best
- If the adversary breaks one layer, the information is still protected
- for example:
    - agree on code words for sensitive entities
    - transmit part of the information in iMessage, part on Signal/Redphone, part on Telegram, part on Wickr, such that having any one part is pretty useless
    - use TOR over a VPN
    - etc.
    
### Information Leaks

- If you give someone information, you might reveal more than you thought:
    - Your phone number, email can be googled: what to they reveal?
    - Reverse Image Search sites such as [TinEye](http://tineye.com) or [Google](http://www.google.com/insidesearch/features/images/searchbyimage.html) allow someone to see whether a picture appears elsewhere on the net, eg Facebook, LinkedIn, Twitter, or your employer's website
    - A picture contains embedded information ("[EXIF data](https://en.wikipedia.org/wiki/Exchangeable_image_file_format)") that frequently contains the time and location the picture was taken
    - As discussed, the IP address of your computer can lead to you, or your ISP.

