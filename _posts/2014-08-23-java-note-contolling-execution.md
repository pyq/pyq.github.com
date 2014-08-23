---
layout: post
title: "Java Note Contolling Execution"
description: "java note"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Controlling Execution
1.
```
if
(Boolean-expression)
	statement  // simple statement or compound satement
//else
	statement	
```

2.
```
for(initialization; boolean-expression; step)
//the loop perform initialization before the first iteration, then perform conditional testing
//the boolean expression is tested before each iteration
//at the endo of each loop, the step executes
```

3. comma separator, which is used to separate definitions and method arguments.  
comma operator has only use in Java: in the control expression of a for loop. In both the initializtion and step portion of the control expression, you can have a number of statements sperated by commas.those statements will be evaluated sequentially. (sperate function)

4.foreach will work with any object that is **Iterable**.  
5. there is an implicit return at the end of method which returns void.  
6. Java "Goto": 

```
lable1:
outer-iteration{
	lable2:
	inner-iteration{
	}
}
//1. A plain continue goes to the top of the innermost loop and continues.//2. Alabeledcontinuegoestothelabelandreentersthelooprightafterthatlabel.//3. Abreak“dropsoutofthebottom”oftheloop.//4. Alabeledbreakdropsoutofthebottomoftheendoftheloopdenotedbythelabel.
```	
7.
**Swith**

*for switch without break, when the first matches, it will execute the next case
because after executing first statements command will be transfered to next statements.*

```
    public static void main(String[] args) {
    	  for(int i = 0; i < 7; i++)
    		  switch(i) {
              case 1: 
              case 2: 
              case 3: 
            	  System.out.println("case "+i);
                     // break;
              case 4: 
            	  System.out.println("case 4");
                    //  break;
              case 5: 
            	  System.out.println("case 5");
                     // break;
              default: 
            	  System.out.println("default");
            }
    	for(int i = 0; i < 7; i++)
            switch(i) {
              case 1: System.out.println("case 1"); break;
              case 2: System.out.println("case 2"); break;
              case 3: System.out.println("case 3"); break;
              case 4: System.out.println("case 4"); break;
              case 5: System.out.println("case 5"); break;
              default: System.out.println("default"); break;
            } 
    }
```
output:
default  
case 1  
case 4  
case 5  
default  
case 2  
case 4  
case 5  
default  
case 3  
case 4  
case 5  
default  
case 4  
case 5  
default  
case 5  
default  
default  
default  
case 1  
case 2  
case 3  
case 4  
case 5  
default  

