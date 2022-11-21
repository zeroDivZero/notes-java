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
