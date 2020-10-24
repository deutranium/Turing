---
layout: post
title:  "Understanding a Modern Chess Engine"
author: Aadarsh
categories: [Chess]
image: assets/images/chess_image1.jpg
---

## Motivation

Chess is undeniably one of the most popular board games in the world. Millions of people are enthralled by the intellectual challenges the game poses and are amazed by the richness of the  game. It is believed that a primitive version of chess (Chaturanga) was developed in India in the 6th century and quickly spread across the world, the rules being modified slightly in the process. The rules of chess as we know it today were formalised in the 19th century.

As the game grew in popularity, analysis of chess positions became increasingly prevalent. As early as the 15th century books analysing chess positions were published and with the rise of modern competitive chess the number of these books grew exponentially. Many of these books tried to describe heuristics to find the best moves in different types of positions, but it was clear that the level of analysis was highly insufficient in many places. Hence, the central question of finding the best move in a given position was often left unanswered(or wrongly answered).  

It is interesting to note that before the rise of the chess engine, the top players in the world were the final authority on what the best move in a given position was. The development of computing technology in the late 19th and 20th century provided an opportunity for this to change. Finding the best move in a given chess position was a problem that was tailor made for the primitive computer due to its highly deterministic nature and programmers jumped at the chance to try and create a program that could play chess better than the best humans in the world. In 1997, a computer program named Deep Blue defeated the world champion Gary Kasparov (this was a major event in chess history because Gary Kasparov is arguably the greatest player of all time and was in his prime in 1997)  and from that point on chess engines have demonstrated time and again that they are the best chess playing entities in the world. The best modern chess engines are around 800 ELO (ELO is the chess rating scheme) points better than the current world champion Magnus Carlsen and it looks like no human will ever be able to compete against these programs.

In this series of articles, we will be exploring the algorithmic developments and thought processes that led to humans creating software that can play almost perfect chess. We are going to look at different strategies that various programmers utilised and how they managed to beat hundreds of years of human experience and knowledge.
