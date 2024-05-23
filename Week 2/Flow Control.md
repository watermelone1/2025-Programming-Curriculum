Control flow is used to *control* the *flow* of reading code. It lets you run code only in specific circumstances, loop code, or do something different in different parameters. It is a very broad topic so this will go over three important topics and future lessons will teach others. The three things this will teach are:
- If statements
- Switch statements
- Loops


If
---

If statements are the most simple but first you have to know a new [data type](https://github.com/watermelone1/2025-Programming-Curriculum/blob/main/Week%201/Variables.md#more-types).
Booleans are a data type which have a true or false value and you can use [boolean operations](https://github.com/watermelone1/2025-Programming-Curriculum/blob/main/Week%201/Operators.md#boolean-comparisons) to modify them.

If statements allow you to run a section of code *only if* a value is `true`. To create an if statement you start with `if` and put what to check in brackets `()` and put the code to run in curly brackets `{}` for example

```java
int points = 16;
if (inRange) {
  shootPiece();
  points++;
}
// shoots and scores if you are in range, otherwise dose nothing
```

You can check for multiple requirements using boolean operations.
```java
int points = 17;
if (inRange && atSpeed && !atWrongAngle) {
  shootPiece();
  points++;
}
// shoots and scores if you are in range, at the right speed, and at the right angle
```
You can choose between several sections using `else`, you attach it to the end of an `if` statement and it runs its section of code *only* if its attached section fails.

```java
int points = 17;
if (inRange && atSpeed && !atWrongAngle) {
  shootPiece();
  points++;
} else {
  findNewPiece();
}
// shoot and scores if requirements are met, otherwise finds a new piece to shoot
```

You can attach more `if` statements to the `else` although it is often bad practice.

```java
if () {
  //option 1
} else if () {
  //option 2
} else {
  //option 3
}
```

If statements do not need curly brackets if they only run one line

```java
int points = 10;
if (scoredPoints()) points++;
```


Switch
---

Because long `if` chains are bad practice there is an alternative. If you want to do something different for different values of a variable you would use a `switch` statement. A switch statement reads a value and runs one section depending on what it is. It does not take a boolean value and you can't compare it, only check its value. It has an unusual syntax, you start with `switch` and then the variable to check and in curly brackets you write `case (checked value): ` where you then write the code it would run. At the end of each section you write `break`. The `default` case will run if no other case matches.

```java
switch(number) {
  case 1:
    //if number = 1
    break;
  case 2:
    //if number = 2
    break;
...

  default:
    //any other number you didn't check
}
```

Loops
---

Loops do exactly exactly what they're called, they let you run a section of code multiple time. The two types of loops are `while` loops and `for` loops.

While loops run its code as long as a condition is true. It is as simple as `while (condition) {/*code in here*/}`

```java
while (hasGamePiece) {
  turnLEDsGreen();
}
```
Although it is possible to create infinite loops it is important to remember that the robot will only read one line of code at a time, and an infinite loop (or just a really long one) will stop the robot.

The more useful loop, although more complex, is the `for` loop. The for loop has three parameters. In the first you declare a variable, usually `int i = 0` (there are several different names for "i" including iterator, index, and integer). The second parameter is a boolean, if it is true the loop continues, otherwise the loop will end. The third parameter is what happens at the end of a loop, usually `i++`. The parameters are seperated by semicolons.

```java
int points = 0;
for (int i = 0; i < 20; i++) {
  shoot();
  points++;
}

// shoots and scores 20 times
```

You can end a loop prematurely with `break`.

for loops have a second format which lets you loop through each item in an array. The format for this is `for(type variable : array)`

```java
int[] integers = {1, 2, 3, 4, 5};
for (int i : integers) {
  System.out.println(2 * i);
}
// 2 4 6 8 10

for (int i = 0; i < integers.length(); i++) {
  System.out.println(2 * integers[i]);
}
//does the same thing
```
