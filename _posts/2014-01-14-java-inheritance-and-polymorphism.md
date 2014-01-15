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
If class B extends A, B class **IS-A** class A  
This is true anywhere in the inheritance tree. IF class C extends B, C passes the **IS-A** test for Both B and A.

#polymorphism
**the reference type can be a superclass of the actual object type && u can have polymorphic arguments and return types**  
for example: Animal d = new Dog();

#####u can't instantiate and **abstract** class

an abstract class contains abstact methods + (concrete methods), in other words, if u put even a single **abstract** method in a class, you have to make the class abstract.

#####remember, you cannot make a new instance of an abstract type, but you can make an array object declared to hold that type.  
(like, **private Animal[] animals = new Animal[5];  cannot do Animal a = new Animal();**  
 because Animal class is abstract)

#####you can call a method on an object reference only if the class of the **reference type** actually has the method.
in other words, ￼The compiler decides whether you can call a method based on the reference type, not the actual object type.

cast with **instanceof** would be great

##interface
a java interface is like a 100% pure abstract class.(make all the methods abstract! so the subclass must implement the methods.)

interface method are implicitly public and abstract