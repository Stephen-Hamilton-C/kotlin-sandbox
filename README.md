# Kotlin Sandbox <!-- omit in toc -->

# Table of contents <!-- omit in toc -->

- [Basic Miscellaneous](#basic-miscellaneous)
  - [for-loop vs forEach](#for-loop-vs-foreach)
  - [val vs var](#val-vs-var)
  - [Input](#input)
  - [Logical Operators](#logical-operators)
- [Types](#types)
  - [String Templates](#string-templates)
  - [Numbers](#numbers)
- [Collections](#collections)
  - [Lists](#lists)

# Basic Miscellaneous

## for-loop vs forEach
- If it’s a primitive or IntRange, use a for-loop.
- If it’s a collection (like sequence or list), use forEach
- If you need continue or break, use for-loop

forEach is faster in some cases, while for-loop is faster in others (factor of 10 in many cases). The criteria above will keep you speedy.

Source: https://medium.com/mobile-app-development-publication/kotlin-for-loop-vs-foreach-7eb594960333

## val vs var
`val` behaves exactly like `final`. It can be declared and then later initialized, like so:
```kt
val pi: Double;
pi = 3.14;
```

`var` is normal, it's just declaring a mutable variable.

## Input

Input is way easier than Java. Don't need a Scanner anymore, just do `readline()`

## Logical Operators

The order of evaluation:
1. Parethesis
2. NOT
3. AND
4. OR

# Types
Java has primitives `int`, `double`, `boolean`, etc.. It also has their class equivalents: `Int`, `Double`, `Boolean`, etc..
The class equivalents have more flexibility and can be used in collections.

However, Kotlin does not have the standard primitives, at least indicated by the names. The primitive types all start with a capital letter: `Int`, `Double`, `Boolean`.
Trying to make a variable with type `int`, `double`, or `boolean` with throw an error.

## String Templates

String templates exist by default, no special syntax required. Use `$var` to simply insert a variable into the string or `${expression}` to insert the result into the string.
```kt
val pi: Double = 3.14159;
println("Pi is $pi") // Pi is 3.14159
```

You must use braces if accessing members of an object.
```kt
val fruits: List<String> = listOf("Apple", "Orange", "Banana");

// WRONG! This will print the value of fruits and then ".size" afterward!
println("I got $fruits.size fruits")

// This is correct:
println("I got ${fruits.size} fruits") // I got 3 fruits
```

## Numbers

You can put an underscore (`_`) in a number variable much like commas in normal numbers. This makes the numbers much easier to read.
```kt
val speedOfLight = 186_282;
// Equivalent to 186282, but the underscore makes it easier to read
```

Order of operations:
1. Parenthesis
2. Multiplication
3. Division
4. Modulus
5. Addition
6. Subtraction

# Collections

## Lists

An immutable list contains items that must never be altered.

`listOf(...objects)` creates an immutable list, while `mutableListof(...objects)` creates a mutable list.

*dude, this is so nice, look at this:*  
You can get a random item from a list using `list.random()` instead of the old clunky way:
```java
List<String> fruits = Arrays.asList("Apple", "Orange", "Banana");
Random random = new Random();
System.out.println("Random fruit: " + fruits.get(rand.nextInt(fruits.size())));
```
Here's the neat Kotlin way of getting a random item from a list:
```kt
val fruits: List<String> = listOf("Apple", "Orange", "Banana");
println("Random fruit: ${fruits.random()}");
```
I'm telling you, Kotlin is literally better Java.
