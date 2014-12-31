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
