---
layout: post
title: Why do we use super keyword in Java?
author: [Mirnes Hasanovic]
category: [Java]
tags: [super, keyword]
---

The **super** keyword in Java is a **reference variable** which is used to refer parent class object.

It will be used in 3 cases:
1. to refer parent class instance variable
2. to invoke parent class method
3. to invoke parent class constructor

Example:

{% highlight java %}
class Animal { // Superclass (parent)
  Animal(int legs, String color) { //constructor
  	System.out.println("Animal is " + color + " and has " + legs + " legs."); 
  }  
  int legs = 2; // variable
  String color = "grey"; // variable
  public void animalSound() { //method
    System.out.println("The animal makes a sound.");
  }
}

class Dog extends Animal { // Subclass (child)
  Dog() { //Subclass constructor
    super(4, "black"); //call the SuperClass constructor
  } 
  public void animalSound() { //Subclass method
    super.animalSound(); // call the SuperClass method
    System.out.println("Number of legs: " + super.legs);// call the SuperClass variable
  }
}

public class Main {
  public static void main(String args[]) {
    Dog myDog = new Dog();
    myDog.animalSound();
  }
}

//Output:
//Animal is black and has 4 legs.
//The animal makes a sound.
//Number of legs: 2
{% endhighlight %}

**Explanation:**

As you can see we have two classes (Animal and Dog), where Dog extends Animal class.
Both classes have the same method **(animalSound())**.

*<u>1. How did we use the parent class variable?</u>*  
{% highlight java %}
System.out.println("Number of legs: " + super.legs);
{% endhighlight %}
We did it by adding **super** keyword to **legs**.

*<u>2. How did we call the parent class method?</u>*
{% highlight java %}
super.animalSound();
{% endhighlight %}
We did it by adding **super** keyword to **animalSound()** method.

*<u>3. How did we use the parent class constructor?</u>*

In the Dog class we have called the constructor from the Animal class and passed **4**  and **black**.
{% highlight java %}
super(4, "black"); //SuperClass constructor
{% endhighlight %}

By passsing **4** and **black** to constructor the output will be:
{% highlight java %}
Animal is black and has 4 legs.
{% endhighlight %}
instead of:
{% highlight java %}
Animal is grey and has 2 legs.
{% endhighlight %}
