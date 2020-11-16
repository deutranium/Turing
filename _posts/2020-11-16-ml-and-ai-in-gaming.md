---
layout: post
title:  "The Advent of ML and AI in Gaming"
author: [ Ainesh, Rishabh ]
categories: [ Artificial Intelligence, Machine Learning, Gaming ]
image: assets/images/ml-and-ai-in-gaming.jpg
---

## Bots and NPCs

Historically, video games have heavily employed the usage of ‘bots’, short for robots, and Non-Player Characters (NPCs). These computer-controlled bots play games in the place of a human and attempt to mimic the behaviour exhibited by regular human players. Bots allow players to experience multiplayer gameplay without necessarily having to go online and play with other human players, while NPCs automate repetitive tasks and positions in the game. These bots and NPCs initially performed actions according to predefined programs and could not go out of the scope of the instructions that were fed to them. This essentially meant that they followed programmed operations; for example, if a character shot them, they would perform whatever they were programmed to do, say dodge the bullet. This made these bots and NPCs one-dimensional and predictable, which frankly decreases the fun that one can have while playing a game. Experienced players, for example, would know what to expect upon performing a certain action, hence eliminating the element of surprise and making the game repetitive. However, with the advent of artificial intelligence, the possibilities for what we could potentially do with bots, NPCs and other avenues in the field of gaming became endless.

## Why AI and ML in Gaming

With the growth of advanced computational techniques and computational power, we can now implement AI and ML techniques in gaming. This is expected to change gaming for the better as (theoretically)  the bots that players fight against can learn how the player plays and can become increasingly challenging at a determined pace, making the players better. This, in theory, could prevent spamming, the repeated use of the same action, which is a very annoying problem in gaming as it 
lowers the skill required to play and makes the game monotonous.

## Advantages of AI and ML in Gaming

As compared to a regular bot, which runs on a predetermined algorithm, an AI bot would require a considerable amount of data to train it which can be obtained by deploying the bot in public lobbies of lower-ranked players. This allows the bot to learn to fight weaker players making sure that it is not too challenging and keeps the game interesting for all players. Also, ML techniques do not need to be restricted to bots; it can be used to make Ray-Tracing and VR technologies faster and 
more efficient and can hence be introduced to devices with weaker specifications.

## Algorithms and Techniques Used in Games

Let’s talk about a few algorithms which may be used in gaming soon. In the popular game series FIFA, an A* search algorithm can be used to help analyse the proximity of the opposition players and space around them to identify better passing opportunities and is also considered to be a “smart” pathfinding algorithm. When a human player has the ball, his teammates will understand if you have the chance to make the pass and move accordingly to create the chance for you to pass or take 
the shot. Some other ML techniques that can be used in games are Deep Learning, Convolutional Neural Networks, Long Short-Term Memory and the most popular methods thought of in this context, Reinforcement Learning and Neuroevolution.

## Implementation IRL

Let’s explore how we would go about implementing an AI bot in a video game. Take Super Smash Bros for example. It is a popular 2d fighting game with only 7 basic inputs (4 movement keys, light attack, heavy attack and dodge). The bot would perform a move which can be judged using a scoring system where a hit would return a large number and would be understood by the bot as a good outcome. Upon its evolution, through hundreds and thousands of moves, it would perform a certain series of actions, calculating its scores and storing the highest scored implementation. After that, it will perform smaller changes around it to find a better move-set. This is a general theory of what we could think of implementing. In theory, we can expect the bot to wait patiently and look for an opening or even perform risky off-stage moves which can easily turn to kills. MIT students have implemented this; they even beat the world champions. [https://github.com/vladfi1/phillip](https://github.com/vladfi1/phillip)

<!-- Youtube video embed-->
<br>
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/mxgTdi1W2PU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

## Areas Where This Work Can Be Expanded To

AI in games, while still being in a primitive state, when compared to other recent advancements in the general field of AI, has an immense practical value, extending far beyond the reach of just video games. The impact of video games in AI research can be summed up in 3 points.
> Firstly, games are a completely self-contained problem where pretty much all the possible events, variables, and outcomes are known.This is extremely beneficial in the testing and development of AI.\
> Secondly, we can generate large amounts of data via randomised gameplay. It's no secret that training data is essential, and in many cases a laborious task, especially when you take into consideration the annotating part, i.e. labelling the data we obtain so that we may properly analyse it.\
> Thirdly, video games, having deterministic outcomes, with environments and variables that we may control and define, allows for the process of trying to sift through the data to find the relevant data a lot easier. Hence it is evident that games play an essential part in AI research.

For example, DeepMind, one of the top AI-based research companies, is extensively involved in the world of video games, and have made several advancements in the field of AI with the help of video games. DeepMind has done notable work towards protein folding, and several of its algorithms have been implemented in Google data centres.

## Future of AI in Gaming

With the field of AI still being relatively new, having a large scope for innovation, the future of the integration of AI and video games does look bright indeed. The main advantage of AI in video games is also its Achilles’ Heel; it isn’t predictable., which isn’t always helpful. Game developers would want to know how a player would interact with the game and the game world. Implementing Deep Learning or a Neural Network is just plain unpredictable and could do anything. This isn’t practical nor ideal in the world of gaming. With unexpected actions being performed, this could lead to the game-breaking in case an outcome has not been tested and taken care of by the developers. Hence, much of the AI that is currently being used in video games is a scaled-down version that is a lot more predictable to prevent unexpected actions and possible errors occurring. In the future, we could see these advanced types of AI being implemented, which could adapt the entire game according to your preferences. For example, if you tend to play and enjoy certain levels of a game more than others, the game could create new levels that combine common aspects of the levels you liked more, which may lead to a better player experience. This could be extended to create personalised truly self-learning game characters that change as you interact with them. A whole video game, unique to you and personalized to what you like. Now that’s exciting!!!
