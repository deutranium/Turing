---
layout: post
title:  "Quantum Cryptographic Protocols"
author: Aadarsh
categories: [ Quantum Cryptography ]
image: assets/images/share-a-coin.png
usemathjax: true
---


To understand the need for quantum cryptographic protocols ,we first need to look at the current state of classical ones. Current classical encryption schemes like RSA work on the basic principle that factorisation of the product of two large prime numbers is an extremely difficult and time consuming task to do with a classical computer. However , with a quantum computer, the process of factorisation is accelerated significantly via Shor's algorithm. Therefore, there was a need to harness the power of the rapidly developing quantum technology.

In this article we are going to explore 2 different problems which are solved using  quantum protocols. 

1) The first problem is to create 50 - 50 game for two parties who are communicating over a classical communication channel (like telephone). This sounds simple, but the catch is that the two parties do not trust the information that the other is telling them. Hence, coin tossing and other similar games are not acceptable solutions. This is because both parties do not see the coin simultaneously which adds a potential for either party to cheat ( this would not matter if both parties trusted each other) , thereby violating the 50 - 50 criteria . Essentially, this problem boils down to creating a game with an inbuilt "anti-cheating mechanism".

2) Quantum Key Distribution: In cryptography,a key refers to a string or some other information that is used to encrypt and decrypt messages.There are multiple different ways to distribute keys between different parties . These methods include the parties actually physically meeting up or sending the key over a normal communication channel. The problem with the former is that it is not feasible on a large scale and the latter is particularly secure as an eavesdropper can steal the key and use it to decipher transmitted messages. The aim of quantum key distribution is to allow the communicating parties to exchange a random,secret key in order to safeguard their communications. It has already been proved that given both parties have access to a secret,random key it is mathematically impossible for an eavesdropper to  steal information . (One time Pad cryptographic protocol).  

Quantum coin flipping is a scheme that describes a method to create such a game. Let's say Alice and Bob are the two parties who want to play this 50-50 game. The scheme works as follows:

1) Alice picks one of these basis and then randomly polarises a stream of photons, for example, if  she picks the rectilinear basis then for each photon she can randomly choose between horizontal and vertical and polarise each individual photons.

2) Bob receives these photons (through a fibre optic cable or something similar) and randomly measures each photon with either a rectilinear or diagonal polariser. 

3) After noting down all the polarisations, Bob guesses which basis Alice used, rectilinear or diagonal. This choice represents the 50-50 game that we set out to achieve.

How does this prevent Alice from cheating? The beauty of this method is that it provides a checking mechanism to ensure that Alice doesn't cheat.
Alice has two potential ways to cheat in this game and we need to understand how this protocol prevents both methods. Firstly, Alice can simply lie about the basis she chose. Let’s assume she used rectilinear polarisers but claims that she used the diagonal basis . Now , Bob can ask her about the direction of polarisation of all the photons he measured using the diagonal basis. Due to the fact that wave function collapse is a probabilistic phenomena,ie there is no way to determine which eigenstate the polarisation is going to collapse to , Alice will have a 50% of matching Bob’s measurement for each photon. If the number of photons is large enough, the probability of getting all of them right will go to 0, allowing Bob to detect the cheating.
Alice can also try to cheat is by not choosing a basis in the beginning, instead polarising the photons randomly with both basis. In this case,  her answers will not match with Bob’s measurement for either basis, clearly highlighting the fact that Alice cheated. 
One interesting thing to note is that this method depends on Bob measuring the photons randomly using polarisers of both basis. If he measures with only rectilinear polarisers and also guess that Alice used the rectilinear basis, Alice can just lie and say that she used the diagonal basis and Bob won't have any correct readings to cross check with Alice. However, if implemented correctly, the Quantum coin flipping protocol does provide us with a method to create a 50-50 game where neither party can cheat.


Quantum key distribution is a method for two parties to share a secret key. The speciality of quantum key distribution is that the two parties will be able to detect if an eavesdropper attempts to steal the key. Again, for simplicity, we are going to assume Alice and Bob are the two people who need to share this key.


## How does the scheme work?

1) Alice starts by creating a random bit string, with 1 representing vertical and 135 degree polarisation, and 0 representing horizontal and 45 degree polarisation.

2)She then randomly polarises a stream of photons corresponding to the bit string using either the diagonal basis or rectilinear basis and transmits the photons to Bob. Unlike quantum coin flipping, she is free to use both basis randomly, ie she can polarise the photon horizontally and the next one to 45 degrees.

3)Bob randomly measures each photon with one of the two possible basis and generates a bit string of his own using the same mapping, 1 representing vertical and 135 degree polarisation, and 0 representing horizontal and 45 degree polarisation.

4) Now , Alice and Bob start communicating on a classical channel.For quantum key distribution to work, the classical channel they use must be authenticated.An authenticated communication channel is one where the identity of both parties can be confirmed. For example, telephone is definitely not an authenticated channel as there is no way to confirm the identity of the person on the other side.  On this authenticated channel, Alice and Bob discuss the order of basis they used for measurement, without disclosing the actual direction of polarisation and drop all the photons for which they both used different basis.

5)At the end of this process, they are both left with the exact same set of bits without ever discussing these bits directly. This happens because when they both use the same basis, the photon is already in an eigenstate of the operator corresponding to Bob's measurement, and hence there is no probabilistic wavefunction collapse taking place.

## How does this prevent Eavesdropping?

Out of the bits they agree on (i.e. they have used the same basis for), they can discuss the exact values for a subset(generally 1/3) of these bits.Naturally, this compromises the secrecy of these bits, but these bits won't be used in the key anyway. The idea behind this is that anyone trying to steal the key will have to measure the polarisation of all the photons, and probability dictates that the eavesdropper would have measured some of these photons with the wrong polariser, forcing the photon to collapse to a state different from the state Alice polarised it to. Now, when Alice and Bob discuss the value of these bits, the expect a 100% match as all the bits have been polarised and measured using the same basis of polarisers. Therefore, if there is a mismatch on even a single bit, then they can conclude that there is an eavesdropper attempting to steal the key and switch to a different channel for sending photons and start the process again. One thing to note hear is that the above analysis is dependent on the assumption that the optic fibre cable (or whatever other medium is used to transport photons) is free from perturbations that could affect the polarised state of the photons.
Why does the classical channel of communication need to be authenticated? If the channel was not authenticated, then the eavesdropper could essentially play the role of Bob in the protocol. That is, the eavesdropper could measure the value of all the photons and then discuss with Alice, pretending to be Bob. In this scenario, the eavesdropper will get direct access to the secret key.
Assuming that the channel for transporting photons is free from perturbations and the classical communication channel is authenticated, quantum key distribution provides a foolproof method to distribute the secret key.
