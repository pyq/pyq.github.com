---
layout: post
title: "java inheritance and polymorphism"
description: "inheritance and polymorphism"
category: "java"
tags: [java]
---
{% include JB/setup %}
##rules for overriding
1. arguments must be the same, and return types must be compatible.  
	(whatever the superclass declares as a return type, the overriding method must declare either the **same type** or a **subclass type**)
2. the method can't be less accessible.

##Overloading a method
1. the return type can be different.
2. you can't change only the return type.  
	(to overload a method, you MUST change the argument list, although you can change the return type to anything)
3. You can vary the access levels in any direction.


#inheritance
###If class B extends A, B class **IS-A** class A  
###This is true anywhere in the inheritance tree. IF class C extends B, C passes the **IS-A** test for Both B and A.