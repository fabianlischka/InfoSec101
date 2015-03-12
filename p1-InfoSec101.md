---
layout: page
title: InfoSec101
---

- [Passwords & Phishing](#steps-passwords)
- [Disk Encryption](#steps-diskencr)
- [Cloud Storage](#steps-cloud)
- [Browsing](#steps-browse)
- [Virtual Private Networks](#steps-vpns)
- [Email](#steps-email)
- [Chat and Voice Calls](#steps-chat)


### PHD comics on: Security in your neighbourhood coffee shop

![PHD comics: Coffee Security](../public/images/PhD-comics-1618-coffee-security.gif)

from: "Piled Higher and Deeper" by Jorge Cham at [www.phdcomics.com](http://www.phdcomics.com/comics.php?f=1618)

---


## <a name="steps-passwords"></a> Passwords & Phishing

### Passwords: The problem

- How do hackers attack passwords? Three ways:
    1. Try and error, using common passwors (*dictionary attack*), and some rules (append `123`, etc.)
        - Computers can try **lots** of combinations in a short time
        - The "dictionaries" used are comprehensive and smartly compiled
    2. Hack into a site, and get the usernames and passwords (*Database breach*)
        - Properly implemented websites store passwords in a way that makes this nearly impossible
        - Many sites are not properly implemented though...
        - Now, use the passwords learned from this breach, and try them on other sites (email accounts, bank accounts, twitter, ...)
    3. Social engineering (*"I lost my password"*)
        - Hackers just click on "I lost my password", then answer the security questions (with information gleaned from public sources, or via "social engineering")
            - Name of my primary school
            - Mother's maiden name
            - Birthday
        - Hackers call, and pretend to be the owner of the account, ask for password reset
- How can we protect against this? Three counter measures:
    1. Use good passwords, hard to guess
    2. Don't re-use passwords across sites
    3. Disable "Security Questions" (eg give bogus answers)
- Problem: These counter measures conflict!
    - Passwords that are hard to guess are hard to remember... 
    - Now have a different one for every site, and you have to remember many! 
    - And, without security questions, you cannot recover it when you (inevitably) forget one!
- Solution: Password manager
    
    
### First Steps: Passwords

- Overall strategy:
    - Use one or two strong *master passwords*, and a password manager
    - Let the password manager create random passwords for all websites etc.
- Weak passwords & common mistakes
    - Avoid [weak passwords](https://en.wikipedia.org/wiki/Password_strength#Examples_of_weak_passwords), such as `password, letmein, secret`
    - Avoid:
        - names of pets or significant others
        - sports teams
        - swear words, sexual words (no need to list them, but no, `696969` is not secure)
        - family-related or religious words (`love`, `jesus`, `angel`, `lord`)
        - words related to the site (eg `job, career, link` for linkedin)
        - generally, dictionary words, unless multiplie unusual ones
        - simple patterns (`1234`, `qwerty`, `abcd`, `1qaz`)
        - post codes, birthdays, years, etc.
    - Don't rely on simple tricks, they're all well known!
        - appending numbers (`password123`) is not secure
        - simple substitutions (`733t spe@k, Tr0ub4dour&3, p@55word`) are not secure
        - simple composition of common patterns is not secure (`ilovejesus123`)
    - Some examples of bad passwords from the 2012 LinkedIn breach and the 2010 Gawker breach:
![PopularPasswords](../public/images/popular-passwords.jpg)
- Strong passwords & best practice
    - Good technique 1: Use the 1st letter of the words of a long, unique sentence (the *passphrase*). This is the [Schneier Scheme](https://www.schneier.com/blog/archives/2014/03/choosing_secure_1.html):
        - *Example:* "Wo hěn xǐhuān HK, IT security, and (sometimes) 9 hours sleep" turns into `WhxHK,ITs&(st)9hs`
        - *Eample:* "When I was 18 I dated Miranda Kerr for atleast 2 weeks, no seriously" turns into `WIw18IdMKfa2wns`
        - Use a creative, weird, unique passphrase, possibly multi-language.
        - Don't use a well known catch phrase, song lyrics, movie quote etc. Make up your own phrase!
        - Should be a long phrase, resulting in at least 12 characters, including numbers, small/capital letters, symbols, etc. (beyond simple substitution)
        - Check that the result does not accidentally contain existing words, acronyms, etc.
        - (Keep in mind that you might encounter different keyboard layouts when using other computers, eg when traveling)
    - Good technique 2: Use 4 or 5 *randomly* selected words from a large dictionary, maybe each truncated at 5 or 4 characters
        - *Example:* "keelhaul", "cleistogamy", "evince", "vacuum" turns into `keel3clei6evin9vacu`
    - Maybe: Test your passwords
        - Password "quality test" routines are available
        - Password quality can be measured in
            - "time it takes to crack" or in
            - "bits of entropy", denoting essentially how many combinations one has to try systematically to come across it
            - the more the better
        - There are websites available allowing you to test the quality of your password
            - **Important**: do *NOT* just type important passwords into a webpage (that you're not logging in to), they could be collecting passwords.
            - If you want to use the password testers below:
                1. Load the page in a fresh browser (Safari/Firefox/IE),
                2. disconnect internet/wifi,
                3. then enter your passwords to test,
                4. finally *quit* the browser before you go back online
            - [Password Tester](https://www.bennish.net/password-strength-checker/) based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with some links for background info. Click "Break it down!" to see the components.
            - [Password Tester](https://www.cygnius.net/snippets/passtest.html), also based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with a few examples.
    - Set your computer up so that the screen saver kicks in after 3 minutes. You'll have to type your password many times a day, and you'll get really fast, and won't ever forget it
- Security questions: very problematic
    - One of the most common ways that accounts are compromised (particularly for "celebrities", for whom a lot of information is publically available)
    - Thus:
        - avoid, or 
        - give bogus answers
            - Like `T$adf^VFBG(*&O(N%R^BHN*UOI`
            - Needless to say, this can complicate things when you DO forget your password.
            - However, you can store these bogus answers in your password manager!
- Multi-factor authentication
    - something you *know* plus something you *have*
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
- `WhxHK,ITs&(st)9hs` billions of centuries (over 100 bits), and
- `keel3clei6evin9vacu` in centuries (73 bits).

A password based on a long, creative passphrase might really be the state of the art.


---


### Suggested Tools: Password Managers

- Purpose: Password Managers allow you to use different (secure) passwords for different sites
- Password Managers store these passwords securely
    - Storage locally (better security, less convenience)
    - Storage in the Cloud (easier sync, automatic backup, less secure)
- Password Managers require one Master Password
    - It better be good! (ideally not used elsewhere before)
    - You better don't forget it! (use regularly, maybe deposit one backup on paper in your mom's bank safety deposit box)
- What: App or browser addin, available on computers and smart phones
- Recommended:
    - If you use Apple products (computer and phone), and want a simple solution:
      - **iCloud Keychain**: Password manager. Safari only (OS X & iOS). Local plus iCloud. Commercial. Closed. Safe and easy if you use only Safari.  [Link](http://support.apple.com/en-us/HT5813)
    - If you want a free, open source solution:
      - **Password Safe, pwSafe**: Password manager, most platforms. Local plus sync options (iCloud, Dropbox). Open Source. Designed by security doyen Bruce Schneier.  [Link](http://pwsafe.org)
      - **KeePass**: Password manager, most platforms. Local plus sync options (Dropbox, Google Drive). Open Source. Powerful, complicated. [Link](http://keepass.info)
    - If you're happy to pay for a commercial solution with support:
      - **1Password**: Password manager, most platforms. Local plus sync options (iCloud, Dropbox). Commercial, expensive (USD 50). Closed. [Link](https://agilebits.com/onepassword)
      - **LastPass**: Password manager, most platforms. Cloud only. Commercial, basic use free, 12 USD/a for smartphone use. Closed. [Link](https://lastpass.com)
- Disadvantages:
    - Can be somewhat cumbersome, particularly sync between devices
    - If the app or password store is compromised, all your paswords are exposed
- Also see [Password managers on Prism Break](http://prism-break.org/en/all/#password-managers)


### First Steps: Avoid Phishing

- Very common and surprisingly effective attack.
- AP Twitter account hacked by phishing. [Source: BBC](http://www.bbc.co.uk/news/world-us-canada-21508660)
![AP Twitter White House](../public/images/AP-Twitter-WhiteHouse.jpeg)

- What is it?
    - emails etc. that pretend to be from an official source, ie a bank or so, and
    - lure you to a malicious website, where either
        - you "log in" with your real credentials on a fake site or
        - are hit a "drive-by" attack by just viewing the page
- Note:
    - a link can have some legitimate text (http://www.mybank.com), but point somewhere else (http://phishingsite.xyz). One can see where a link leads to by
        - hovering over it (OS X)
        - tap-and-holding a link (iOS)
    - the server (whatever is before the first slash) must be read from right to left (so, this is not a good link: www.mybank.com.domain.bla.phishingsite.xyz/login.html)
- Prevention:
    - be suspicious of unexpected, somewhat generic emails
    - read the link before you click (*actual* link, not displayed)
    - don't click on links in emails to "log in" somewhere
        - use your own bookmarks, or just type it in
    - check the exact name of the website, and the "lock" symbol
    - never provide your password to anyone, except the *actual* website it's for

### Malware

- Rule of thumb: if it's free, it's crap.
- Trojan Horse: malicious software packaged to look like something desirable, tricking the user into actively installing it.
    - spammy websites claim that your computer is infected by a virus, and offer a free "virus scanner" for download. Actually, it is this "virus scanner" that is the malware.
    - a popular early Android app was a free flashlight app. However, it uploaded all the user's contact data, location, etc. to the provider, who sold it.
- Don't install arbitrary "disk cleaners", "search bars", etc.
- Don't install anything unless absolutely necessary, and only from a trusted source
- Don't open untrusted attachments
- Don't plug in untrusted USB sticks

- Also see [Human Security on riseup.net](https://help.riseup.net/en/security/human-security)

## <a name="steps-diskencr"></a> Disk Encryption

### First Steps: Disk Encryption

- Purpose: Protects the content of your laptop
    - when it's stolen
    - when it's in the hand of government/border control
- What: App, or embedded in the operating system
- How: Encrpyts your entire harddrive, and decrypts what's needed on the fly
    - Without Disk Encryption, can just take out the harddrive from your laptop (or start it up in "Target Mode") and copy everything from it, without logging in
    - When Disk Encryption turned on initially, will restart and run a few hours in the background to encrypt everything
- Disadvantages: Might be ever so slightly slower on old hardware

### Suggested Tools: Disk Encryption

- Automatically enabled in iOS 8, and Android L. Can be set up for earlier Android versions (from HoneyComb onwards?)
- Recommended:
  - **FileVault**: Disk encryption. OS X. Enable in System Preferences -> Security & Privacy. Requires restart. [Link](http://support.apple.com/en-us/HT4790)
  - **BitLocker**: Disk encryption. Windows. [Link](http://windows.microsoft.com/en-US/windows7/products/features/bitlocker) 
- Careful:
  - **TrueCrypt** appears to have some issues, the developers don't recommend its use anymore
- Also see [Disk Encryption on Prism Break](http://prism-break.org/en/all/#disk-encryption)

### Deleting Data

- When data is deleted on a modern OS, it is just moved into the trash folder
- When the trash folder is emptied, only the "directory link" to the data is deleted, thus rendering it invisible, and liable to be overwritten in the future when more space is required. The actual data is still there and can, for a while, be recovered with special software (or even "forensic" hardware that carefully examines the magnetic platter and figures out whether a 0 or 1 was stored there!)
- Really sensitive data: Chose "Secure Erase", which will overwrite the deleted data several times with random bits, thus rendering it pretty illegible
- Don't forget backups and cloud syncing! Data might still lurk there.
- Note: if you use disk encryption, this is not a problem (even if the bits are recovered, they make no sense without the password)

## <a name="steps-cloud"></a> Cloud Storage

### First Steps: Cloud Storage

- Be aware of what is in the cloud
- iOS/OS X keep your contacts, calendars, photos in iCloud
    - The iCloud celebrity photo hack was most likely a mix of bad passwords and social engineering

### Suggested Tools: Cloud Storage

Most well known tools cannot be recommended, but SpiderOak is a better version of DropBox, and BitTorrentSync a good alternative for many purposes.

- Recommended:
  - **BitTorrentSync**: Distributed backup, alternative to Cloud storage. All platforms.  [Link](https://www.getsync.com)
      - Allows you to share and sync folders across devices that you choose (your own, or eg among a group of people) 
  - **SpiderOak**: Cloud backup. Encrypted. All platforms. [Link](https://spideroak.com)
      - Like DropBox, but better encryption.
- Careful, only partial encryption: Dropbox, Google Drive, iCloud
- Not recommended at all: 360 Cloud Disk, Baidu Cloud Disk, QQ Net Disk
- Note: Whatever you encrypt yourself with PGP you can put on any cloud server, as it can't be decrypted without your private key

- Also see [Prism Break on File Storage](http://prism-break.org/en/all/#file-storage-sync)

## <a name="steps-browse"></a> Browsing

### First Steps: Browsing

- Search engines and social networks collect a lot information about you (even while you visit other websites), and sell it.
- Facebook is notified whenever you visit one of the millions of sites that has a "Like" button. Similarly for Twitter, Google, etc.
- For example, if you read an article in the NY Times about depression, or HIV treatment, or bankruptcy law, Facebook and Google will be notified that that is an interest of yours (and their Terms of Service will specify whether they're allowed to serve you related ads, save the information, or sell it - good luck finding out).
- How unique is your browser setup? Can you be uniquely identified by your browser alone? Find out with [Panopticlick](https://panopticlick.eff.org) from the EFF.
- From your IP address, your approximate location can be determined. See for example [IPLeak](http://ipleak.net).
- A few steps you can take:
    - Regularly delete all cookies/history
        - Note: this requires you to log in again on all websites, so use with care.
        - It might trigger "you're logging in from an unknown device" warnings, particularly if you're traveling or using a VPN
    - Browse in Private mode ("porn mode")
    - Use different browsers for different tasks (private/job/sensitive)
    - [Uninstall Flash](https://duckduckgo.com/?q=uninstall+flash). Fewer and fewer websites require this legacy technology riddled with security holes.
    - Install some of the tools in the next section
- If you ignore warnings about security certificates, MITM ("men in the middle") attackers could read all your traffic (incl. password)
- Always use HTTPS, if possible, as it encrypts your traffic. Some browser extensions do this for you automatically
- Some background:
    - ["Getting to know you"](http://www.economist.com/news/special-report/21615871-everything-people-do-online-avidly-followed-advertisers-and-third-party), The Economist, part of an insightful [Special Report: Advertising and Technology](http://www.economist.com/news/special-report/21615869-technology-radically-changing-advertising-business-profound-consequences).
    - ["Can't trust Uber"](http://www.nytimes.com/2014/12/08/opinion/we-cant-trust-uber.html?_r=0), in the NY Times
    - ["DEFCON 19: Tracking the Trackers: How Our Browsing History Is Leaking into the Cloud"](https://www.youtube.com/watch?v=BK_E3Bjpe0E), Youtube


### Suggested Tools: Secure Browsing - Search Engines
- Recommended Search Engines:
  - **DuckDuckGo**: Anonymous, unlogged web search. Can be set as default in many browsers, including Safari. [Link](https://duckduckgo.com)
  - **Ixquick**: Anonymous, unlogged web search, using non-Google sources. [Link](https://www.ixquick.com)
  - **StartPage**: Anonymous, unlogged web search, using Google as the source. [Link](https://startpage.com)
- Note: If you use DuckDuckGo, you can easily pull up other results:
    - append "!s" to be redirected to StartPage's results
    - append "!g" to be redirected to Google's results (which will track you)
    - append "!v" to be redirected to Youtube (video search)
    - and [more](http://imlefthanded.com/my-favourite-duckduckgo-bangs/), [many more](https://duckduckgo.com/bang.html)
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
- Also see [Browser Addons on Prism Break](http://prism-break.org/en/all/#web-browser-addons), and a [comparison](http://www.areweprivateyet.com), and [Better Web Browsing on riseup.net](https://help.riseup.net/en/security/network-security/better-web-browsing)

### Advanced Steps: Browsing with Tor

- For further anonymity, use [Tor (The Onion Router)](https://www.torproject.org), a stand-alone application available for most platforms, based on Firefox
- Tor routes all your traffic through a few extra hops, encrypted, so that the website you are visiting does not know who it's talking to, and interceptors near you don't know what websites you're visiting
- Note: the traffic from the final Tor node to your destination is not encrypted (unless you use HTTPS). The final Tor node might monitor it, and it might be run by a WFO (*well funded organization*).
    - It would not be sensible to divulge private information when using Tor
    - Don't log into any website (Facebook, etc.)
    - Don't use your real name, or google yourself
    - Don't open documents downloaded through Tor while online.
- The [Tor download page](https://www.torproject.org/download/download-easy.html.en) lists several security precautions; read them.
- Domain names ending in [*.onion*](https://en.wikipedia.org/wiki/.onion) are only accessible with a Tor browser. 
    - For example, the Tor site of DuckDuckGo is [3g2upl4pq6kufc4m.onion](3g2upl4pq6kufc4m.onion).
- Disadvantages:
    - Rather slow
    - final hop in the clear
    
### Suggested Tools: Secure Browsing - TOR

- Recommended Tools:
  - **OnionBrowser**: Anonymous browsing (TOR) for iOS. Open source [Link](https://mike.tig.as/onionbrowser/)
  - **OrBot**: Anonymous browsing (TOR) for Android. [Link](https://guardianproject.info/apps/orbot/)
  - **TorBrowser**: Anonymous browsing (TOR) for Linux, OS X, Windows. [Link](https://www.torproject.org)

- Also see [Web Browser on Prism Break](http://prism-break.org/en/all/#web-browsers)
- Also see [Tor on riseup.net](https://help.riseup.net/en/security/network-security/tor)

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

## <a name="steps-email"></a> Email

### Basic Steps: Secure Email

- Basic Idea: 
    - Encrypt your message including attachments into some blob (the *ciphertext*)
    - Send that blob via email
- Note: Meta data is NOT encrypted/protected and can be intercepted/manipulated
    - sender, recipient
    - subject line
    - length
    - time and frequency of mails

### Suggested Tools: Secure Email

- The standard for asymmetric encryption is PGP/GPG
- (PGP = "Pretty Good Privacy" is the original implementation, OpenPGP is the open internet standard, and GPG = "Gnu Privacy Guard" is an open source implementation. Bottom line: all the same)
- Purpose: PGP/GPG takes arbitrary text and encrypts it
- What: PGP/GPG is basically a command line tool, but various apps and utilities exist for computers and smartphones, including ones that tie into email programs directly.
- For key management, consider [keybase.io](https://keybase.io)
- Recommended:
  - **GPG4Win**: GPG for Windows. [Link](http://www.gpg4win.org/)
  - **GPGTools**: not free anymore. GPG on OS X Mail. EFF score 5/7. [Link](https://gpgtools.org)
  - **iPGMail**: not free. GPG for iOS Mail. Closed source. EFF score 4/7. [Link](https://ipgmail.com/)
- Not recommended at all for sensitive information: Normal email
- Also see [Email Encryption on Prism Break](https://prism-break.org/en/all/#email-encryption)
- Also see [Encrypted Email on arsTechnica](http://arstechnica.com/security/2013/06/encrypted-e-mail-how-much-annoyance-will-you-tolerate-to-keep-the-nsa-away/)

### PGP Best Practices

- When you write an encrypted email, chose a subject that doesn't reveal any information ("cat pictures")
- When generating keys, chose 4096 bits, RSA
- Secure your private key with a strong passphrase
- Set an expiry date in, say 2 years
    - this allows you to retire the key automatically when you lose the private key
    - you can always extend your key, or upload a new one
- Avoid sending very similar messages with only small changes, re-using greeting and signature, etc.
    - the Nazi's Enigma was broken faster because every message ended with "Heil Hitler"
- Beware of drafts stored in clear text on the mail server.
    - either enable "encrypt drafts", or go off-line while composing sensitive emails
- Note: anyone can upload keys to keyservers, so you cannot trust that any key you download actually belongs to the individual listed in the key. You should therefore verify with the individual owner the full key fingerprint of their key. You should do this verification in real life or over the phone.

- Also see [OpenGPG Best Practices on riseup.net](https://help.riseup.net/en/security/message-security/openpgp/best-practices)


## <a name="steps-chat"></a> Chat and Voice Calls

### First Steps: Secure Chat and Voice Calls

- Unfortunately, the most popular apps are spectacularly insecure
- Fortunately, there are some decent and free alternatives out there!
- Levels of security
    1. **No encryption:** Many apps don't encrypt content at all, or badly. Not recommended. Very dangerous, as your conversations could easily be intercepted or altered by:
        - the café whose Wifi you are using,
        - your internet service provider,
        - your government,
        - the company/provider.
    2. **Partial encryption:** Some apps encrypt the communication all the way to their server, and from there to the other device. Careful, only partial encryption!
        - This is fairly secure against random hackers, or the café whose Wifi you are usin.
        - However, nobody knows what happens on the server itself.
        - Your government could have a pipe to there, or
        - the company itself could spy on it, analyse it, sell it.
    3. **End-to-end encryption:** The most secure is end-to-end encryption, meaning only the two devices that are communicating know the keys, and NOBODY inbetween can decrypt what is happening. Recommended.
        - However, meta data (with whom do you chat how often how much) can still be seen with some of these.
- MITM (man in the middle attack)
    - One weakness of end-to-end encryption is the [man-in-the-middle attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack).
    - To circumvent that, the software shows you something representing the key used, such as a two-word phrase, or a square pixely picture. You should compare with the person that you're communicating with, on a second independent channel (*"out-of-band"*), to ensure that you're both talking to each other without anyone in the middle.


### Suggested Tools: Secure Chat (Text)

(Note: The EFF score refers to the [EFF ScoreCard](https://www.eff.org/secure-messaging-scorecard) for secure messaging.)

We recommend **iMessage** for Apple users, and **Signal** and **TextSecure** for smartphones (iOS and Android, respectively).

- Recommended
  - **iMessage**: End-to-end encrypted. Apple only. Closed source. EFF score 5/7 [Link](https://www.apple.com/ios/messages/)
  - **Signal**: End-to-end encrypted, compatible with TextSecure. iOS. Also supports voice calls. Open source. EFF score 7/7. [Link](https://whispersystems.org/blog/signal/)  
  - **Telegram**: End-to-end encrypted (“secret Chat” only!). Smartphones and computers. Open source. EFF score 5/7. [Link](https://telegram.org/)
  - **TextSecure**: End-to-end encrypted, compatible with Signal. Android. Open source. EFF score 7/7. [Link](https://whispersystems.org/)

- Recommended for advanced users that are happy with fiddly setups:
  - **Adium**: OTR chat for OS X, EFF score 6/7. A bit clunky. [Link](https://www.adium.im)
  - **ChatSecure**: OTR chat for iOS, Android. A bit clunky. EFF score 7/7. [Link](https://chatsecure.org/)
  - **Pidgin + OTR**: OTR chat for Windows, EFF score 7/7 [Link](https://otr.cypherpunks.ca)

- Careful, only partial encryption: AIM, Blackberry Messenger, Facebook Chat, IRC, Line, Telegram non-secret and groups, WhatsApp, Yahoo Messenger
- Not recommended at all: Firechat, Google Hangout, Google Talk Talk, ICQ, Kik, Kaoko, QQ, Snapchat, Viber, WeChat, Whisper
- Not recommended at all: SMS

- Also see the [EFF ScoreCard](https://www.eff.org/secure-messaging-scorecard)
- Also see [Prism Break on Instant Messaging](http://prism-break.org/en/all/#instant-messaging)

### Suggested Tools: Secure Voice calls

We recommend **FaceTime** for Apple users, and **Signal** and **Redphone** for smartphones (iOS and Android, respectively).

  - **Redphone**: Free, encrypted calls, compatible with Signal. Android. Open Source. EFF score 7/7 [Link](https://whispersystems.org/blog/signal/)
  - **Signal**: Free, encrypted calls, compatible with Redphone. iOS. Also supports text chat. Open Source. EFF score 7/7 [Link](https://whispersystems.org/blog/signal/)

- Careful, only partial encryption: Google Hangout (Voice/Video)
- Not recommended: Normal phone calls, Skype

- Also see [Prism Break on Video/Voice](http://prism-break.org/en/all/#video-voice)

### Suggested Tools: Whistleblowing

- Use [SecureDrop](https://en.wikipedia.org/wiki/SecureDrop) for confidential communication between journalist and sources.
    - You can use it to contact news organizations that have stablished a secure drop instance using a pseudonym, and subsequently communicate with them.
    - Your organization can set up an instance of the software on a server to allow anyone to contact you pseudonymously.
    - **SecureDrop**: Online platform for secure communication between journalists and sources (whistleblowers). [Link](https://freedom.press/securedrop)
- Example: [Contact *The Guardian*](https://securedrop.theguardian.com) at 33y6fjyhs3phzfjj.onion


## Miscellanous

### Information Leaks

- Your phone is a tracking device, effectively
    - If your mobile phone is connected, your cell phone provider knows where it is (even if it's not a smart phone)
    - If your mobile phone is a smart phone, your phone knows where it is (and can record/share it)
    - If you're meeting an important source, consider leaving your phone at home
- If you give someone information, you might reveal more than you thought:
    - Your phone number, email can be googled: what to they reveal?
    - Reverse Image Search sites such as [TinEye](http://tineye.com) or [Google](http://www.google.com/insidesearch/features/images/searchbyimage.html) allow someone to see whether a picture appears elsewhere on the net, eg Facebook, LinkedIn, Twitter, or your employer's website
    - A picture contains embedded information ("[EXIF data](https://en.wikipedia.org/wiki/Exchangeable_image_file_format)") that frequently contains the time and location the picture was taken
        - There are tools availble to remove that information, known as EXIF strippers or metadata scrubbers.
        - Recommended (but maybe a bit complicated): ExifTool. Windows, OS X, UNIX. [Link](http://www.sno.phy.queensu.ca/~phil/exiftool/index.html)
    - The IP address of your computer can lead to your ISP, and then to you.


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
    
### Advanced Steps

- If you have highly sensitive information, you'll need to be more careful and systematic. Research:
    - OpSec
    - VMs (Virtual Machines)
    - **Tails**: The amnesic incognito live system. Operating System on a USB stick. [Link](https://tails.boum.org)

