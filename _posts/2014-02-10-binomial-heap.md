---
layout: post
title: "Binomial Heap"
description: "Binomial Heap"
category: "Algorithm"
tags: [Algorithm]
---
{% include JB/setup %}
#Binomial Heap
![time cost for heap](http://media-cache-ak0.pinimg.com/originals/c3/e1/a0/c3e1a004e90b6dd3c52d866cfa224e3f.jpg)
##For MST (prim's algorithm)
V = n, E = m
Binomail Heap: O(nlogn + mlogn)  
Fibonacci Heap: O(nlogn + m * 1)  

##operation for Binomial heap
Delete a key:  
1. BINOMIAL-HEAP-DECREASE-KEY(H,x,−∞)  
2. BINOMIAL-HEAP-EXTRACT-MIN(H)