---
layout: post
title:  "Working of a Chess Engine I"
author: Kunwar
categories: [Chess]
image: assets/images/chess_image1.jpg
---

The story of chess engines begins in the year 1770, when the inventor Wolfgang von Kempelen revealed “The Turk”, a chess playing machine, to Empress Maria Theresa of Austria ,attempting to impress her and the general public. The machine managed to play at quite a high level and also demonstrated a solution to the famous Knight’s tour problem(The question is to cover all squares of a chessboard with a knight such that each square is visited only once). The legend of “The Turk” spread rapidly and within a few years the machine was touring Europe, defeating many people along the way. Unfortunately for Kempelen, the machine was shown to be a fraud. The machine was designed to allow a human operator to remain hidden underneath the chess board and play against the challenger. All in all, “The Turk” was an ingenious creation that has historical significance in our story but really did not add much to the theory of automated chess.

After the Turk, progress towards automated chess stagnated for a while. The boom in computing technology and corresponding developments in electrical devices (like transistors) provided people with a completely new angle to attack the problem. Instead of attempting to build a machine that could play chess, people started exploring the possibility of writing programs that could play chess. It is important to realise that apart from the artistic joy of  solving the problem of finding the best move in a given chess position, the aforementioned solution provided computer scientists and neuroscientists an opportunity to ask deeper questions about the nature of human and machine intelligence. Also chess has very well defined rules and this made it a perfect fit for the primitive computer. Now we discuss in depth the evolution of chess engines starting from the first rigorous study of the matter by Claude Shannon. 

## Important Properties of the Game:
1. The problem is clearly defined i.e. the possible moves and the objective(checkmate) are absolute. 
2. The game ends in a finite number of moves.
3. The discrete structure of chess fits well into the digital nature of modern computers.

## Position
In chess there is no chance element(apart from which player plays white and subsequently first) and each opponent has “perfect information” at each move to all the previous moves. From von Neumann and Morgenstern, 1944 any chess position then must be -
1. A won position for white i.e. white will win however black plays
2. A draw position i.e. both sides can force a draw however the other side plays
3. A won position for black i.e. black will win however white plays

No method is known for determining with absolute certainty which of the three categories a position belongs to. If there were one could determine the outcome of the game after the first move. For example, say we made a slight change to the rules of the game such that a player is not forced to move a piece at their turn of the play and can, if they choose, ‘pass’. Now we can prove that white can at least draw with ideal play. For, in the initial position white is either winning or not. If white is winning let white make the winning move otherwise let white pass. If white passes, due to the symmetry of the initial position as white had no winning move neither does black now. So the best black can do is draw. 

Any ‘position’ P in chess will require the following data to be well defined -
1. A statement of the positions of all pieces on the board. 
2. A statement of which side, White or Black, has the move.
3. A statement as to whether the king and rooks have moved. This is important since by moving a rook, for example, the right to castle on that side is forfeited.
4. A statement of, say, the last move. This will determine whether a possible en passant capture is legal, since this privilege is forfeited after one move.
5. A statement of the number of moves made since the last pawn move or capture. This is important because of the 50 move drawing rule


