---
layout: post
title: When should switch be used instead of if else statements?
author: [Mirnes Hasanovic]
category: [Example]
tags: [switch, if-else]
---

Whenever you have **more than 2 conditions** on a **single** variable it would be good to use **switch** statement. 
Otherwise, stick with multiple if-else statements.

Let's take weekdays for example. 

(*An example will be in Java, but you can use it in any other programming language.*)

{% highlight java %}
int day = 4;
switch (day) {
  case 1:
    System.out.println("Monday");
    break;
  case 2:
    System.out.println("Tuesday");
    break;
  case 3:
    System.out.println("Wednesday");
    break;
  case 4:
    System.out.println("Thursday");
    break;
  case 5:
    System.out.println("Friday");
    break;
}
// Outputs "Thursday" (day 4)

{% endhighlight %}