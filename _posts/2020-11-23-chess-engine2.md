---
layout: post
title:  "Working of a Chess Engine II"
author: Kunwar
categories: [Chess]
image: assets/images/chess_image1.jpg
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

$f(P) =    500(K-K') + 9(Q-Q') + 5(R-R') + 3(B-B'+N-N') + (P-P') $
 - 0.5(D-D'+S-S'+I-I') 
 + 0.1(M-M') + ... 








