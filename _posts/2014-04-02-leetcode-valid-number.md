---
layout: post
title: "LeetCode: Valid Number"
description: "regular expression for valid number"
category: "LeetCode"
tags: [LeetCode, Regular Expression]
---
{% include JB/setup %}
#Valid Expression#
I solve this problem by Regular Expression:

```
import java.util.regex.Pattern;
import java.util.regex.Matcher;
		marches()
		// here because 3. is also valid . and in java should use \\ represent \
		RegEx = "[-+]?([0-9]*\\.?[0-9]+|[0-9]+\\.[0-9]*)([eE][-+]?[0-9]+)?"
		
		RegEx_Original = [-+]?([0-9]*\.?[0-9]+)([eE][-+]?[0-9]+)? 
		
```



some other solution is great:
###finite automata####
![finite automata](http://media-cache-ak0.pinimg.com/originals/cd/89/89/cd89899071fb72e22bc820d620063598.jpg)

[solution 1](http://www.cnblogs.com/chasuner/p/validNumber.html)
[solution 2](http://www.cnblogs.com/midnightcat/p/3364431.html)