---
layout: projects
title: Chess Titans
subtitle: Classic Chess game built on lisp with AI based on Minimax Algorithm
category: projects
zip_url: https://github.com/ranveeraggarwal/Chess-Titans/archive/master.zip
issue_url: https://github.com/ranveeraggarwal/Chess-Titans/issues
repository_url: https://github.com/ranveeraggarwal/Chess-Titans
codeveloper: Tarun Kathuria
---

###Brief description of the project:
This project is an implementation of the classic game of Chess. By default, the game is supposed to be a 1 player game which uses the minimax algorithm with alpha-beta pruning for finding an optimal move upto a certain depth(default 2). However, both the depth and the mode can be changed to 2 player as well.

---
###The Implementation
We programmed moves according to the rules of the game. Then we designed a function that continuously checks the valid moves for the current board state. This in turn gave the basic implementation - No AI.

Next, we took up the heuristics from Wikipedia and designated values to each piece. We then implemented the minimax algorithm that goes upto two levels to check the best possible move for the next turn and then used Alpha-Beta pruning to improve the running time.

---
###The GUI
The GUI was developed using the built-in DrRacket graphics toolkit.

---
###Snapshots
Here are a few snapshots of how the game looks during gameplay:

<img src="../images/chess-titans-2.png">
<img src="../images/chess-titans-1.png">
<img src="../images/chess-titans-3.png">

---
###How to run: 
On the terminal, type `drracket ChessSubmission.scm &`. Hit <kbd>Ctrl+R</kbd>, and the GUI will show up. Click on new game image button, then the level 1 image button and start playing!
