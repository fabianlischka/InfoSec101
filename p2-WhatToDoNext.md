---
layout: page
title: What to do next
---

Here you'll find some concrete steps (some simple, some a bit more involved) to take to protect yourself and your information. At the end, there are links to [more guides and resources](#further-links).

### What to do
- [for Macs (OS X)](#wtd-mac)
- [for Windows](#wtd-win)
- [for iPhones (iOS)](#wtd-ios)
- [for Android](#wtd-android)

## Suggested Tools: Selection & Criteria

We recommend only a small subset of all available tools - the ones we consider "the best" for most users with

- average (or maybe slightly lower) technical IT background.
- average (or slightly higher) need for privacy and security of information.
  - Note that life-and-death situations require stronger solutions (and much more paranoia) than we can cover here!

### How to evaluate which cryptographic tools to use?

- Fact: Cryptography is hard!
    - Weakest Link property:
        - Adversary only needs to break the weakest link in the chain
        - If you're careful 20 times, but careless once, you might already be screwed
    - Adversary is not playing fair:
        - Key Loggers
        - Timing attacks, Side channel attacks, Chosen Plaintext attacks, etc.
        - Rubber hose, Wrench (see xkcd comic below)
- Thus: Desireable Attributes of a tool:
    - Organizational properties
        - Open Source
        - Security Audit
        - Clear threat model, clear crypto solutions
    - Crypthographic properties
        - Established crypto algorithms
        - End-to-end encryption
        - Perfect forward secrecy
    - Price
        - We give preference to free/open source tools,
        - But we will list commercial solutions if they provide clear benefits (such as ease of use, better support, etc.)
        - However, very expensive tools will be penalized.

In summary, our list below includes tools that are not too hard to use, preferably open source, with good enough crypto, preferably cheap or free.


### xkcd on: Security and the Weakest Link

![xkcd: Security](http://imgs.xkcd.com/comics/security.png)

from: "xkcd" by Randall Munroe at [xkcd.com](https://xkcd.com/538/)

---

## <a name="wtd-mac"></a> What to do: Mac

### What to do: Mac - today

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

### What to do: Mac - If you have a Weekend

- Enable FileVault (Disk Encryption). It requires a system restart, then works in the background to encrypt your disk. (System Preferences -> Security & Privacy -> FileVault)
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

## <a name="wtd-win"></a> What to do: Windows

### What to do: Windows - Today

- In your browser:
    - Switch your Search Engine to DuckDuckGo
    - Install Addons
        - Always HTTPS, if available
        - Privacy Badger
- Download and install
    - **Telegram**: Chat. End-to-end encrypted (“secret Chat” only!). All Platforms. Closed source. EFF score 5/7. [Link](https://telegram.org/)
    - **TorBrowser**: Anonymous browsing (TOR) for the desktop. [Link](https://www.torproject.org)
    - **Wickr**: Chat. End-to-end encrypted. All platforms. EFF score 4/7. [Link](https://wickr.com)


### What to do: Windows - If you have a Weekend

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

## <a name="wtd-ios"></a> What to do: iOS

### What to do: iOS - Today
- Switch your search engine to DuckDuckGo (Settings -> Safari -> Search Engine)
- Use iMessage and Facetime, both end-to-end encrypted
- Download (from the App Store)
    - Browsing apps: OnionBrowser (anonymous/private browsing)
    - Chat apps: Signal, Telegram
    - Voice call apps: Signal


### What to do: iOS - If you have a Weekend

- Get started with a Password Manager
    - If you're only on Safari (Mac and iOS), Keychain is great
    - If you're happy to pay for a commercial solution, look at LastPass or 1Password
    - If you prefer a free open-source solution, get pwSafe
- Get started with GPG:
    - download & install
    - **iPGMail**: not free. GPG for iOS Mail. Closed source. EFF score 4/7. [Link](https://ipgmail.com/)
    - copy your private key from your desktop computer over to your iPhone, [see this guide.](https://ipgmail.com/guide/)
    - send yourself a message from the desktop and decrypt it on the iPhone, and vv


## <a name="wtd-android"></a> What to do: Android

### What to do: Android - Today

??? TBD

#### What to do: Android - If you have a Weekend

??? TBD

## <a name="further-links"></a> Further Resources

### Guides

* [Computer Security for Journalists](https://docs.google.com/file/d/0B2HGtAJEbG8PdzVPdHcwekI2V2M/edit?pli=1). A presentation by Jennifer Valentino-DeVries (WSJ) on information security for journalists
* [Digital Security for Journalists](http://www.slideshare.net/eschnou/digital-security-forjournalists). A presentation by Laurent Eschenbauer on information security for journalists
* [Doxxing Defense](http://www.computerworld.com/article/2849263/doxxing-defense-remove-your-personal-info-from-data-brokers.html#tk.cwfb). A guide on how to remove your personal information from data brokers
* [Email Self Defense](https://emailselfdefense.fsf.org/en/). A guide to setting up encrypted email on the desktop, unfortunately somewhat confusing and out-of-date.
* [Encryption Works](https://freedom.press//encryption-works). A guide for journalists on “How to Protect Your Privacy in the Age of NSA Surveillance”. Somewhat out-of-date.
* [Journalist Security Guide](https://cpj.org/reports/2012/04/information-security.php). A guide on information security, part of a guide for (general) security for journalists by the *Committee to Protect Journalists*
* [Planning Digital Security for your Story](http://www.scribd.com/doc/209968137/Threat-Modeling-Planning-Digital-Security-for-your-Story). A presentation by Jonathan Stray on information security for journalists
* [Privacy 101](https://www.privacyinternational.org/resources/privacy-101).

### Commented lists of tools

* [EFF Secure Messaging Scorecard](https://www.eff.org/secure-messaging-scorecard). A useful list and brief evaluation of chat apps, for all platforms.
* [Guardian Project](https://guardianproject.info/howto/). Tutorials and tools for a few privacy tools.
* [Prism Break](http://prism-break.org/en/all/). A very comprehensive overview about a lot of apps and software, with some good comments, for all platforms. Note: Only Free/Open Source tools are considered, not commercial ones.
* [Surveillance Self Defense](https://ssd.eff.org/en/index). A useful guide and list of tutorials about many aspects of information security