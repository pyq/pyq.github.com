---
layout: post
title: "Java Note Polymorphism"
description: "polymorphism"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Polymorphism

1. dynamic binging or late binding or run-time binding: used in upcasting - taking an object reference and treating it as a reference to its base type.
2. late binding means the binding occurs at run time, based on the type of object. (not reference type)
3. all method binding in Java uses late binding unless the method is **static** or **final**(private are implicitly final).
4. pitfall: **overriding private methods**

```
//: polymorphism/PrivateOverride.java// Trying to override a private method.package polymorphism;import static net.mindview.util.Print.*;public class PrivateOverride {  private void f() { print("private f()"); }  public static void main(String[] args) {    PrivateOverride po = new Derived();po.f(); }}class Derived extends PrivateOverride {  public void f() { print("public f()"); }} /* Output:private f()*///:~
```

Derived's f() is a brand new method, not overloaded or override method of base class.

> only non-private method may be overriden.


5. sub object is upcast to a super reference, any field accesses are resolved by the compiler, (that's to say based on reference type )not polymorphic. also the static methods are associated with the class, not the individual objects, that's to say based on the reference type.
 

###the order of constuctor calls for a complex object:(not include static field initialization sth)
1. The base-class constructor is called.This step is repeated recursively such that the root of the hierarchy is constructed first, followed by the next-derived class, etc., until the most-derived class is reached.
2. Member initializers are called in the order of declaration.
3. The body of the derived-class constructor is called.  


the order of disposal should be the reverse of the order of initialization. you should perform the derived-cass cleanup first, then the base-class cleanup.

for polymorphic methods inside constuctors, even thought the derived constructor is not finished, it will called the overriden method in the constructor, but the value of field in the method might be 0, not default set value. (polymorphism calls the most-derived method, even before completely initializing the object)

Covariant return type: means that an overridden method in a derived class can return a type derived from the type returned by the base-class method: (that's say use derived type instead of based type for the return type)

Design with Inheritance or composition? a better approach is to chooes composition first, when not sure or obvious.

>A general guideline is “Use inheritance to express differences in behavior, and fields to express variations in state

pure substitution, perfect substituted.  is-like-a relationship: has same fundamental interface but has other features.

Downcasting: in java every cast is checked. (RTTI runtime type identification)

Java always uses the most-derived method for the object type

 