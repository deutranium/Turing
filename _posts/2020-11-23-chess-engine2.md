---
layout: post
title:  "Working of a Chess Engine II"
author: Kunwar
categories: [Chess]
image: assets/images/EkdwuWgXYAUzaIb.jpg
usemathjax: true
---

## Perfect game
In principle, it is possible to construct a machine to play a perfect game i.e. a machine which would never lose or draw a won position and never lose a drawn position and would capitalize on any mistake made by the opponent. Two impractical methods are -
1. Consider all the possible moves in a given position, then all the possible moves for the opponent and so on. The game must end after a finite number of moves(due to the 50 move drawing rule). Each of the variations must then lead to either a win or a lose or a draw. Working backwards from the end we can determine if there is a forced win, lose or draw. Being conservative with our calculations, this will still lead to a computing time of approximately 1090 years for the first move.
2. Another method is to have a dictionary of all positions of chess pieces. For each position there is an entry giving the correct move(calculated by the above method). The machine simply looks at the entry for it’s position and makes the move. The number of possible positions is of the order of 1043 which makes this unfeasible.

## Strategy
Considering the above section, it is only practical to view the problem as designing a machine which plays skillful instead of perfect chess. A strategy may be defined as the process of choosing a move in any given position. In theory of games if a strategy always chooses the same move for the same position it is called “pure” strategy otherwise if it relies on statistical elements and does not always result in the same choice it is called a “mixed” strategy.


- **Evaluation function:**
As discussed before, any position P leads to either a win, lose or a draw. An evaluation function f(P) assigns to position P a value which determines to which category(win, lose, draw) the position P belongs.

In chess, because of the complicated nature of the rules, there does not exist an exact evaluating function but it is still possible to make approximate evaluations. Indeed all chess students are taught to perform such evaluations. These are based on the general structure of the position, the number and kind of black and white pieces, pawn formation, mobility, etc. 
The following are some principles to evaluate chess positions - 
1. The relative values of queen, rook, bishop, knight and pawn are about 9, 5, 3, 3, 1, respectively. Thus other things being equal if we add the numbers of pieces for the two sides with these coefficients, the side with the largest total has the better position.
2. Rooks should be placed on open files. This is part of a more general principle that the side with the greater mobility, other things equal, has the better game.
3. Backward, isolated and doubled pawns are weak.
4. An exposed king is a weakness (until the end game).

These are only crude generalizations from observing numerous games and all can be contradicted by particular counter examples. However, from these we can construct a crude evaluation function like - 

$$ f(P) =    500(K-K') + 9(Q-Q') + 5(R-R') + 3(B-B'+N-N') + (P-P') $$


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$$    - 0.5(D-D'+S-S'+I-I') $$ 


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$$    + 0.1(M-M') + ... $$


where - 

&nbsp;&nbsp;&nbsp;&nbsp;K,Q,R,B,N,P are the number of white kings, queens, rooks, bishops, knights, pawns respectively,

&nbsp;&nbsp;&nbsp;&nbsp;D,S,I are doubled, backward and isolated white pawns,

&nbsp;&nbsp;&nbsp;&nbsp;M is the white mobility (measured, say, as the number of legal moves available to white).

&nbsp;&nbsp;&nbsp;&nbsp;Primed letters are the similar quantities for black.

Here the coefficients 0.5 and 0.1 are merely rough estimates.
This is only for illustrative purposes and there are many other terms which should be included. Checkmate has been included by giving the king a value larger than the maximum of all other terms combined.

Note - An important point to note regarding simple evaluation functions like the above example is that they are only significant in relatively quiescent positions. For example if white captures black’s queen in an exchange, though white is for a moment a queen ahead, black will immediately recover it.

An improvement to this evaluation function would be to consider different future variations which is how chess players calculate. Variations are investigated until a somewhat quiescent position is reached. At this point an evaluation is done. The variation leading to highest evaluation is chosen while the opponent is assumed to be playing to reduce this evaluation.

This leads to n-move deep analysis of a position.
Mathematically, an example of one move deep analysis is as follows - 
Let the current position be P and let the legal moves be $$M_1, M_2, …., M_n$$.
Let $$M_{1}P, M_{2}P, …., M_{n}P$$ be the position after $$M_1, M_2$$, etc. are played. 
Now choose $$M_i$$ such that $$f(M_{i}P)$$ is maximum.

A better strategy will involve considering the opponent’s reply - 
Let the current position be P and let the legal moves be $$M_1, M_2, …., M_n$$.
Let $$M_{i1}, M_{i2}, …., M_{is}$$ be all the legal moves of the opponent in position MiP.
Black plays to minimise the evaluation and can be assumed to choose move $$M_{ij}$$ such that $$f(M_{ij}M_{iP})$$ is minimum.
White should choose the move Mi such that $$f(M_{ij}M_{i}P)$$ is maximum where $$M_{ij}$$ is chosen for any Mi such that  $$f(M_{ij}M_{i}P)$$ is minimum.


Similarly, a two move deep strategy can be constructed by extending the above argument to consider two moves each by machine and opponent.
I.e. we will consider all the two move combinations possible by legal moves. Now we fix all other than the opponent's last move. This last move is varied and the one for which f is minimum is chosen as the assumed last move by the opponent in this variation. Now our second move is changed and this process is repeated again. This is done for all possible second moves for us and the one giving maximum f is chosen. We continue backwards this way to the current position and chose the best move.

This can be generalised for n moves.
