---
layout: algopost
title: "Lonely Number"
category: algorithms
alcat: search
---

###Problem Statement   
We are given a list of elements. All elements but one occur twice. Find the element that occurs only once.  

###Solution  
**The Bad Way:**  
The brute force way to do it would be to go over the list once for each element and see if it exists twice. This is bad [O(n^2)].

**The Intelligent Way**  
Think `XOR`.  
XOR or *Exclusive OR* of two numbers is 0 if the two numbers are same.  
Basically, `a XOR a` will result in 0.  
We take XOR of all the numbers in the list. And that would give us the lonely number. As simple as that.  
How? Every number that occurs twice in the list will be XOR-ed with itself, and cancel. And in the end we'll be left with the number that occurs only once. This is a great example of application of a concept as simple as logic gates in Search-based algorithms.

Pseudocode:  

	init = 0;
	for number in list
		init = init XOR number;

	return init