---
layout: post
title: "java constructor and object"
description: "constructor and memory"
category: "Java"
tags: [Java]
---
{% include JB/setup %}
##instance variable && local variable
**instance variable** are declared inside a class but not inside a method, like XXX.instance variable. (heap)  
**local variable** are declared inside a method, including method parameters. (stack)

*if you put a constructor -any constructor- in your class, the compiler will not build the default constructor.  
then if you want a no-arg constructor, and you've already put in a constructor with arguments, you'll have to build the no-arg constructor yourself.*

Overloaded constructors must have different argument list.(argument list include the order and/or type of arguments)
that means it's ok for following two constructors.

```
public class Mushroom{
	public Mushroom(boolean i, int size){}
	public Mushroom(int size, boolean i){}
}
```

**even abstract classes have construtors**

######every cosntructor can have a call to super() or this, but never both! because either must be the first statement in the constructor!!!!

when you call a new XX(),  xx constructor goes into a stack and invokes the superclass, the superclass will be finished first, because **super()**!!