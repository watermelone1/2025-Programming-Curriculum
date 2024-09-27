# How to Read Code

Code is written in lines, with each line doing something from top to bottom.
```
1. This line runs first
2. This line runs second
3. This line runs third
```

Comments don't run any code but can leave notes to someone reading it.
```java
runMotor(20);
scorePoints(1);
//This is a comment which doesn't do anything
```

As you can see, every line ends with a semicolon `;`.  Think of it like how a period ends a sentence, a semicolon ends a line of code.

### All concepts after this point haven't been taught yet (probably)

---

Variables, methods, and classes have a special naming format.\
Variables and methods use camelCase where the first word is not capitalized and each word after is with no spaces.\
Classes use PascalCase witch is the same as camelCase but the first word is capitalized.\
Constants use SCREAMING_SNAKE_CASE with all uppercase letters and underscores `_` between words

```java
int armSpeed;
int robotWheelSpeeds;
void goToStartPosition()
// camelCase

class GoToPositionCommand
//PascalCase

final double ARM_GEAR_RATIO
//SCREAMING_SNAKE_CASE
```

Any flow control is wrapped in curly brackets `{}` including classes, and methods.

```java
class GoToPositionCommand {...}
void goToStartPosition() {...}
```
Helpful Tips
---
VSCode will highlight a lot of things such as:
- Code highlighting
- Variable and method usages
- Bracket start and ends
