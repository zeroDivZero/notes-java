# CHEAT SHEET

## File Name

Each **.java** file should have 1 class, class and file names must match. If multiple classes, compiler produces bytecode for each class (**.class** file). To avoid confusion, JVM uses bytecode matching file name as entry point.

```java
/* HelloWorld.java */
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello world!");
  }
}
```

## Compile and Execute

Compile (creates bytecode **.class** file per class):

```sh
javac HelloWorld.java
```

Run:

```sh
java HelloWorld
```

## Primitive Types

### Integer

```java
int age = 15;
```

### Double

```java
double gpa = 3.45;
```

### Character

```java
char firstInitial = 'K';
```

### Boolean

```java
boolean isRegistered = true;
```

There are more. These are most used.

## String

Reference type, built from characters.

```java
String firstName = "John";
String lastName = "Smith";
```

### `charAt()`

```java
char firstInitial = firstName.charAt(0);
```

### Concatenate

```java
String name = firstName + " " + lastName;
```

### `equals()`

```java
if (string1.equals(string2)) {
  // do something
}
```

### `toLowerCase()`

```java
String lowerCaseString = myString.toLowerCase();
```

## Relational Operators

`>`, `<`, `==`, `>=`, `<=`, `!=`

## `if`

```java
if (num < 5) {
    // do something
} else {
    // do something else
}
```

## `while`

```java
while (isOn) {
  // do something
  // set `isOn` to `false` to exit loop
}
```

## Function

```java
double calculateTotalMealPrice(double listedMealPrice, double tipRate, double taxRate) {
    double tip = tipRate * listedMealPrice;
    double tax = taxRate * listedMealPrice;
    double total = listedMealPrice + tip + tax;
    return total;
}
```

If not returning value, specify `void`. Arguments optional.

## Class

```java
public class Triangle {
    // class variable
    static int numOfSides = 3;

    // instance variables
    double base;
    double height;
    double sideLenOne;
    double sideLenTwo;
    double sideLenThree;

    // constructor
    public Triangle(double base, double height, double sideLenOne, double sideLenTwo, double sideLenThree) {
        this.base = base;
        this.height = height;
        this.sideLenOne = sideLenOne;
        this.sideLenTwo = sideLenTwo;
        this.sideLenThree = sideLenThree;
    }

    // instance method
    public double findArea() {
        return 0.5 * (this.base * this.height);
    }
}
```

Usage:

```java
Triangle triangleA = new Triangle(15, 8, 15, 8, 17);
double triangleAArea = triangleA.findArea();

System.out.println(triangleA.base);
System.out.println(Triangle.numOfSides);
```
