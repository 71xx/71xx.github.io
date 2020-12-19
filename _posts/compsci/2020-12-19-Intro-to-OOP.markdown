---
layout: single
title:  "Introduction to OOP"
date:   2020-12-19 14:00:23 +0100
categories: compsci
tags: code
excerpt: Introduction to OOP and Object Oriented Concepts using Java Examples
---

# Java Files

## Classes

{% highlight java linenos %}

// A class is a blueprint for an object, such as the scanner object
// A class has variable and methods
// OOP is essentially about objects with variables and methods

public class Example1 extends Example2 {
  // OOP Concept 2 - Inheritance
  // Inheritance means that all the functions of a `super` class can be used by a class that inherits it.
  // Super class, is the parent class, in this case, `Example2` and a sub-class is the class that is extending the super class, `Example1`
  
  
  // OOP Concept 1 - Polymorphism
  // Means that you can have multiple methods with the same name and different parameters
  
  String name;
  
  public void sayName() {
    System.out.println("My name!");
  }
  
  public void sayName(String name) {
    System.out.println("My name is " + name);
  }
  
  // This also means that you can override other methods by using those from a different class
  public void sayHi() {
  }
  
  
  // OOP Concept 3 - Encapsulation 
  
  String flavour;
  // Access modifiers, private means that only objects with direct inheritance can access this String object
  public String flavour1; 
  private String flavour2;
  
  
  public void openBag() {
    System.out.println("Bag is open");
  }
  
  // This kind of method is called a setter and it allows us to access a private variable by using a public method 
  public void setFlavour(String newFlavour) { 
    flavour2 = newFlavour;
  }
  
  // This method is a getter and allows us to read data from a private object,using a public method
  public String getFlavour() {
    return flavour2;
  }
  
  
  // OOP Concept 4 - Abstraction
  // Essentially means that only the important parts of a program are visible to a user / programmer and the rest is hidden
  // Focusing only on the important parts
  
  
  public static void main(String[] args) {
    Example1 e1 = new Example1(); // Creating an object of the Example 1 class
    e1.sayHi(); //The reason we can use the `sayHi` method is because we told out class to extend from Example2, which contains the sayHi method
    
    
    // This is an example of encapsulation because it means that we can set and get the flavour without directly accessing a private object
    e1.setFlavour("Beef");
    System.out.println(e1.getFlavour());
  } 
  
}


{% endhighlight %}



{% highlight java linenos %}


public class Example2 implements Example3 {
  // To use methods and variables from interfaces we need to use the `inherits` keyword
  
  public void sayHi() {
    System.out.println("Say hi");
  }

  @Override
  public void openBag() {
    // TODO Auto-generated method stub
    System.out.println("Bag opened");
  }
  
  public static void main(String[] args) {
    Example2 e2 = new Example2();
    e2.openBag(); // Calling our method that was declared in the interface
  }
  
}


{% endhighlight %}


## Interfaces

{% highlight java linenos %}


// An interface is a list of variables and methods
// useful as they can be like blueprints for creating classes with similar methods and functions.

// Abstraction - The interface is completely abstracted as doesn't say how methods are implemented (shows the code)

public interface Example3 {
  
  final String flavour = "Beef";
  
  
  void openBag();
  
  
}


{% endhighlight %}


# Concepts to Remember

 * Classes are blueprints for objects
 * Objects can represent real-world objects, using variables and methods
 * Methods can have the same name using `polymorphism`, but using different parameters
 * You can bring methods and variables from other classes by `inheriting` them in the class declaration
 * You can take a list of variables and methods, an interface, and implement them using the `implements` keyword
 * You can also have access to private variables by having methods to access and change them, these are called setters and getters, this is known as `encapsulation`

# Definitions

 * **Abstraction**. Abstraction means using simple things to represent complexity. We all know how to turn the TV on, but we don’t need to know how it works in order to enjoy it. In Java, abstraction means simple things like objects, classes, and variables represent more complex underlying code and data. This is important because it lets avoid repeating the same work multiple times.
 * **Encapsulation**. This is the practice of keeping fields within a class private, then providing access to them via public methods. It’s a protective barrier that keeps the data and code safe within the class itself. This way, we can re-use objects like code components or variables without allowing open access to the data system-wide.
 * **Inheritance**. This is a special feature of Object Oriented Programming in Java. It lets programmers create new classes that share some of the attributes of existing classes. This lets us build on previous work without reinventing the wheel.
 * **Polymorphism**. This Java OOP concept lets programmers use the same word to mean different things in different contexts. One form of polymorphism in Java is method overloading. That’s when different meanings are implied by the code itself. The other form is method overriding. That’s when the different meanings are implied by the values of the supplied variables. See more on this below.