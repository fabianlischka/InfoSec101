---
---

# Information Security for (Non-IT) Professionals



## What are the issues: Goals of Security

- **Privacy**
  - **Confidentiality:** Nobody can read the message, except recipient. (*Encryption, Secure Channel*)
  - **Anonymity:** Nobody can figure out your name or location
- **Security**
  - **Integrity:** Nobody has messed with your message. (*Signature*)
  - **Authentication:** The recipient is who you think they are. (*No MitM attack*)

#### PHD comics on: Security in your neighbourhood coffee shop

![PHD comics: Coffee Security](http://www.phdcomics.com/comics/archive/phd080913s.gif)

from: "Piled Higher and Deeper" by Jorge Cham at [www.phdcomics.com](http://www.phdcomics.com/comics.php?f=1618)

---


## What to do?

### What to do: Steps & Suggested Tools

#### Suggested Tools: Criteria

How to evaluate which cryptographic tools to use?

- Cryptography is hard!
    - Weakest Link property
    - Adversary is not playing fair (CPA, Side Channels)
- Desireable Attributes of a tool:
    - Organizational properties
        - Open Source
        - Security Audit
        - Clear threat model, clear crypto solutions
    - Crypthographic properties
        - Established crypto algorithms
        - End-to-end encryption
        - Perfect forward secrecy

---        
#### xkcd on: Security and the Weakest Link

![xkcd: Security](http://imgs.xkcd.com/comics/security.png)

from: "xkcd" by Randall Munroe at [xkcd.com](https://xkcd.com/538/)

---
        
#### First Steps: Passwords

- use strong passwords
    - Good technique: Use the 1st letter of a passphrase: 
        - "Fab hěn xǐhuān HK, IT security, and (sometimes) 9 hours sleep" turns into `fhxHK,ITs&(st)9hs`
        - Use a creative, strange, unique, multi-language passphrase.
    - Don't use [weak passwords](https://en.wikipedia.org/wiki/Password_strength#Examples_of_weak_passwords)
    - Test your passwords:
        - Note: do NOT type any of your passwords into a random web page. 
        - Load the page in a fresh browser, disconnect wifi, test your passwords, then close the browser
        - [Password Tester](https://www.bennish.net/password-strength-checker/) based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with some links for background info. Click "Break it down!" to see the components.
        - [Password Tester](https://www.cygnius.net/snippets/passtest.html), also based on [zxcvbn](https://tech.dropbox.com/2012/04/zxcvbn-realistic-password-strength-estimation/), with a few examples.
    - Set your computer up so that the screen saver kicks in after 3 minutes. You'll have to type your password many times a day, and you'll get really fast, and won't ever forget it
- Security questions: avoid, or give bogus unguessable answers like `T$adf^VFBG(*&O(N%R^BHN*UOI` (Note: of course, this can complicate things when you DO forget your password.)
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
- `fhxHK,ITs&(st)9hs` billions of centuries (over 100 bits). 

A password based on a long, creative passphrase might really be the state of the art.


---


#### Suggested Tools: Password Managers

- Password Managers allow you to use different (secure) passwords for different sites
- Password Managers store these passwords securely
    - Storage locally (better security, less convenience)
    - Storage in the Cloud (easier sync, automatic backup, less secure)
- Password Managers require one Master Password 
    - it better be good!
    - you better don't forget it! (use regularly, maybe deposit one backukp on paper in your mom's bank safety deposit box)
- Available on desktop and smart phones
- Recommended:
  - **iCloud KeyChain**: Password manager. Safari only (OS X & iOS), cloud. Commercial. Closed. Safe and easy if you use only Safari. [Link](http://support.apple.com/en-us/HT5813)
  - **Password Safe**: Password manager, most platforms, local. Bruce Schneier.  [Link](http://pwsafe.org)
  - **1Password**: Password manager, most platforms, local. Commercial. Closed. [Link](https://agilebits.com/onepassword)
  - **LastPass**: Password manager, most platforms, cloud. Commercial. Closed. [Link](https://lastpass.com)
- Also see [Password managers on Prism Break](http://prism-break.org/en/all/#password-managers)

#### First Steps: Disk Encryption

- protects the content of your laptop 
    - when it's stolen
    - when it's in the hand of government/border control
- without Disk Encryption, can just take out the harddrive from your laptop (or start it up in "Target Mode") and copy everything from it
- when turned on initially, will run a few hours in the background to encrypt everything

#### Suggested Tools: Disk Encryption

- Automatically enabled in iOS 8, and Android L. Can be set up for earlier Android versions (from HoneyComb onwards?)
- Recommended:
  - **FileVault**: Disk Encryption, OS X. Set up in System Preferences -> Security & Privacy. [Link](http://support.apple.com/en-us/HT4790)
  - Windows: ??
- Careful:
  - **TrueCrypt** appears to have some issues, the developers don't recommend its use anymore
- Also see [Disk Encryption on Prism Break](http://prism-break.org/en/all/#disk-encryption)

#### First Steps: Browsing

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
- If you ignore warnings about security certificates, MITM ("men in the middle") attackers can read all your traffic (incl. password)
- Always use HTTPS, if possible, as it encrypts your traffic. Some browser extensions do this for you automatically
- Some background:
    - ["Getting to know you"](http://www.economist.com/news/special-report/21615871-everything-people-do-online-avidly-followed-advertisers-and-third-party), The Economist, part of an insightful [Special Report: Advertising and Technology](http://www.economist.com/news/special-report/21615869-technology-radically-changing-advertising-business-profound-consequences).
    - ["Can't trust Uber"](http://www.nytimes.com/2014/12/08/opinion/we-cant-trust-uber.html?_r=0), in the NY Times
    - ["DEFCON 19: Tracking the Trackers: How Our Browsing History Is Leaking into the Cloud"](https://www.youtube.com/watch?v=BK_E3Bjpe0E), Youtube
    
    
#### Suggested Tools: Secure Browsing - Search Engines
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

#### Suggested Tools: Secure Browsing - Browser Addons

- Recommended Tools:
  - **Adblock**: Blocks ads when browsing. Chrome, Firefox, Opera, Safari. “Pay what you want”. [Link](https://getadblock.com)
  - **Adblock Edge**: Blocks ads when browsing. Firefox. [Link](https://addons.mozilla.org/en-US/firefox/addon/adblock-edge/)
  - **AlwaysHTTPS**: Encrypts your browsing with many websites. Firefox, Chrome, Opera [Link](https://www.eff.org/https-everywhere)
  - **Ghostery**: Stops trackers when browsing. Uploads anonymized tracker data by default. Firefox, Chrome, Opera, Safari [Link](https://www.ghostery.com/en/)
  - **Privacy Badger**: Stops advertisers and trackers when browsing. Firefox, Chrome. From the EFF. [Link](https://www.eff.org/privacybadger)
    
- Alternatives:
  - **Adblock Plus**: Blocks ads when browsing. Android, Chrome, Firefox, IE, Opera, Safari. Lets “acceptable ads” through by default. [Link](https://adblockplus.org)
  - **Disconnect**: Stops trackers when browsing. USD 50/a. Open Source. OS X, Win, Android, iOS [Link](https://disconnect.me)

- Note: On Android, some of these apps are banned from the Play Store, because they  interfere with Google's business model. [Source: Disconnect Blog](https://blog.disconnect.me/blog/google-just-banned-our-new-android-app-before-it-even-launched-another-example-of-why-privacy-friendly-alternatives-for-android-app-distribution-are-critically-important)
- Also see [Browser Addons on Prism Break](http://prism-break.org/en/all/#web-browser-addons), and a [comparison](http://www.areweprivateyet.com)

#### Advanced Steps: Browsing

- For further anonymity, use [TOR (The Onion Router)](https://www.torproject.org), a stand-alone application available for most platforms
- TOR routes all your traffic through a few extra hops, encrypted, so that the website you are visiting does not know who it's talking to, and interceptors near you don't know what websites you're visiting
- It would not be sensible to divulge private information (such as your real name or facebook logins or so) when using TOR
- The [TOR download page](https://www.torproject.org/download/download-easy.html.en) lists several security precautions; read them.


#### Suggested Tools: Secure Browsing - TOR

- Recommended Tools:
  - **OnionBrowser**: Anonymous browsing (TOR) for iOS. Open source [Link](https://mike.tig.as/onionbrowser/)
  - **OrBot**: Anonymous browsing (TOR) for Android. [Link](https://guardianproject.info/apps/orbot/)
  - **TorBrowser**: Anonymous browsing (TOR) for Linux, OS X, Windows. [Link](https://www.torproject.org)
  
- Also see [Web Browser on Prism Break](http://prism-break.org/en/all/#web-browsers)

#### First Steps: Multiple Accounts

- consider having multiple separated accounts on your machine, for 
    - work
    - fun
    - private
    - sensitive projects etc.
- use shared folders to move information between them in a controlled matter
- a bit of inconvenience because you have to re-enter passwords etc., but it makes leaks of information much harder

#### First Steps: VPNs

- "Virtual Private Network"
- secures the connection ...
    - from your device all the way...
    - to a specific exit node "somewhere" (you can choose)
- from the exit node, the traffic goes (normally) to its destination
- protects from interception "nearby" (Internet Cafe, your ISP, local gov't)
- allows to circumvent censorship, eg when traveling in China, Iran
    - have to enable SSL for that (or SSH tunnel, possibly)

#### Suggested Tools: VPNs

- many providers
    - there is no free lunch: expect to pay for good service (about USD 5/month)
    - **AirVPN**: VPN provider with strong committment to security, privacy. [Link](https://airvpn.org)
- to test whether the VPN works correctly, visit [IPLeak](http://ipleak.net), for example, and see what it thinks your IP address and location are.

#### First Steps: Secure Chat and Voice Calls

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
    - The most secure is end-to-end encryption, meaning only the two devices that are communicating know the keys, and NOBODY inbetwen can decrypt what is happening. Recommended.
        - However, meta data (with whom do you chat how often how much) can still be seen with some of these.
- MITM (man in the middle attack)
    - One weakness of end-to-end encryption is the [man-in-the-middle attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack). 
    - To circumvent that, the software shows you something representing the key used, such as a two-word phrase, or a square pixely picture. You should compare with the person that you're communicating with, on a second independent channel, to ensure that you're both talking to each other without anyone in the middle.


#### Suggested Tools: Secure Chat (Text)

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
- Not recommended at all: Firechat, Google Hangout, Google Talk Talk, ICQ, Kik, Kaoko, QQ, Snapchat,  Viber, WeChat, Whisper
- Not recommended at all: SMS

- Also see the [EFF ScoreCard](https://www.eff.org/secure-messaging-scorecard)
- Also see [Prism Break on Instant Messaging](http://prism-break.org/en/all/#instant-messaging)

#### Suggested Tools: Secure Voice calls

  - **Signal/Redphone**: Free, encrypted calls. EFF score 7/7 [Link](https://whispersystems.org/blog/signal/)

- Careful, only partial encryption: Skype, Google Hangout (Voice/Video)
- Not recommended: Normal phone calls

- Also see [Prism Break on Video/Voice](http://prism-break.org/en/all/#video-voice)

#### Suggested Tools: Cloud Storage

- Careful, only partial encryption: Dropbox, Google Drive, iCloud
- Not recommended at all: 360 Cloud Disk, Baidu Cloud Disk, QQ Net Disk

#### Advanced Steps: Secure Email

- GPG allows secure sending of email including attachments
- However, meta data is NOT encrypted/protected
    - sender, recipient
    - subject line
    - length

#### Interlude: Asymmetric encryption

- Asymmetric encryption is *awesome*
- Here is the idea:
    - Plain Text + key + algo = Ciphertext (=gibberish)
    - send the Ciphertext across (even a non-secured line)
    - Ciphertext + key + algo = Plain Text
- Now, here the magic: the keys for encryption and decryption need *not* be the same. So, you create a private key and a public key. The public key can be published everywhere.
- If someone has the public key, they *cannot* reconstruct the private key.
- So: 
    - Plain Text + Bob's public key + algo = Ciphertext (=gibberish)
    - send the Ciphertext across (even a non-secured line)
    - Ciphertext + Bob's private key + algo = Plain Text
- Anything that's been encrypted by Bob's public key could be plastered all over the wall: Only Bob (or, more precisely, whoever holds Bob's *private key*) can decrypt and read it
- Key management can be a bit tricky: you want to make sure, when you send a message to Bob, that it's really him that holds the private key, not some impersonator. Best to check with him by comparing "finger prints"!


#### Suggested Tools: Secure Email

- The standard for asymmetric encryption is PGP/GPG
- (PGP = "Pretty Good Privacy" is the original implementation, OpenPGP is the open internet standard, and GPG = "Gnu Privacy Guard" is an open source implementation. Bottom line: all the same)
- For key management, consider [keybase.io](https://keybase.io)
- Recommended:
  - **GPG4Win**: GPG for Windows. [Link](http://www.gpg4win.org/)
  - **GPGTools**: not free. GPG on OS X Mail. EFF score 5/7. [Link](https://gpgtools.org)
  - **iPGMail**: not free. GPG for iOS Mail. Closed source. EFF score 4/7. [Link](https://ipgmail.com/)
- Note recommended at all for sensitive information: Normal email


## What to do next

### What to do: Mac

#### What to do: Mac - today

- Use Messages and Facetime (end-to-end encrypted)
- In Safari,
    - Switch your Search Engine to DuckDuckGo (Safari -> Preferences -> Search)
    - Install Extensions (Safari -> Safari Extensions):
        - Adblock Plus (choose all options: block malware, trackers. By default, "acceptable ads" are displayed, can be disabled)
        - maybe Ghostery (or Disconnect Private Browsing)
        - maybe CryptoCat (for anonymous chats)
- In Firefox, Chrome,
    - Switch your Search Engine to DuckDuckGo
    - Install Addons
        - Adblock Edge
        - Always HTTPS
        - Privacy Badger
- Download and install
    - **Telegram**: Chat. End-to-end encrypted (“secret Chat” only!). All Platforms. Closed source. EFF score 5/7. [Link](https://telegram.org/)
    - **TorBrowser**: Anonymous browsing (TOR) for the desktop. [Link](https://www.torproject.org)
    - **Wickr**: Chat. End-to-end encrypted. All platforms. EFF score 4/7. [Link](https://wickr.com)

#### What to do: Mac - If you have a Weekend

- Enable FileVault, best overnight (System Preferences -> Security & Privacy -> FileVault)
- (in Safari -> Preferences -> Privacy, occasionally remove all website data. Note that you'll have to log in fresh to all websites, so only do this if you know all your passwords, or have a password manager)
- Get started with a Password Manager
    - If you're only on Safari (Mac and iOS), Keychain is great
    - If you're happy to pay for a commercial solution, look at LastPass or 1Password
    - If you prefer a free open-source solution, get KeePass or PasswordSafe
- Get started with GPG:
    - download & install   
    - **GPGTools**: not free. GPG on OS X Mail. EFF score 5/7. [Link](https://gpgtools.org)
    - generate your first key, upload the public part to keyservers
    - consider joining [keybase.io](https://keybase.io)
    - download other people's public keys, and send them your first encrypted message

### What to do: Windows
#### What to do: Windows - Today

- In your browser:
    - Switch your Search Engine to DuckDuckGo
    - Install Addons
        - Always HTTPS, if available
        - Privacy Badger
- Download and install
    - **Telegram**: Chat. End-to-end encrypted (“secret Chat” only!). All Platforms. Closed source. EFF score 5/7. [Link](https://telegram.org/)
    - **TorBrowser**: Anonymous browsing (TOR) for the desktop. [Link](https://www.torproject.org)
    - **Wickr**: Chat. End-to-end encrypted. All platforms. EFF score 4/7. [Link](https://wickr.com)


#### What to do: Windows - If you have a Weekend

- Get started with a Password Manager
    - If you're happy to pay for a commercial solution, look at LastPass or 1Password
    - If you prefer a free open-source solution, get KeePass or PasswordSafe
- Get started with GPG:
    - download & install   
    - **GPG4Win**: GPG for Windows. [Link](http://www.gpg4win.org/)    
    - generate your first key, upload the public part to keyservers
    - consider joining [keybase.io](https://keybase.io)
    - download other people's public keys, and send them your first encrypted message
- Consider 
    - **Pidgin + OTR**: OTR chat for Windows, EFF score 7/7. [Link](https://otr.cypherpunks.ca)

### What to do: iOS

#### What to do: iOS - Today
- Switch your search engine to DuckDuckGo (Settings -> Safari -> Search Engine)
- Use iMessage and Facetime, both end-to-end encrypted
- Download (from the App Store)
    - Browsing apps: OnionBrowser (anonymous/private browsing), Ghostery (somewhat private browser)
    - Chat apps: Telegram, Wickr, (not free:) Threema
    - Voice call apps: Signal
  
  
#### What to do: iOS - If you have a Weekend

- Get started with a Password Manager
    - If you're only on Safari (Mac and iOS), Keychain is great
    - If you're happy to pay for a commercial solution, look at LastPass or 1Password
    - If you prefer a free open-source solution, get KeePass or PasswordSafe
- Get started with GPG:
    - download & install   
    - **iPGMail**: not free. GPG for iOS Mail. Closed source. EFF score 4/7. [Link](https://ipgmail.com/)
    - copy your private key from your desktop computer over to your iPhone, [see this guide.](https://ipgmail.com/guide/)
    - send yourself a message from the desktop and decrypt it on the iPhone, and vv
- maybe install CryptoCat, maybe ChatSecure (OTR messaging) for more chat options


### What to do: Android
#### What to do: Android - Today

???

#### What to do: Android - If you have a Weekend

???

## Further Resources

### Guides

* [Computer Security for Journalists](https://docs.google.com/file/d/0B2HGtAJEbG8PdzVPdHcwekI2V2M/edit?pli=1). A presentation by Jennifer Valentino-DeVries (WSJ) on information security for journalists
* [Digital Security for Journalists](http://www.slideshare.net/eschnou/digital-security-forjournalists). A presentation by Laurent Eschenbauer on information security for journalists
* [Doxxing Defense](http://www.computerworld.com/article/2849263/doxxing-defense-remove-your-personal-info-from-data-brokers.html#tk.cwfb). A guide on how to remove your personal information from data brokers
* [Email Self Defense](https://emailselfdefense.fsf.org/en/). A guide to setting up encrypted email on the desktop, unfortunately somewhat confusing and out-of-date.
* [Encryption Works](https://freedom.press//encryption-works). A guide for journalists on “How to Protect Your Privacy in the Age of NSA Surveillance”. Somewhat out-of-date.
* [Journalist Security Guide](https://cpj.org/reports/2012/04/information-security.php). A guide on information security, part of a guide for (general) security for journalists by the *Committee to Protect Journalists*
* [Planning Digital Security for your Story](http://www.scribd.com/doc/209968137/Threat-Modeling-Planning-Digital-Security-for-your-Story). A presentation by Jonathan Stray on information security for journalists
* [Privacy 101](https://www.privacyinternational.org/resources/privacy-101). 

### Organisations

* [Committee to Protect Journalists](https://cpj.org). 
* [Electronic Frontier Foundation](https://www.eff.org). An organisation dedicated to *Defending your Rights in a Digital World*
* [HK Civil Liberties Union](http://hkclu.org/). A group of volunteers from the legal profession in Hong Kong to defend and safeguard the civil rights and liberties of every individual in Hong Kong.
* [Privacy International](https://www.privacyinternational.org). An organisation dedicated to the privacy and security of individuals

### Commented list of tools

* [EFF Secure Messaging Scorecard](https://www.eff.org/secure-messaging-scorecard). A useful list and brief evaluation of chat apps, for all platforms.
* [Guardian Project](https://guardianproject.info/howto/). Tutorials and tools for a few privacy tools.
* [Prism Break](http://prism-break.org/en/all/). A very comprehensive overview about a lot of apps and software, with some good comments, for all platforms. Note: Only Free/Open Source tools are considered, not commercial ones.
* [Surveillance Self Defense](https://ssd.eff.org/en/index). A useful guide and list of tutorials about many aspects of information security