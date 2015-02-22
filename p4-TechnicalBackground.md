---
layout: page
title: Technical Background
---


## What are the issues: Goals of Security

- **Privacy**
  - **Confidentiality:** Nobody can read the message, except recipient. (*Encryption, Secure Channel*)
  - **Anonymity:** Nobody can figure out your name or location
- **Security**
  - **Integrity:** Nobody has messed with your message. (*Signature*)
  - **Authentication:** The recipient is who you think they are. (*No MitM attack*)

## Threat Modeling
- What do I want to keep private?
    - Messages, locations, identities, networks, etc.
- Who wants to know? Who is the adversary?
    - Story subject, governments, law enforcement, corporations, etc.
- What can the adversary do?
    - Technical
        - Hacking, intercept communications, install malware, intall keylogger
    - Legal
        - Lawsuits, subpoenas, detention
    - Social
        - Phishing, “social engineering,” exploiting trust
    - Operational
        - The one time you didn’t use a secure channel
        - The one person you shouldn’t have told
    - Physical
        - Theft, rubber hose, wrench
- What happens if adversary succeeds?
    - Story's blown, legal problems for a source, someone gets killed

## How the Internet works (briefly)

- Computers on the internet are identified by their IP address (37.48.81.50)
- Your computer knows the IP address of the DNS (domain name service) server. Given a domain name (such as www.google.com), your computer will ask the DNS server for the corresponding IP address.
- All traffic gets chopped into little packets with the destination address, which are then sent from your laptop
    - via the Wifi access point (home, cafe, ...)
    - via your ISP
    - via your country's network
    - possibly around the world
    - to another network, ISP, server, ...
    - etc.
- Basically, by default, in clear text: everyone on the way could read along


## Metadata

- Metadata is the data that's not inside a message or decument (the content, or plaintext of the message), but associated with it, or "on the envelope".
- Types of metadata:
    - for mail, text messages, chat etc:
        - sender and recipient of a message
        - length of a message
        - subject of the message (when using PGP!)
        - time the message was sent
        - number of messages
    - for browsing:
        - website address
        - frequency and time of access
    - for documents (Microsoft Office, PDF, etc):
        - author
        - file location
        - title, subject
        - keywords
        - creation, modification dates
        - company name
        - comments
    - for images
        - time
        - camera type
        - exposure information
        - exact location (!)
- Consider:
    - in a potential conflict zone, a sudden increase of (encrypted) radio messages
    - somebody receiving several letters from a sexual health clinic
    - a list of everyone who frequently exchanges emails with Ai Weiwei
    - an "anonymous" review of scientific paper containing the author's real name in the Microsoft Word file properties
    - a journalist interviewed programmer John McAfee while he was fleeing from alleged persecution in Belize. He posted a photo of McAfee, which included GPS coordinates, leading to McAfee's capture in Guatemala two days later.



## Symmetric encryption

- Alice wants to send a message (the *plaintext*) to Bob.
- Alice uses an algorithm and a key to encypt the message, obtaining the *ciphertext* (=gibberish).
- Bob receives the *ciphertext*, and uses the key to decrypt it.
- So:
    - Plain Text + key + algo = ciphertext
    - send the ciphertext across (even a non-secured line)
    - Ciphertext + key + algo = Plain Text
- If evil Eve is listening in, and gets the cyphertext, she cannot read it, because she doesn't have the key.
- Postal analogy:
    - Alice puts the message in a box, and locks it with a padlock. She sends it over to Bob. Bob has the same key, and uses it to open the padlock and read the message. They must have gone shopping together to buy the padlock and taken a key each.
- Problems:
    - Alice and Bob must have the same key. They must have met once before, and agreed on a key.


## Asymmetric encryption

- Asymmetric encryption is *awesome*
- Same idea: Alice wants to send bob a message, she uses a key to encrypt it, sends over the ciphertext, and bob uses a key to decrypt it.
- Now, here the magic: the keys for encryption and decryption need *not* be the same. So, you create a private key and a public key. The public key can be published everywhere.
- If someone has the public key, they *cannot* reconstruct the private key.
- So:
    - Plain Text + Bob's public key + algo = ciphertext (=gibberish)
    - send the ciphertext across (even a non-secured line)
    - ciphertext + Bob's private key + algo = Plain Text
- If evil Eve is listening in, and gets the cyphertext, she cannot read it, because she doesn't have the key (Bob's private key).
- Anything that's been encrypted by Bob's public key could be made totally public: Only Bob (or, more precisely, whoever holds Bob's *private key*) can decrypt and read it
- Postal analogy:
    - Alice asks Bob to send over a padlock, and Bob sends over a padlock.
    - Alice puts the message in a box and locks it with Bob's padlock, and sends the box over to Bob.
    - Bob uses his key to open his padlock and read the message.
- Problems:
    - Key management can be a bit tricky. You want to make sure, when you send a message to Bob, that it's really him that holds the private key, not some impersonator. Best to check with him by comparing "finger prints"!
    - See MITM attack below

## MITM Attack

- Postal analogy:
    - Alice asks Bob to send over a padlock, and Bob sends over a padlock.
    - Eve intercepts Bob's padlock, and sends her own padlock.
    - Alice puts the message in a box and locks it with what she thinks is Bob's padlock (but is Eve's), and sends the box over to Bob.
    - Eve intercepts the message again, unlocks her padlock, makes a copy of the message and/or changes it, then puts it in a box and locks it with Bob's padlock, and sends it to Bob.
    - Bob uses his key to open his padlock and read the (intercepted/manipulated) message.
- How to prevent that?
    - Alice can talk to Bob, and check that the padlock is his.



## Some basic privacy technologies

### PGP (1991), GPG (1999)
[Pretty Good Privacy](http://www.symantec.com/products-solutions/families/?fid=encryption), [Gnu Privacy Guard](https://gnupg.org/)

The gold standard in encryption. PGP is a proprietary program owned by Symantec since 2010, while GPG is the open-source version. Both implement the open standard OpenPGP for asymmetric encryption. It is by far the most versatile and well audited algorithm used to sign and encrypt any kind of data. Its creator Phil Zimmerman was under investigation for many years in the United States for “exporting ammunition without a license” for offering his cryptosystems. He challenged these investigations by releasing the source code freely in a printed book that anybody could buy and scan, actions protected by the First Amendment. Some people even had the basic algorithm tattooed on their bodies, thus making it technically illegal for them to “export” themselves from the country. GPG is a library and command line utility, but several applications for Linux, OS X and Windows and smartphones are available, as well as plug-ins for Outlook, Thunderbird, and OS X Mail, that make email encryption relatively easy. The GPG project was significantly funded by the German Government, but has been soliciting donations to employ two full-time developers.


### OTR
[Off-the-Record Messaging](https://otr.cypherpunks.ca/)

A protocol that allows to exchange encrypted information (like PGP), but provides for deniable authentication. This means that it if intercepted, it is later impossible to prove who was communicating with whom while it is still possible for users to authenticate each other. In addition, if a key ever were to be compromised this would not allow to decrypt previous message exchanges (a property known as “perfect forward secrecy”). It is most commonly used in chat applications and can even be used on top of other chat protocols. It is not to be confused with Google Talk's 'Off the Record' feature.


### TLS (1999)
[Transport Layer Security](https://www.ietf.org/)

An open standard developed by the Internet Engineering Task Force (IETF), a group of volunteers loosely associated with the Internet Society. It ensures that data transmitted between your browser and a server is encrypted and the server's identity is authenticated. Successful encryption is usually indicated with a green address bar or a lock and the 's' in https. Attacks against this protocol are frequently observed in China, the address bar then turns red and the browser will issue a warning that is not to be ignored.

### Tor (1990s)
[The Onion Router](https://www.torproject.org/)

A protocol and open-source software that allows data to be transmitted around the internet in a way that not only encrypts it, but also hides its destination and origin, by routing it through several layers (thus the name). Originally developed in secrecy by the US Navy to allow spies and sources to securely route information back to the United States, it was released to the public in 2004. The Electronic Frontier Foundation (EFF) has since led its development, and the Tor browser bundle is now available for all major platforms, allowing anonymous browsing. Inside the Tor network it is possible to host sites which are incredibly difficult to locate or censor, the so called “Tor hidden services". Among them are both drug markets and platforms for whistleblowers.

### Bitcoin (2008)
[Bitcoin](https://bitcoin.org/)

Proposed by the pseudonymous programmer Satoshi Nakamoto and released to the public in 2009. Its development is open to anybody, but currently dominated by the Bitcoin Foundation. The Bitcoin technology is essentially a large distributed blockchain that users can alter according to strict rules laid out in the protocol based on majority rule, thus allowing to indelibly and unanimously record transactions. Bitcoin is currently most known for the use as a digital and distributed currency that is outside the control of central banks or governments, but has also been used to record contracts, such as a marriage.

