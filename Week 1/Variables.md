Variables allow you to store data about your program. You can use them in place of a number or String or anything else.\
The most important types to know are:
- Integers: `int` (Ranges from ±2.147 billion)
- Decimal numbers: `double`/`float` (see more, usually use `double`)
- Strings: `String`

Create variables by first specifying the type and the name:

```java
double gearRatio;
int motorID;
String robotName;
```
Before the variable has a value it has a default value of `null`;
\
Specify the values with `=` with the variable name on the left, and the value on the right:

```
double gearRatio = 5/3;
int motorID = 20;
String robotName = "Donatello";
motorID = 30; //changes the value of motorID to 30
```
\
You can use variables the same way you would use any other values:

```java
String robotName = "Donatello";
System.out.println("You can use variables here");
System.out.println(robotName);

if (robotName.length() > 5) {...}
```
\
You can change a variable using `=` again:
```java
int distanceMoved = 0;
System.out.println("I moved " + distanceMoved + " meters");
//I moved 0 meters

distanceMoved = 5;
System.out.println("I moved " + distanceMoved + " meters");
//I moved 5 meters
```
\
It is important to remember that you CANNOT change a variables type. When you create a variable you cannot change the type.
```
double movementSpeed = 1.0; // This is a decimal number
movementSpeed = "2.0"; // This does not work because "2" is a String instead, use 2.0;
```
\
What's the deal with Doubles and Floats
---
Computers are not perfect. They cannot express every number perfectly. The same way that we cannot perfecly represent every fraction as a decimal (eg 1/3 ≈ 0.3333), computers have to cut off a decimal after a certain length. Doubles and floats (floating pint numbers) are good enough for us and we most likely won't run into a problem with them. The important thing to remember here is that **doubles are more accurate than floats**

Floating point numbers have the property that the closer the number is to zero the more accurate the number is and the farther it is the less accurate it is. At extremely high values it is less accurate and can even skip over some numbers.

Example:
```java
System.out.println(0.1 + 0.2);
// 0.30000000000000004
```
More: [Floating Point Weirdness](https://0.30000000000000004.com/)

More Types
---
The three most important types are `int`, `double`s and `String`s but there are several more built-in types although we rarely use them. 

There are eight "basic" types called primitives and they are:
- `int`: represents an integer between -2,147,483,648, and 2,147,483,647 (2^31)
- `long`: represents an integer between -9,223,372,036,854,775,808, and 9,223,372,036,854,775,807 (2^63)
- `short`: represents an integer between -32768, and 32767 (2^15)
- `byte`: a single byte in memeory, an integer between -128 and 127 (2^7)
- `float`: a 32 bit floating point number (see above)
- `double`: a 64 bit floating point number (see above)
- `char`: a character ('A', ':', '$'), not a String but only a single character, denoted with `'`
- `bool`: a true or false value

Technically a `String` is not a primitive type and is a "reference type", there are five reference types which are:
- Strings: A list of `char`s, denoted with `""`
- Arrays: A list of another type, denoted with `[]` when initializing a variable or `{}` when setting a variable (see more)
- Enums: Similar to an Array, all members are public, static, and final
- Classes/Objects: See OOP document, allows you to create your own types, Strings are actually objects
- Interface: maybe i'll make a document for it, DM @fatcactis otherwise. Stores variables and methods required for a class

About Arrays
---
Arrays are a sequence of another type with a specified length for example `int[] array = new int[5]`  creates an array of 5 `int`s. Each thing in an array is called a member or item and its position is called its index. To access the member at a certain index you put its index in the `[]`. 

```java
int[] motorIDs = {1,2,3,4,5};
motorIDs[1]; // get the first member of motorIDs
// returns 2 what happened?
```
Array indices start at 0, meaning that `motorIDs[0]` returns the first item in the array, and `motorIDs[1]` returns the second item, lets try again

```java
int[] motorIDs = {1,2,3,4,5};
motorIDs[0]; //this actually returns the first member
// returns 1
```

You can change array members the same way you would change any other variable
```java
double[] wheelSpeeds = {1.1, 2.3, 4.5, 0.5};
wheelSpeeds[3] = 5.4; // changes the fourth item to 5.4
wheelSpeeds; // {1.1, 2.3, 4.5, 5.4}
```

Arrays have a set size which you cannot change for example this example would fail
```java
String[] robotNames = {"Maurice", "Nessie", "Donatello"};
robotNames[3] = "2025 Robot Name";
//robotNames[3] is out of bounds (indexOutOfBoundsException)
```

# Enum
Enums, short for enumerator, are a special type of variable that can only be one of a few options.

```java
enum DayOfTheWeek {
  MONDAY,
  TUESDAY,
  WEDNESDAY,
  THURSDAY,
  FRIDAY,
  SATURDAY,
  SUNDAY
}

DayOfTheWeek today = DayOfTheWeek.THURSDAY;
```

Enums in java have other special properties similar to a class. They can have variables and constructors.

```java
enum Color {
  RED(1., 0., 0.),
  YELLOW(1., 1., 0.),
  GREEN(0., 1., 0.),
  CYAN(0., 1., 1.),
  BLUE(0., 0., 1.),
  PURPLE(1., 0., 1.),
  BLACK(0., 0., 0.),
  GRAY(.5, .5, .5),
  WHITE(1., 1., 1.)

  final double red;
  final double green;
  final double blue;

  Color(double r, double g, double b) {
    this.red = r;
    this.green = g;
    this.blue = b;
  }
}
```
