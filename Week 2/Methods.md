(This is expanded upon in Week 3, all info will be on this document)

Methods allow you to condense code into a repeatable list of instructions. Take this code for example.
```java
public static void main(String[] args) {
  //move forward
  frontLeftMotor.set(0.6);
  backLeftMotor.set(0.6);
  frontRightMotor.set(0.6);
  backRightMotor.set(0.6);

  //move back
  frontLeftMotor.set(-0.6);
  backLeftMotor.set(-0.6);
  frontRightMotor.set(-0.6);
  backRightMotor.set(-0.6);
}
```

Here, every time we want to move the robot we have to set each motor individually. We can write a method that moves all of the motors at once. To write a method we start with `public static void` (we'll go in depth on this later), the name of the method with parentheses after and then put the code in curly brackets.

```java
public static void main(String[] args) {
  moveForward();
  moveBackwards();
}

public static void moveForward() {
  frontLeftMotor.set(0.6);
  backLeftMotor.set(0.6);
  frontRightMotor.set(0.6);
  backRightMotor.set(0.6);
}

public static void moveBackwards() {
  frontLeftMotor.set(-0.6);
  backLeftMotor.set(-0.6);
  frontRightMotor.set(-0.6);
  backRightMotor.set(-0.6);
}
```

Here the movement is a method that we can use anywhere, but we need a seperate method for each speed. We can use parameters to choose our own speeds.
```java
public static void main(String[] args) {
  move(0.6); //move forward
  move(-0.6); //move backwards
}

public static void move(double speed) {
  frontLeftMotor.set(speed);
  backLeftMotor.set(speed);
  frontRightMotor.set(speed);
  backRightMotor.set(speed);
}
```

Now we can move at any speed whenever we want.

Return
---
Methods can do more than condense code. They can take the place of variables. For example if you have a method that calculates the distance to a target the method would *return* the distance. To make a method return something you change `void` to the type that it returns, `void` just means no type:

```java
public static double distanceToPoint(double x, double y) {
  double distance = Math.sqrt((x * x) + (y * y)); //distance formula
  return distance;
}

public static void main(String[] args) {
  System.out.println("Distance to (5, 12): " + distaanceToPoint(5.0, 12.0))
}
```

###Everything after this point is not taught until Week 3

Getters and Setters
---

Getters and Setters allow your code to be more readable and allows you to make changes without the risk of breaking something. If you have a public variable then everything can both read and change it. Getters allow you to make a variable private but still access it without allowing you to change it. This way things you won't accidentally change an important part of the robot.
```java
class RobotContainer {
  private static Arm m_arm;

  public static Arm getArm() {
    return m_arm;
  }
}
```

`m_arm` is private so you cannot use `RobotContainer.m_arm`. If it was you could accidentally change `m_arm` with `RobotContainer.m_arm = new Arm();`. With a getter you can only access it with `RobotContainer.getArm()`. Setters are similar but used less often. They let you set a value without needing to know its value.

```java
private double targetRotation = 2 * Math.PI;

public void setTargetRotation(double degrees) {
  targetRotation = Math.toRadians(degrees);
}
```

They are also often used together to make it more readable.

# Method Overloading

Overloading is when a method can do two different things depending on the types provided. This is done with a method being defined twice with two different types of parameters. For example if you want a method that can take in a String, *or* a number this can be done using an overload.

```java
public double getNumber(String s) {
  return Double.parseDouble(s);
}

public double getNumber(char c) {
  return (double) c - '0'; //trust me this works;
}

void main() {
  System.out.println(getNumber("3.6")); // getNumber takes a String
  System.out.println(getNumber('4')); // getNumber takes a char
}
```
