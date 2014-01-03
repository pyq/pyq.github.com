---
layout: post
title: "coursera Week1"
description: "Union-Find&&Analysis of Algorithms."
category: "coursera"
tags: [coursera,Algorithms, Union-Find, Analysis]
---
{% include JB/setup %}
#Analysis of Algorithms
##Observation
![pic](http://media-cache-ec0.pinimg.com/originals/f6/46/4b/f6464baa027355c6c01e6c0afac4eeaa.jpg)

lg(T(N)) = b lg N + c  
b = 2.999  c = -33.2103  T (N) = a N b, where a = 2 c  
![pic](http://media-cache-ec0.pinimg.com/originals/6a/c1/31/6ac131bd0b98ee7309edf9cc61a782a0.jpg)
####**how to get his result**
theoretical method(not know how to get 23 and 11):  
1. lg(20743.56) = b lg1679616 + c  
2. lg(489.63) = b lg279936 + c  
=> 1 - 2: $$b =\frac {lg(20743.56/489.63)}{lg(1679616/279936)} = 5.4 / 2.58 = 2,09$$

empirical method
$$ratio = \frac {next.seconds}{pre.seconds}$$(eg. 20743.56/489.63 = 42.36)  
6 = 1296/ 216 = 1679616 / 279936

#####memory
Total memory usage for a data type value:・ Primitive type: 4 bytes for int, 8 bytes for double, ...  ・ Object reference: 8 bytes.  ・ Array: 24 bytes + memory for each array entry.  ・Object: 16 bytes + memory for each instance variable + 8 bytes if inner class (for pointer to enclosing class). [why???]  ・Padding: round up to multiple of 8 bytes.for example:
![memory examople](http://media-cache-ec0.pinimg.com/originals/56/e5/7a/56e57ae5e1c2a1e2f70b990b0b2d7b4f.jpg)

###dislike these knowledge below.
--------------------------------------
##Union-Find
###Quick-find
![Quick-find](http://media-cache-ak0.pinimg.com/originals/32/ec/cb/32eccbda7bb397c32eb6c8cc346539e7.jpg)
####Quick-union
![quick-union](http://media-cache-ec0.pinimg.com/originals/ed/4d/da/ed4dda79f68b32bbf832fd66bba38ca2.jpg)
###Weighted quick-union
・ Modify quick-union to avoid tall trees.
・ Keep track of size of each tree (number of objects). 
・ Balance by linking root of smaller tree to root of larger tree.
####performance
![performance](http://media-cache-ec0.pinimg.com/originals/90/00/38/900038587b2604a4bdfd81013268882f.jpg)

I think the most importance thing is using *2 virtual nodes* as the top and bottom when design the algorithm for programming assignment(**percolates**).

other things r not that interesting~:(
------
$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$
<script type="text/javascript" src="https://stackedit.io/libs/MathJax/MathJax.js?config=TeX-AMS_HTML"></script>