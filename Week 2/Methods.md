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
