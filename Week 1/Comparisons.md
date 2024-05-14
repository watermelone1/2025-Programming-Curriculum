Comparisons are similar to operators, they are booleans but they *compare* two values. They are:
- `==`
- `<`
- `>`
- `<=`
- `>=`

`==` checks if two values are equal. `=` equal is not used because it is already used to set variables.
```java
3==2; //false
1==1; //true
controller.joystickValue == 1;
```

`<`, `>`, `<=`, `>=` are greater or less than and greater or less than or equal.
```java
if (currentAngle < targetAngle) {
  rotateUp();
}
if (gearRatio >= 3/5) {
  decreaseMaxSpeed(0.2);
}
```
<br><br>
Be aware that sometimes `==` does not work with Strings and you should use `exampleString.equals(comparedString);`:
```java
  String str1 = "robot";
  String str2 = "robot";
  String str3 = new String("robot");

  System.out.println(str1 == str2);
  System.out.println(str2 == str3); 
  System.out.println(str1.equals(str2));
  System.out.println(str2.equals(str3));
```
```
true
false
true
true
```

The reason is that the `==` compares the actual locations in memory of the strings which can be different in the case of `str3` while `Strinf.equals()` compares the values

[Explanation](https://www.scaler.com/topics/difference-between-equals-method-in-java/)
