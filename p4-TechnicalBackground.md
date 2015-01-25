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
  - **Authentication:** The recipient is who you think they are. (*No MitM attack*) **( Define MITM - but nice defines on all the other points :) )**

## How the Internet works (roughly)

- Computers on the internet are identified by their IP address (37.48.81.50) **( Give a better explaination i.e. compare it to a physical address - this point needs to be driven home)**
- All traffic gets chopped into little packets with the destination address, which are then sent from your laptop **(packets?)**
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
    - Plain Text + key + algo = Ciphertext (=gibberish) **(Define plain text,key, algo and ciphertext - all are technical terms. Also what key?)**
    - send the Ciphertext across (even a non-secured line) **(What's a non-secured line in this context?)**
    - Ciphertext + key + algo = Plain Text **(Same key used to encrypt? Or are we doing asymmetric? :))**
- Now, here the magic: the keys for encryption and decryption need *not* be the same. So, you create a private key and a public key. The public key can be published everywhere. **(Define this before talking about it in the previous points)**
- If someone has the public key, they *cannot* reconstruct the private key. **(Why not?)**
- So: 
    - Plain Text + Bob's public key + algo = Ciphertext (=gibberish)  **(Hmmm, looks like this is a good description of asymmetric - so what was the last section?)**
    - send the Ciphertext across (even a non-secured line)
    - Ciphertext + Bob's private key + algo = Plain Text
- Anything that's been encrypted by Bob's public key could be plastered all over the wall: Only Bob (or, more precisely, whoever holds Bob's *private key*) can decrypt and read it **( Elaborate on the more presicely bit)**
- Key management can be a bit tricky: you want to make sure, when you send a message to Bob, that it's really him that holds the private key, not some impersonator. Best to check with him by comparing "finger prints"! **(fingerprints? Of whose hand? ;) Define and explain :) )**


## MITM Attack
