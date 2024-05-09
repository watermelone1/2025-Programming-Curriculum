An operator is what lets you modify [variables](https://github.com/watermelone1/2025-Programming-Curriculum/blob/main/Week%201/Variables.md) and use them with other variables or numbers. The basic operators include:
- The four basic math operators `+ - * /`
- Modulus `%`
- Increment/Decrement `++ --`
- Assignment operators `+= -= *= /= %=`
- Boolean comparisons (see more)
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
