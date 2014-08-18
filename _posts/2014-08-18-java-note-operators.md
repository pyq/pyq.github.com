---
layout: post
title: "Java Note Operators"
description: ""
category: "java operators"
tags: [java]
---
{% include JB/setup %}
#Operators
1. side effect: means change the value of an operand

2. Almost all operators work only with primitives. The exceptions are ‘=‘, ‘==‘ and ‘!=‘, which work with all objects (and are a point of confusion for objects). In addition, the String class supports ‘+’ and ‘+=‘.

3. +: a string followed by '+' foolowed by a non-String, it attempts to convert the non-S to String

4. lvalue must be a distinct, named variable(there must be a phsical space to store the value.)

5. primitive holds the actual value, for object, hold a reference.

6. boolean only work with == and != in all relational operators

7. \== and \!= operators, which compare references, and equals( ), which actually compares content.

8. short-circuiting: the expresiion will be evaluated only until the truth or falsehood of the entire expression can be unamigiguously determined. (that's to say a&&b, if a is false, don't check b at all)

9. e in java emans '10 to the power' not the natural logarithms

10. Bitwise operator: AND& OR| XOR^   
	\>> (signed right shift): if value is positive, zeroes are inserted at higher-order bits, negative will be inserted 1  
	\>>> (unsigned right shift):  regardless of the sign, insert zeros 000
	
11. class types do not allow casting ???

12. Truncation and rounding: double and float to an integer always truncates the number

13. Ingeral, largest data type in an expression determines the size of the result. (float + double , the result will be double)

##Two usefull code

**equals and ==**

```
class Dog{
	int x;
	Dog(int n){
		x = n;
	}
}
class Cat{
	int y;
	Cat(int n){
		y = n;
	}
	public boolean equals(Cat c2) {
		return y == c2.y;
	}
}

public class EqualsAndDengdeng {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Dog d1 = new Dog(1);
		Dog d2 = new Dog(1);
		System.out.println("d1 == d2 is " + (d1 == d2));
		System.out.println("d1.equals(d2) is " + d1.equals(d2));
		//output cause default equals also just compare reference, should override
		//d1 == d2 is false
		//d1.equals(d2) is false

		
		Cat c1 = new Cat(1);
		Cat c2 = new Cat(1);
		System.out.println("c1 == c2 is " + (c1 == c2)); 
		System.out.println("c1.equals(c2) is " + c1.equals(c2));
		//output
		//c1 == c2 is false //compare reference
		//c1.equals(c2) is true //compare content yes!
		
		//!System.out.println(1 || 2); invalid also for && and !
		
		
	}

}

```

**-1shift test**

```

public class ShiftTest {
	public static void main(String[] args) {
		//The binary representation of the numbers is referred to as signed twos complement.
		//-1 [10000001]yuan = [11111110]fan = [11111111]bu
	    int i = -1;
	    System.out.println(Integer.toBinaryString(i));
	    //11111111111111111111111111111111 32 1 complement
	    i >>>= 10;
	    System.out.println(Integer.toBinaryString(i));
	    //1111111111111111111111  >>>zero extension
	    long l = -1;
	    System.out.println(Long.toBinaryString(l));
	    //1111111111111111111111111111111111111111111111111111111111111111 64 1
	    l >>>= 10;
	    System.out.println(Long.toBinaryString(l));
	    //111111111111111111111111111111111111111111111111111111
	    // short and byte would be wrong cause after shit it will truncate back not enough bits
	    short s = -1;
	    System.out.println(Integer.toBinaryString(s));
	    //11111111111111111111111111111111 convert to int first
	    s >>>= 10;
	    System.out.println(Integer.toBinaryString(s));
	    //11111111111111111111111111111111
	    byte b = -1;
	    System.out.println(Integer.toBinaryString(b));
	    //11111111111111111111111111111111
	    b >>>= 10;
	    System.out.println(Integer.toBinaryString(b));
	    //11111111111111111111111111111111
	    b = -1;
	    System.out.println(Integer.toBinaryString(b));
	    //11111111111111111111111111111111
	    System.out.println(Integer.toBinaryString(b>>>10)); //here is right cause not assign back to b but printed directly
	    //1111111111111111111111
	}
}

```