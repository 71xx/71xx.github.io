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