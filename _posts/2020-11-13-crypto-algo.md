---
layout: post
featured : true
title:  "Cryptographic Algorithms"
author: [ Sarthak, Tushar ]
categories: [ Cryptography, Security, Algorithms ]
tags: [cryptography, introductory, algorithms, secret key, public key, RSA, hashing, cryptographic algorithms]
image: assets/images/crypto_algo.jpg
---
 
We talked about cryptography and what it means in our first article, [Introduction to cryptography]({% post_url 2020-10-27-intro-to-crypto %}). Now we talk about it in more depth, with a focus on its implementation.
Some of the aims of Cryptography are to facilitate the following:
1. Guarantee that no party can view information that should not be visible to it.
2. To verify the origin of information (i.e. user authentication).
3. Guaranteeing that information has not been tampered with after someone sends it.
4. Accountability for information sent by someone.
5. Restricting access to particular information.
 
In modern times, most of our information is transmitted, stored, and received from or through the internet and other online services. As the internet is closely tied to computation, modern cryptography is also very closely tied to computation. This is why cryptography achieves most of what it achieves with an _"algorithm"_ - a sequence of instructions for a computer to follow. 
A common core of cryptographic algorithms is the principle of encryption. Suppose you want to hide some information, which we shall term as "Plaintext". Now, it need not strictly be text, but that is just how the name goes. **Encryption** is the process of transformation of this into something which is not easily recognisable or understandable, which we call "Ciphertext". Hence when someone discovers the Ciphertext, they will never think of the Plaintext. Each of these processes uses a "key". Cryptographic algorithms used to encrypt or decrypt are called "Ciphers".
 
<table class="table table-bordered"><tr><td style="text-align: center">
Plaintext<span class="text-secondary">---Encryption---></span>Ciphertext<span class="text-secondary">---Decryption---></span>Plaintext
</td></tr></table>
<br>
 
There are several ways of classifying cryptographic algorithms. We will talk about their categorisation based on the number of keys and their general application.
 
## Secret Key Cryptography
 
Secret Key Cryptography (SKC) methods employ a single key for both encryption and decryption. The well-known daily use of the lock and key is similar to this. You use the same key to lock _and_ to unlock the lock. Hence, the privacy of the key is integral to the security of the system. Since the same key is used at both ends of the communication, it is also called as Symmetric Key Cryptography. It has mainly two classifications – Stream ciphers and Block ciphers. One of the most well-known encryption method, the Caesar Cipher, is an SKC. Data Encryption Standard (DES) is an example of an important SKC today. The Enigma code used by the Nazis during World War II and now popularised by the Oscar-nominated movie _"The Imitation Game"_ was also based on SKC. Read about SKC in the article [Secret Key Cryptography]({% post_url 2020-11-16-SKC %}).
 
## Public Key Cryptography
 
Public key cryptography (PKC) has been deemed as the most significant development in modern cryptography. Modern PKC was first described publicly by Martin Hellman and Whitfield Diffie in 1976. This allowed for secure communication even over insecure lines. That is, one could communicate even if the threat of hackers is present! The mechanism of PKC is similar to how a mailbox would work. People with a key to a slit can deposit a letter and only you, with the other key to open the bottom, can view the entire contents. So you can safely communicate with people without meeting in person or making any prior agreements (which are required in SKC). This is a massive jump from making chits in a secret language in a boring class!
 
The mathematical method depends on "trapdoor functions", which are easy to process, but are relatively extremely difficult to revert, _unless_ you have specific special information. One trivial, but famous and useful example is of multiplication. It is easy to multiply two large numbers (imagine a size you feel would be difficult), but it is difficult to factor even one number of this size. One of the most used algorithms, RSA, is based on the difficulty of factorisation. Article on RSA coming soon!
 
Notice how all these examples use two keys. Due to this reason, it is called "Asymmetric Key Encryption". The two keys are called Public key and Private key and are self-explanatory in their names. However, every coin has two sides. Asymmetric systems are very time-consuming. So, often an SKC is used to encrypt a file and then PKC is used to provide the key used in it. More on Public Key Cryptography and Diffie-Hellman Key exchange in [this article]({% post_url 2020-11-21-PKC %}).
 
## Hashing
 
Hashing uses one-way functions that compute a string of fixed length, called a _Hash_, from the plaintext. It is very hard to find the original string from the Hash. Making minor changes to the starting text also changes the hash value completely. These functions in essence, use no key. Getting the plaintext from a hash is a tough thing to do. Unlike the trapdoor functions used in asymmetric encryption, hash functions do not have any information that makes them easier to decrypt. They are designed such that it is nearly impossible to decrypt them. Decrypting a SHA-256 hash will take, on average, more time than we humans will live in this universe.
Hash functions are used to provide a digital fingerprint for a file’s content, and by some operating systems to encrypt passwords. They are also used in blockchain. 
There are several different classes of hash functions. Here are some of the most commonly used:
* Secure Hashing Algorithm (SHA-2 and SHA-3)
* RACE Integrity Primitives Evaluation Message Digest (RIPEMD)
* Message Digest Algorithm 5 (MD5)
* BLAKE2
 
Each of these classes of Hash function may contain several different algorithms. For example, SHA-2 is a family of hash functions that includes SHA-224, SHA-256, SHA-384, SHA-512, SHA-512/224, and SHA-512/256.
While all of these hash functions are similar, they differ slightly in the way the algorithm creates a hash. They also differ in the fixed length of the hash they produce.
<br><br>
----
<br><br>
A point to note in modern cryptographic methods is that security is always a gamble if seen from a very barebones perspective. For example, we need to find just one number to break an RSA system. However, it is extremely _improbable_ to do so, since we use RSA-2048, which means the number we need to find is of the size 1028 bits, i.e. we need to check all primes between 2<sup>127</sup> and 2<sup>128</sup> since any of these could be our key. This means we need to check 2<sup>128</sup> - 2<sup>127</sup> = 2<sup>127</sup> numbers. Even if we remove all even numbers (since they cannot be primes), we get 2<sup>126</sup> numbers to check. That is more than 10<sup>37</sup>! Additionally, these are not one-time measures. To break this, we would have a time of about 3 minutes, since the key changes in about that time. So, it would be appropriate to say, "It is not a gamble if you know you're going to win". 
Further, you should compare this security to more conventional systems as well. For instance, breaking a lock open is not easy, but certainly doable. So, when you leave your house locked, you depend on this very ideology. The same holds for safes, where we trust our most treasured material possessions. So this idea of security where we rely on systems that can be broken, but we make it very inefficient to do so, and then hope that no one bothers to attempt it either, for this same reason.