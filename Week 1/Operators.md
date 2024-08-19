An operator is what lets you modify [variables](https://github.com/watermelone1/2025-Programming-Curriculum/blob/main/Week%201/Variables.md) and use them with other variables or numbers. They include:
- The four basic math operators `+ - * /`
- Modulus `%`
- Increment/Decrement `++ --`
- Assignment operators `+= -= *= /= %=`
- Boolean operators and comparisons (see more)
- Bitwise operators (we won't use these, if you want to then take AP CSA)

Using operators is as easy as putting it between two numbers or variables. `+ - *` do exactly what they would do in a regular math equation and do not even need a variable. `/` is slightly different, if you divide two integers it will always give out another by throwing away the remainder. To get a double you cast it to a double first.

```java
int shotAngle = 12;
int angleDifference = 20;
int targetAngle = shotAngle + angleDifference
// targetAngle = 12 + 20 = 32

double currentDistance = 10;
double targetDistance = 5;
double distanceToMove = currentDistance - targetDistance;
// distanceToMove = 10 - 5 = 5

double movementSpeed = 100;
double speedFactor = 0.6;
double endSpeed = movementSpeed * speedFactor;
// endSpeed = 100 * 0.6 = 60;

double currentSpeed = 68;
double newSpeed = 49;
double speedFactor = newSpeed/currentSpeed;
// speedFactor = 49/68 = 0.659
// if these were ints it would be 0 because it would throw out the decimal. 
```

If you want to change a variable at the same time you use an operator you use either an increment or decrement, or assignemnt operator. Increment operators add or subtract one from a variable.
```java
int pointsScored = 14;
pointsScored++; // pointsScored = 15

currentDistance = 10;
movedDistance = 3;
currentDistance += movedDistance // currentDistance = currentDistance + movedDistance
```
(remember that without assigning the variable it will not change `currentDistance + movedDistance` will not necesarily change `currentDistance`)

Modulus
---

Modulus is a strange operator, it's a math operator although it's unlikely you have ever used it in a math class. It basically means to only use the remainder after a division for example `5 % 3` is the remainder of 5/3, 2. Because of this, you can easily find if a number is a multiple of another. If a%b = 0 then a must be a multiple of b.
```java
System.out.println(7%2); // 1, 7 is not a multiple of 2
System.out.println(45%9); // 0, 45 is a multiple of 9
```

As a increases, a%b loops from 0 to (b-1)
```java
0 % 4;  // 0
1 % 4;  //  1
2 % 4;  //   2
3 % 4;  //    3
4 % 4;  // 0
5 % 4;  //  1
6 % 4;  //   2
7 % 4;  //    3
8 % 4;  // 0
9 % 4;  //  1
```

This pattern does not work the same for negative numbers

Boolean Comparisons
---

Boolean is a type with stores only a true or false value. 
```java
boolean isRobotOn = true;
boolean onRedTeam = false;
```

Booleans have their own ways of modifying them. These are 
- AND `&&`
- OR `||` (vertical bar on the right of the keyboard)
- NOT `!`
- XOR `^`

NOT is the easiest boolean operator. It only has one input and returns the opposite of what it was given for example `!true` is false and `!false` is true. We use it the most such as checking whether or not we are in range of something, whether or not we have game pieces, or whether or not we are simulating the robot.

AND means that a value is true only if both sides are true for example `true && false` or `false && true` both give `false`, `true && true` is the only combination that gives `true`. This is representable using a "truth table"

|A&&B|      | A     |       |
|---|-------|-------|-------|
|   |       | TRUE  | FALSE |
| B | TRUE  | TRUE  | FALSE |
|   | FALSE | FALSE | FALSE |

We use AND to check for multiple requirements:
```java
if (withinRange && atCorrectAngle) shoot();
```

OR gives a true value if at least one of its sides are true so `true || false` or `true || true` both give `true`. The truth table for OR is:

|A\|\|B|      | A     |       |
|---|-------|-------|-------|
|   |       | TRUE  | FALSE |
| B | TRUE  | TRUE  | TRUE  |
|   | FALSE | TRUE  | FALSE |

We use OR to check for one or more requirements:
```java
boolean canClimb = climbersUp || alreadyClimbing;
```

XOR is the least common boolean operator, it is true when *exactly* one input is true, `true ^ false` is true but `true ^ true` is false. The truth table is: 

|A^B|      | A     |       |
|---|-------|-------|-------|
|   |       | TRUE  | FALSE |
| B | TRUE  | FALSE | TRUE  |
|   | FALSE | TRUE  | FALSE |

Bitwise Operators
---
There is a reason this was left for the end. This is the dark scary side of programming. Rest assured we will NEVER use this on robot code. Ever. Only in AP CSA will you actually use it and you'll probably not touch it after (idk im not in ap csa as of writing this). 

Before learn bitwise operators you must know how to count in binary. I'm not going to teach that but its not too hard and [here](https://www.khanacademy.org/math/algebra-home/alg-intro-to-algebra/algebra-alternate-number-bases/v/large-number-decimal-to-binary) is a random Khan Academy video I found. A bitwise operation is applying a boolean operation to every bit in a number, the bitwise operators are:
- Bitwise OR `|`
- Bitwise AND `&`
- Bitwise XOR `^`
- Bitwise NOT `~`
- Bitshift Left `<<`
- Bitshift Right `>>`

Bitwise OR applies an OR operation on every pair of bits for example

<sup>excuse the horrible formatting</sup>
| a    | 1 | 0 | 0 | 1 | 0 |
|------|---|---|---|---|---|
| b    | 0 | 1 | 0 | 1 | 1 |
| a\|b | 1 | 1 | 0 | 1 | 1 |
(markdown formatting is hard)

Bitwise AND applies an AND operation on every pair of bits for example

| a    | 1 | 0 | 0 | 1 | 0 |
|------|---|---|---|---|---|
| b    | 0 | 1 | 0 | 1 | 1 |
| a&b  | 0 | 0 | 0 | 1 | 0 |

Bitwise XOR applies an XOR operation on every pair of bits for example

| a    | 1 | 0 | 0 | 1 | 0 |
|------|---|---|---|---|---|
| b    | 1 | 1 | 0 | 1 | 1 |
| a^b | 0 | 1 | 0 | 0 | 1 |

BitWise NOT applies a NOT operation on every bit for example

| a    | 1 | 0 | 0 | 1 | 0 |
|------|---|---|---|---|---|
| !a   | 0 | 1 | 1 | 0 | 1 |

(this one is actually different because java uses 32-bit [Two's complement](https://en.wikipedia.org/wiki/Two%27s_complement)) For most values of x, ~x = (-x)-1

Bitshifts move all of the bits to the left or right and throws out the bit on the end. For most purposes this is the same as multiplying or dividing by 2

| a    | 1 | 0 | 0 | 1 | 0 |
|------|---|---|---|---|---|
| a>>1 | 0 | 1 | 0 | 0 | 1 |
