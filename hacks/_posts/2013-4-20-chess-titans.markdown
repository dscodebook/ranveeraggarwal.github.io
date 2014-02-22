---
layout: hacks
title: Chess Titans
subtitle: Classic Chess game built on lisp
category: hacks
zip_url: https://github.com/ranveeraggarwal/Chess-Titans/archive/master.zip
issue_url: https://github.com/ranveeraggarwal/Chess-Titans/issues
repository_url: https://github.com/ranveeraggarwal/Chess-Titans
codeveloper: Tarun Kathuria
---

###Brief description of the project:
We have implemented the classic game of Chess. By default, the game is supposed to be a 1 player game which uses the minimax algorithm with alpha-beta pruning for finding an optimal move upto a certain depth(default 2). However, both the depth and the mode can be changed to 2 player as well.

---
###How to run: 
On the terminal, type `drracket ChessSubmission.scm &`. Hit <kbd>Ctrl+R</kbd>, and the GUI will show up. Click on new game image button, then the level 1 image button and start playing!
<!--
Here are a few snapshots:

<script>
$(document).ready(function() {
    $('.pics').cycle({
		fx: 'scrollDown',
		speed:    250, 
                timeout:  2000 
	});
});
</script>

<div class="pics"> 
    <img src="{{site.url}}/img/rr1.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr2.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr3.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr4.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr5.jpg" width="400" height="224" /> 
</div> -->
