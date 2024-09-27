When you run a program a terminal will appear in the bottom. You can use the terminal to display information about the program. The simplest way of doing so is called printing (this does not use an actual printer). We use `System.out.println();`. Anything you put inside will be written in the console

```java
System.out.println("This will show in the console!")
System.out.println("Hello World!");
System.out.println("Use \n
                    for multiple lines");
```

As you can see, every message is surrounded by quotation marks `""`. This basically tells the computer that it is a message or "String".\
You can combine strings using `+` called "concatenation".

```java
System.out.println("You can " + "combine messages!");
//You can combine messages!
```

Or you can print math equations (We'll go more in depth later), math equations are not put in quotations or it will not calculuate it. You can combine numbers with strings

```java
System.out.println(1 + 4 * 7 - 6 / (3 * 6));
System.out.println("1 + 4 * 7 - 6 / (3 * 6)");
//28.666667
//1 + 4 * 7 - 6 / (3 * 6)

System.out.println(1 + 5 + " <- this should be 6");
//6 <- this should be 6
```

Helpful Tips
---
VSCode can autocomplete by typing `sout` and pressing tab
