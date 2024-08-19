Object Oriented Programming is the concept of combining variables into objects. An object can have different properties that you can control. Classes provide the structure of an object. Here is an example Arm class

```java
public class Arm {
  private double rotation;
  private double extension;
  private boolean open;
  // pretend these methods have functionality
  public void openClaw() {}
  public void closeClaw() {}
  public boolean getClaw() {}
  public void goToAngle(double angle) {}
  public double getAngle() {}
  public void goToExtension(double distance) {}
  public double getExtension() {}
  private bool isAngleAllowed(double angle) {}
  private bool isExtensionAllowed(double distance) {}
}
```

You can create an arm object and control it using this class. An object is created, or *instantiated*, using the keyword `new`. The type of the variable is the name of the class.

```java
Arm arm = new Arm();
arm.openClaw();
double targetDistance = 10;
arm.goToExtension(targetDistance);
arm.goToRotation(15.0);
```

# Static variables and methods

You may want to run code from another class without relying on using an object for it. You can use `static` variables and methods for it. Something that is `static` can be run directly from the class. We have used it in the form of the Math class. things like `Math.sqrt`, `Math.pow`, and `Math.PI` are static methods and variables in the class `Math`. Static methods and variables are not included when you instantiate them.

```java
public class Color{
  double red;
  double green;
  double blue;

  public static final Color WHITE = new Color(1.0, 1.0, 1.0);
  public static final Color RED = new Color(1.0, 0.0, 0.0);
  public static final Color BLUE = new Color(0.0, 1.0, 0.0);
  public static final Color GREEN = new Color(0.0, 0.0, 1.0);
  public static final Color BLACK = new Color(0.0, 0.0, 0.0);
  public static add(Color c1, Color c2) {}
  public static mix(Color c1, Color c2) {}
  public static invert(Color c1) {}

  public double getHue() {}
  public double getSaturation() {}
  public double getLightness() {}

  public Color(double r, double g, double b) {
    this.red = r;
    this.green = g;
    this.blue = b;
  }
}
```

With this we can use `Color.add` to add to colors, `Color.mix` to mix two colors and `Color.invert` to invert a color. We can also use `Color.WHITE` to get the color white as well as the other colors. Due to a weird quirk of Java, enums are always static. There is also a method that doesn't have a name, it is called a *contructor*. The constructor is a method that runs when an object is created. You can also give it parameters which are passed in when you create it, `new Color(1.0, 1.0, 0.0)` would create yellow. We can do anything in the constructor just like another method.

```java
public class LEDs {
  Color[] colors;
  int currentColor = 0;

  public LEDs(Color[] colors) {
    System.out.println("LEDs are created with colors: " + colors);
    this.colors = colors;
  }

  public void setColor(int c) {
    currentColor = c;
  }
}
```

# Access modifiers

You may have also noticed the use of `public` and `private`. These determine where certain code is accessible. `private` means that something can only be accessed within its class while `public` means something can be accessed from anywhere. Generally you want to keep variables `private` unless necesarry.

```java
public String username = "Admin";
private String password = "supersecretadminpassword";
```

Even regular methods or variables we keep private as long as another class doesn't rely on it. For example in a Drivetrain class the motors would be private because other classes will never access the motors directly. Instead there might be a `goToPosition()` or `goToRotation()` method in the Drivetrain class which controls the motors from there.

```java
public class Drivetrain {
  private SwerveModule frontLeftModule;
  private SwerveModule frontRightModule;
  ...

  public void goToPosition(Vector2 pos) {/*Moves the robot to given position*/}
}

public class Main {
  public static void main(String[] args) {
    Drivetrain drive = new Drivetrain();
    drive.goToPosition(new Vector2(4.5, 3.8)); // Drives the robot to 4.5 meters and 3.8 meters
    drive.fontLeftModule = new SwerveModule; // Not allowed, drive.frontLeftModule is private
  }
}
```

# Getters and Setters

Sometimes you may need to access a private variable but *not* change it, or getting a variable may need more information. You can use a getter for that. The same is true for setting a variable although if you need to you often also need to get it and you might as well make it public then. In either case a getter or setter would be used. Simply, getters just return a variable and are usually public.

```java
public class Color {
  private double r;
  private double g;
  private double b;

  public getR() {}
  public getG() {}
  public getB() {} 
}
```

# Passing by value or by reference

When you pass a variable into a method parameter some variables are passed by *value* and some are passed by *reference*. Changing the parameter when you pass by value will not affect the original variable while passing by reference will. All primitive types (int, double, boolean) are passed by value, while objects are passed by reference. For example:

```java
void increment(int x) {
  x++;
}

int a = 5;
increment(a); // a = 5, a is not changed despite running x++, it is passed by value.


void invertColor(Color c) {
  c.invert();
}

Color red = new Color(1.0, 0.0, 0.0);
invertColor(red); // red is inverted, it is passed by reference
```
