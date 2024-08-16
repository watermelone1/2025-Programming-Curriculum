Object Oriented Design has three main patterns it follows:

- Encapsulation
- Inheritance
- Polymorphism

# Encapsulation

Encapsulation is the idea that any information about an object should be defined inside of its class. For example something could tell the intake to do something without worrying at all about how it does it. If you tell the arm to move up you shouldn't care how the robot calculates how to get to a position as long as it does it.

# Inheritance

Inheritance is the idea that a class can *extend* another. When a class extends anoter class it copies the parent class but can override and add to its code. For example there might be a `Light` class with methods `turnOn` and `turnOff` but you might also have an `LEDs` class that extends the `Light` class. The LEDs can have `setColor` but still use `turnOn` and `turnOff` without rewriting it.

```java
public class Shape {
  String name;
  public void getArea();
}

public class Square extends Quadrilateral {
  double sideLength;
  public void getArea() {return sideLength * sideLength}
}

public class Quadrilateral extends Shape {
  final int numberOfSides = 4;
}
```

Here, the `Square` extends `Quadrilateral` which extends `Shape`. Quadrilaterals can still use `name` and `getArea()`, but also have `numberOfSides` equal to 4. Squares inherit `numberOfSides` and `name` but also override `getArea()`.

There is another access modifier called `protected` this means that something can only be modified in a child class or overridden.

# Polymorphism

Polymorphism is the idea that it doesn't matter if a class is a child or not as long as it has the same methods and variables (always the case in Java). You can pass a child type in when a parameter requires a parent type. For example take these Animal classes:

```java
public class Animal {
  String sound;
}

public class Cow extends Animal {
  String sound = "Mooo";
}

public class Sheep extends Animal {
  String sound = "Baaah";
}
```

Something can use an Animal and any of these can be passed in.

```java
public void makeSound(Animal animal) {
  System.out.println(animal.sound);
}

makeSound(new Animal()); // nothing, Animal.sound is unset
makeSound(new Cow()); // Mooo
makeSound(new Sheep()); // Baaah
```
