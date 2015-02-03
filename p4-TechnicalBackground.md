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

## How the Internet works (roughly)

- Computers on the internet are identified by their IP address (37.48.81.50)
- All traffic gets chopped into little packets with the destination address, which are then sent from your laptop
    - via the Wifi access point (home, cafe, ...)
    - via your ISP
    - via your country's network
    - possibly around the world
    - to another network, ISP, server, ...
    - etc.
- Basically, by default, in clear text: everyone on the way could read along



## Asymmetric encryption

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


## MITM Attack

TBD


## Some basic privacy technologies

### PGP (1991), GPG (1999)
[Pretty Good Privacy](http://www.symantec.com/products-solutions/families/?fid=encryption), [Gnu Privacy Guard](https://gnupg.org/)

The gold standard in encryption. PGP is a proprietary program owned by Symantec since 2010, while GPG is the open-source version. Both implement the open standard OpenPGP for asymmetric encryption. It is by far the most versatile and well audited algorithm used to sign and encrypt any kind of data. Its creator Phil Zimmerman was under investigation for many years in the United States for “exporting ammunition without a license” for which offering his cryptosystems. He challenged these investigations by releasing the source code freely in a printed book that anybody could buy and scan, actions protected by the First Amendment.12 Some people even had the basic algorithm tattooed on their bodies, thus making it technically illegal for them to “export” themselves from the country. GPG is a library and command line utility, but several applications for Linux, OS X and Windows and smartphones are available, as well as plug-ins for Outlook, Thunderbird, and OS X Mail that make email encryption relatively easy. The GPG project was significantly funded by the German Government, but is currently soliciting donations to employ two full-time developers.


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

