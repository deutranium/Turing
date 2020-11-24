---
layout: post
title:  "Social Effects of GANs (3/3)"
author: [Kshitijaa, Ainesh]
categories: [ GAN ]
image: assets/images/intro-to-gans.jpeg
usemathjax: true
---

As you must have seen in the previous two articles of the series: [Introduction]({{ site.baseurl }}{% post_url 2020-11-23-GAN-social %}) and [Applications]({{ site.baseurl }}{% post_url 2020-11-23-GAN-application %}), GANs can produce "realistic" data, but mind you, it is still "realistic" and not "real".

Coming to the social aspects of this technique, you must have seen a few examples of the applications of GANs in the [previous article] and how they can affect us. This article will mainly discuss the threats it can pose.
One can easily guess that the main issue that can be perceived as a threat would be somehow linked to differentiating between the “realistic” and “real” data. This can lead to counterfeiting through deep fakes etc., in even essential services like banking.
To analyze the scope, try to find which of these two people is fake and which one is real. The odds are you’re able to find the minuscule difference with careful analysis, but most likely, you would not be able to


![](../assets/images/GAN-social.png)

Well, regardless of who you thought is real and who is fake, it’ll be surprised to know that both of these are fake, generated using a GAN (source: [here](https://towardsdatascience.com/the-dangers-of-adversarial-learning-874a95cdddd3))

Now that you know the limits of the human brain to distinguish between realistic and real data, we shall analyze the domain-specific effects below.

### Banking
Banking relies on the authentication of the user to carry out any transaction done. Using GANs, one can create fake profiles and carry out all the processes a real human can.

### Ethics
Deepfakes generated using such techniques can be used for malicious purposes like catfishing etc., to lure people into even giving money to these fake entities.

### Porn Industry
Using GANs, one can easily convert a typical picture of any person to look like an adult movie actor, resulting in social consequences which they might not have expected, in some cases even leading to depression and suicide because of the spread of realistic fake images/videos. The AI firm Deeptrace found 15,000 deepfake videos online in September 2019, a near doubling over nine months. A staggering 96% were pornographic and 99% of those mapped faces from female celebrities on to porn stars.

## Conclusion
We just saw the adverse effects GANs can have, which are worsened with the fact that the codes for such actions are usually easily accessible. All this leads to a wide-spread dilemma about both the accessibility and the scope of use of these. As a result, required measures should be taken while ensuring that the technology does not become restricted to a particular entitled section. One such example was when OpenAI decided to share the code with limited text generation capabilities instead of what they thought would be too dangerous to be released into the public domain.

With technology and research in the field of GANs developing at a rapid pace, we must ensure that humans are always one step ahead of technology, because otherwise there could be severe implications.