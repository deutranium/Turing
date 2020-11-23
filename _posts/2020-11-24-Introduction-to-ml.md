---
layout: post
title:  "Introduction To Machine Learning"
author: [Tushar , Pahul]
categories: [Machine Learning]
image: assets/images/ML2.jpg
excerpt: "A basic insight into Machine Learning"
---

## What is Machine Learning? 





QUICK!! Find the answer to `4371 * 2584`. Do it in your head. Hard right? 

 

Now do this 

 

QUICK!! What's in this picture? 

 

![](../assets/images/MLcar.jpg)

 

How quickly did you do this? Was it hard? 

 

Great. Now go to someone, and teach them do these. Which one is easier to explain? 

 

For the first task, first you have to teach them single digit multiplication tables, and then for multiple digits, you have to teach them the long multiplication technique we all learnt in elementary school. Take the last digit of the second number, and multiply it with the first number, digit by digit, taking care of all the carry-overs. And then move on to the next digit of the second number, shift it by one place… and so on, you all know the drill. We have a clear and well-defined set of instructions. 

 

But what about the second task? How do you teach someone to look at a picture and identify whether it's a car? It might seem a trivial task for our brain, but if you think of it, there is no obvious set of well-defined instructions. So it is something which can not be directly 'taught' or 'fed into' someone's mind. 

 

Now let's come to the case of a computer. The first task is something that all modern computers can easily do with the instructions stored in their ALUs. They will convert the numbers in binary, follow the instructions (mainly a series of AND and OR operations), convert back to decimal and output the answer. Pretty straightforward. 

 

Coming to the second task, we ask a question; is it even possible for a computer to do so? If yes, is there a set of instructions that could be 'coded' into a machine which identifies a picture of a car? All these questions are valid, because how a machine handles information and instructions is much different than how we do. And Machine Learning is an attempt to answer these kind of questions. 

 

Machine Learning involves computers learning how they can do certain tasks without explicitly programmed to do so. Computers learn from a sample data provided to them, usually in huge amounts. This "training data" usually contains example inputs and their expected outputs and the machine is then made to figure out a general rule that maps these inputs and outputs. 

 

We rely on Machine Learning when the tasks are not simple enough, and could be challenging for a human to manually create the algorithms. Hence we help the computer develop its own algorithm, rather than specifying each and every step. Machine Learning has, thus, been a revolution in the world of computers. 

 

## History of Machine Learning 

 

It all started in 1950 when Alan Turing first proposed the idea of a machine having human-like intelligence. He came up with a test called the Turing test, although he called it the imitation game. In essence, if a machine can fool a person into thinking that it is human, then it is an intelligent machine. Later on, a small but significant change was made in Turing's paper where the question "Can machines think?" was replaced with "Can machines do what we (as thinking entities) can do?". 

 

In 1952, The first checkers program, that learnt as it played, was made by Arthur Samuel. He used something called alpha-beta pruning with minimax. Essentially he would search for the best move he could play, assuming the opponent played ideally. Since he had some memory constraints at the time, he used alpha-beta pruning to optimize it. 

 

In 1957, Frank Rosenblatt used Donald Hebb's [model of a brain cell](http://s-f-walker.org.uk/pubsebooks/pdfs/The_Organization_of_Behavior-Donald_O._Hebb.pdf)  and Arthur Samuel's works in machine learning to create the perceptron. It is an algorithm that is used for supervised learning of binary classifiers. In simple terms, it was an algorithm that could be used to classify data into one of two types of things. Like classifying a picture as either containing a cat or not containing a cat. 

 

In 1960, the use of multiple layers in a perceptron began. This opened a new path in neural network research. It led to things like backpropagation and feedforward neural networks. 

 

In 1990 the concept of boosting was introduced by Robert Schapire. Boosting algorithms are used to reduce bias during supervised learning and are used to turn weak learners into strong learners. Weak learners are people who take up an arts degree in college classifiers that classify such that their results are slightly better than random guessing. Strong learners are computer science undergrads classifiers that accurately classify the data given to them. 

 

## How does Machine Learning effect you? 

 

Presently, machine learning has led to humans being able to make chatbots that you talk to when you're lonely, voice recognition, self driving cars, better fraud detection, and much more. 

 

There are many places you can see the effects of machine learning in your own life. When Facebook suggests you to tag your friend on your post whom it recognised before you did, and when you shop for a ceiling fan on Flipkart and it suggests you to add a rope to the cart as well, it's all a result of machine learning. From your YouTube video recommendations and the cute single ladies that want to message you ads that Google shows you, to the bots that constantly search for possible frauds in a banking system and the bots that take down my memes inappropriate content on Facebook. From autocorrect that shows you the spelling of the word "gorogeous" to the text recommendation that puts a laughing emoji after you type "I'm so sorry for your loss". 

 

Training data highly influences the performance of your machine learning application. This can cause problems. A machine learning system trained on current customers only may not be able to predict the needs of new customer groups that are not represented in the training data. Machine learning systems used for criminal risk assessment have been found to be biased against black people. In 2015, Google photos would often tag black people as gorillas, and in 2018 this still was not well resolved, but Google reportedly was still using the workaround to remove all gorillas from the training data, and thus was not able to recognize real gorillas at all. In 2016, Microsoft tested a chatbots that learned from Twitter, and it quickly picked up racist and sexist language. This adds the need to make sure that test data is fair and equal, which is very hard to do when dealing with huge amounts of data. 


The next article in the series is :- [From Dictation To Automation]({% post_url 2020-11-24-Automation-Dictation %})