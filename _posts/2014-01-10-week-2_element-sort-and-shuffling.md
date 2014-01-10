---
layout: post
title: "week 2_element sort and shuffling"
description: "random shuffling"
category: "coursera"
tags: [coursera, Algorithm]
---
{% include JB/setup %}
#Shuffle
##1.1 Fisher–Yates shuffle
```
从原始数组中随机取一个之前没取过的数字到新的数组中
```
the simple way to implement but extra useage for memory and need (n square) time
##1.2 Knuth-Durstenfeld Shuffle
```
To shuffle an array a of n elements (indices 0..n-1):
  for i from n − 1 downto 1 do
       j ← random integer with 0 ≤ j ≤ i
       exchange a[j] and a[i]
``` 
time O(n)
##1.3 Inside-Out Algorithm
the algorithm in ppt

```
To initialize an array a of n elements to a randomly shuffled copy of source, both 0-based:
  a[0] ← source[0]
  for i from 1 to n − 1 do
      j ← random integer with 0 ≤ j ≤ i
      if j ≠ i
          a[i] ← a[j]
      a[j] ← source[i]

```
time O(n)