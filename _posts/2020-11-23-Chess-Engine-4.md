---
layout: post
title:  "Algorithms in Chess Engines"
author: [ Aadarsh , Kunwar  ]
categories: [ Chess ]
image: assets/images/engine4.jpg
usemathjax: true
---

In the previous article we explored some basic evaluation functions and gave an algorithm which makes n-move deep analysis for any position. Now we look at more advanced algorithms to evaluate best moves in a given position. 

## The Infinity Lemma: 

The infinity lemma in chess (and other games) states that these games cannot go on forever, that is the number of moves in the game is finite. In chess, the infinity lemma is enforced by the 75 move rule, which states that if no pieces are captured and no pawns are moved over a sequence of 75 consecutive moves, then the game is declared to have ended in a draw. 
Terminal positions
A terminal position is a position from which no legal moves are possible. Associated with any terminal position p is an integer f(p) which represents the value of this position to the player whose turn it is to move in p. The value to the other player is assumed to be -f(p). 

## Recursive formulation

The problem is to find the best move in any position. We assume the best move is the one which achieves the greatest possible value when the game ends if the opponent plays optimally. 
Let F(p) be the greatest possible value achievable from position p from the viewpoint of the player whose move it is.
Say in position p we have d moves, $$ p_1, p_2, …, p_d $$ . Now after playing a move $$ p_i $$ the position will have evaluation $$ -F(p_i) $$ for the same player, therefore - 

        $$ F(p) = f(p)  , if d=0 $$

           $$  =  max(-F(p_1),-F(p_2), …, -F(p_d)) , if d > 0 $$

## A Naive approach:

A very simplistic approach to calculate F(p) for any position p is to explore every possible sequence of moves starting from p. These sequences can be arranged in the form of a tree, which is called the game tree.  Naturally, these sequences will end at terminal positions with associated values f(p), and the aim for the players is to maximise their value at the end of the game. 
Unfortunately, the brute force approach is not a feasible approach to try and find the best move in a position . This is because the number of positions to consider in such a scheme is extremely large (more than the number of atoms in the universe) and modern computers will take an incredibly large amount of time to complete these computations.

## Optimizations:

Clearly, we need to optimise our basic solution strategy to achieve a feasible real-world solution. The remainder of the article is going to be dedicated to two major optimisations that have significantly accelerated the process of finding the best moves in a given position. 

## Branch and Bound :

The main aim behind the branch and bound optimisation is to reduce the number of states we need to visit in the game tree. The key intuition is this; if we have two possible moves $$p_1$$ and $$p_2 $$ and the opponent has a response to $$p_2 $$ that is at least as good as their response to $$p_1$$, then we don’t need to explore the subtree of $$p_2$$. This is because our opponent can force us to play to the less favourable position $$p_1$$ and hence we only need to explore the subtree of $$p_1$$. 
## Transposition table

Another optimisation can be made which relies on being able to store the already processed positions. Say we calculate $$ F(p_i) $$ for a position $$ p_i $$ . Now say after a string of moves we are at a stage where we need to calculate $$ F(p_i) $$ again. Here instead of calculating the function again we can use the value we calculated before. A practical problem is that there are too many positions to store, therefore we have to replace certain positions when overflow occurs with suitable replacement policy. 
The first positions to be replaced are the ones which cannot recur e.g. if the number of pawns changes. After that different strategies based on tree depth, ageing, etc. are used to select the positions to be replaced.

