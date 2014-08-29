---
layout: post
title: "Java Note Interfaces"
description: "Interfaces"
category: "java"
tags: [java]
---
{% include JB/setup %}
#Interfaces

1. abstract method: is incomplete, it has only a declaration and no method body.
2. A class containing abstract methods is called an abstract class. (it is possibe to make a class **abstract** without including any abstract metthods. so you can't get instance of that class)
3. derived a abstract class would also be a abstract class.
4. the **interface** keyword produces a completely abstract class, one that provides no implementation at all. (an interface provides only a form but no implementation).
5. an interface can also contain fields, but these are implicitly static and final.
6. methos in an interface as public (implicity), so implement an interface, the methods form must be defined as public.
7. for upcasting, it doesn't matter if you are upcasting to a regular class or an abstract class or an interface. All are ok!!
8. Complete decoupling... 
9. interface has no implementation at all, so no storage associated with an interface. (fields are not part of the interface, the values are stored in the static area)
10. when combine a concrete class with interfaces , the concrete class must extends first then implement interfaces(get error otherwise)
11. Normally, you can use extends with only a single class, but extends can refer to multiple base interfaces when building a new interface.
12. Reminder: overloaded methods cannot differ only by return type.
13. a method that takes an interface (as args) provides a way for any class to be adapted to work with that method.
14. fields defined in interfaces cannot be "blank finals", but can be initialized with non-constant expressions.
15. nesting interfaces, holy shit...
16. facotry method design pattern: isolated the implementation of the interface. don't need to  specify exact type of derived class type. see following code.

```
package interfaces;

interface Cycle {
	int wheels();
}

interface CycleFactory {
	Cycle getCycle();
}

class Unicycle implements Cycle {
	public int wheels() {
		return 1;
	}
}

class UnicycleFactory implements CycleFactory {
	public Unicycle getCycle() {
		return new Unicycle();
	}
}

class Bicycle implements Cycle {
	public int wheels() {
		return 2;
	}
}

class BicycleFactory implements CycleFactory {
	public Bicycle getCycle() {
		return new Bicycle();
	}
}

class Tricycle implements Cycle {
	public int wheels() {
		return 3;
	}
}

class TricycleFactory implements CycleFactory {
	public Tricycle getCycle() {
		return new Tricycle();
	}

}

public class E18_CycleFactories {
	public static void ride(CycleFactory fact) {
		Cycle c = fact.getCycle();
		System.out.println("Num. of wheels: " + c.wheels());
	}

	public static void main(String[] args) {
		ride(new UnicycleFactory());
		ride(new BicycleFactory());
		ride(new TricycleFactory());
	}
} /*
 * Output: Num. of wheels: 1 Num. of wheels: 2 Num. of wheels: 3
 */// :~           
```
17
. an appropriate guildeline is to prefer classes to interfaces, start with classes, and if it becomes clear that interfaces are necessary, then refactor.(don't overuse interface)
