---
layout: post
title: "Java Note Introduction to Objects"
description: "Introduction to objects"
category: "Java"
tags: [java]
---
{% include JB/setup %}
#Introduction to java
1. Programming in a object thinking helps to improve the cohesiveness of the object. (high cohesion)

2. Class:  access control hides the implementation reduces program bugs from corruption by a careless or uninformed client programmer.  
	**private**: no one can access that element except you, **the creator of the type **  
	**protected**: acts like private, with the exception that an inheriting class has access to **protected** memeber, but not **private** members:
(default access : package access)

3. Reusing the implementation: compositon(has a )  interface (islike a relationship)

4. The compliler does ensure that the method exists and performs type checking on the arguments and return value, but it doesn't know the exact code to execute.(late binding)

```
void doSomething(Shape shape) {  shape.erase();  // ...  shape.draw();}

Circle circle = new Circle();Triangle triangle = new Triangle();Line line= new Line();doSomething(circle);doSomething(triangle);doSomething(line);	
//do something base on circle.```
5. objects are created on the heap. (? primitive type on stack?)
6. everything is an object, container holds objects can hold anything
7. upcasting (safe! like circle is a type of shape) & downcasting (unsafe so have parameterized type)