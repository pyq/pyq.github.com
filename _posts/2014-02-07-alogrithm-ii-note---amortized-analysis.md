---
layout: post
title: "Alogrithm II note   amortized analysis"
description: "amortized analysis"
category: "Algorithm"
tags: []
---
{% include JB/setup %}
#Amortized analysis
##3 method:
. aggregate method  
. accounting method  
. potential method

##Aggregate Method:
1.sum up all the cost for n operations. 2 use the result T(n)/n

##Accounting Method:
1. every operation cost = actual cost + credit.   
**credit used to pay future. can not in debt**

##Potential Method:
1. use the potential to pay next extra cost. can not be negative.

##Dynamic Table
expand and contract.