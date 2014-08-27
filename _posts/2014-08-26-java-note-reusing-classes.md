---
layout: post
title: "Java Note Reusing Classes"
description: "Reusing Classes"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Reusing Classes
1. Composition: has-a relationship.   inheritance : is-a relationship.
2. you can create a main() for each one of your classes.
3. when create an object of the derived class, it contains within it a *subobject* of the base class. the subobject of the base class is wrapped within the derived-class object.
4. Java atuomatically inserts calls to the base-class constructor in the derived-class constructor.(super() ). construction happens from the base "**outward**" (root -> most-derived)
5. Delegation: not inheritation relationship, so add the "base class" as a member to get its methods.
6. **finally** clause is always executed.
7. unlike c++, the derived class with same method name (but not same args list), is a new overloaded method.   we can use **@Override** to test override method. (error if overload not override).
8. Upcasting is always safe (derived class is a superset of the base class, has all methods in the base class).  **the real method is based on the object type not the reference type.**
#### final 

final data: 1 it can be a compile-time constant that won't ever change. 2 it can be a value initialized at tun time that you don't want changed.

a field that is both **static** and **final** has only one piece of storage that cannot be changed.

final primitive: value constant.  final object reference: makes the *reference* a constant. object it self can be modified.

Static: only one.
final doesn't mean that its calue is known at compile time.
blank final must be initialized before it is used.


final argument is primarily used to pass data to anonymous inner classes.


final method: 1 prevent any inheriting class from changing. 2 efficiency. (actually only consider preventing overiding.)

private method is implicitl final.

######final class just means the methods are final, the fields in that class can be final or not.

class code is loaded at the point of first use.

the constuctor is also a static method even though the static keyword is not explicit.

**If the base class has a base class, that second base class would then be loaded, and so on. Next, the static initialization in the root base class (in this case, Insect) is performed, and then the next derived class, and so on. **   (load from derive to root, initial from root to derive)

Loading the class initializes the static variables. The base class loads first, then the next-derived class, and finally the most-derived class. This creates the object and initializes the non-static members, also starting at the root class. (only say about initial order)

loading may be caused by either the creation of the first instance of that class or by the access of a static member. (main method static!!!)