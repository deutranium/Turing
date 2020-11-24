---
layout: post
title:  "Introduction to Cryptography"
author: [ Sarthak, Tushar ]
categories: [ Cryptography, Security ]
tags: [cryptography, introductory]
image: https://cdn.pixabay.com/photo/2015/12/13/15/32/cryptographic-1091257_1280.jpg
---

Cryptography is the science of data security and privacy in the context of communication. It may seem like a loaded definition, so let us understand what it means. Often, we want to tell someone something, but do it in a manner so that anyone else cannot know of it. This may be as simple as passing notes in a history class to something complex and important, such as sending company or government secrets. Remember when Sheldon speaks in Klingon with Leonard in Season 10 Episode 7 of The Big Bang Theory, so that Amy and Penny don’t understand them?

<!-- Youtube video embedd-->
<br>
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/OOq3g8a7HRk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

Here Sheldon "encrypts" his data by speaking in Klingon rather than English (which everyone would understand) and Leonard is the only other person who can "decrypt" it and understand what is being said. Cryptography includes several fields, such as User authentication and Information integrity (verifying the information has not been tampered with). In some cases, you want to share the information with someone, without letting them see it either! That may seem vacuous, but that is how your passwords are stored. More about this, and other aspects of cryptography, coming soon.

In today's age, where the internet is often considered as a right, and social networking is higher than ever- be it through sites like Facebook or through messengers like WhatsApp, secure communication is an integral but usually overlooked part of our daily lives. We create 2.5 quintillion bytes of data every day and 90% of our complete online data was created in the last 2 years. Let that unfathomable size sink in. These statistics give an insight into how crucial cryptography is in today's world. Cryptography is the reason that you are sure the person you are texting is actually the person that you want to text, and not some impostor. It is what allows you to receive the messages that someone sent you without being accessed or adulterated by someone else. It is being used as you use this site, to make sure a hacker is not pretending to be this blog. 

Evidence of use of cryptography in some form has been seen in most major early civilisations. The first known evidence of cryptography is the use of hieroglyphs in an inscription carved around 1900 BC, in the tomb of the nobleman Khnumhotep II, in Egypt. Arthshashtra by Kautilya, an Indian classic on statecraft dated to around 200 BC, mentions giving assignments to spies in "secret writing". At about 100 BC, Julius Caesar is known to have used a simple substitution cipher to convey secret messages to his army generals posted in the war front. It is by far the most popular ancient cipher today, commonly called as "Caesar cipher". During the 16th century, Vigenere designed a cipher that was supposedly the first cipher which used an encryption key. In one of his ciphers, the encryption key was repeated multiple times spanning the entire message. Then the ciphertext was produced by adding the message character with the key character modulo 26. At the start of the 19th century, when electricity became the new major power source, Hebern designed an electro-mechanical contraption which was called the Hebern rotor machine. 

These early forms of encryption can be easily broken with modern computational power, so a need of superior of cryptographic ideas was established. With the advent of the digital age, modern data and communication is largely digital, which is why cryptography is largely applied to computers. For this, cryptographic methods had to become mathematical. In 1945, Claude Shannon of Bell Labs published an article titled, "A mathematical theory of cryptography.", now considered to be the advent of modern cryptography. This, along with the idea of public key cryptography emerging in the 1970s, materialised as the RSA algorithm and Diffie–Hellman key exchange, are arguably the foundations of modern cryptography. 

If you want to know more, check out the article [Cryptographic Algorithms]({{ site.baseurl }}{% post_url 2020-11-13-crypto-algo %})