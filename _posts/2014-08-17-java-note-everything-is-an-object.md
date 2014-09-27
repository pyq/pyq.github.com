---
layout: post
title: "Java Note Everything is an Object"
description: ""
category: "Java"
tags: [java, object]
---
{% include JB/setup %}
#Everything is an object Note
1. object reference is on the stack, the pointed object is on heap 
2. primitive types are placed on the stack (more efficient)  
| Primitive type | Size | Minimum | Maximum | Wrapper type|  
|----------------|------|---------|---------|-------------|  











//: object/Documentation1.java

#exercise solution

```
public class EverythingIsAnObject {
	private int i;
	private char c;
	
	public void printDefaultValue() {
			System.out.println("field int i default value is " + i+"!");
			System.out.println("field char c default value is" + c +"!");
			System.out.println(c == '\u0000');
	}
	
	
	public static void main (String[] args) {
		EverythingIsAnObject ob = new EverythingIsAnObject();
		//excersise 1
		//output should be: 0, null'\u0000'
		ob.printDefaultValue();
		//excersise 2: trivial hello world javac xxx.java java xxx
		//local i can't use cause not initialized(dislike c++ local i override field i)
		//int i;
		//System.out.println("local i" + i);
		
	}

}

class StaticTest {
           static int i = 47;
}
public class Incrementable {
	static void increment() {
		StaticTest.i++;
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Incrementable sf = new Incrementable();
		sf.increment();
		Incrementable.increment();
		increment(); // cause in the Incrementable class already in that class when execute main()
		//You can call increment( ) by itself, because a static method (main( ), in this case) can call another static method without qualification.
		
		System.out.println(StaticTest.i);
		
		System.getProperties().list(System.out);
	    System.out.println(System.getProperty("user.name"));
	    System.out.println(
	    System.getProperty("java.library.path"));
	}

}
```