# JAVA Basics

> Note - When we run this file, what happens is that it tries to find a class of the same name as the file name. (let's say our file name is `Basics.java`).
> 
> Class is something which keeps all the objects, methods inside of it.

Once the system has figured out the `Basics` class, it will try to figure out the `main` method. `main` is always the entry-point.

Java Boilerplate - 

```java
class Basics {
    public static void main(String[] args) {
        
    }
}
```

- `public` is an access specifier. It tells if it is available to the outer world or not to use.

- `static` is a keyword. It means that we don't have to create an object. We simply can directly reference the method by saying `Basics.main`. This is how the system can reference the `main` entrypoint.

> Note - If we don't write `static`, the `run` wont figure out the `main`, since it is not able to find the static main method as the system is trying to access `Basics.main`. `run` is the default build rule which works only when we write the `static` keyword.

- `void` means we are not returning anything.

- `main` is our method or function. Function is a portion of code that does something.

> Note - We have defined our build-rule so that it picks up the input from input.txt file and shows the output in the output.txt file. But when we click the `run` button just above the `public` keyword, we take the input from the command line.

- And those command line inputs usually goes into this `String args[]` arguments. So , basically if we are trying to give the input from the command line, we need to mention `String args[]`, we can't skip it.

Now, to print something on the screen, we write -

```java
System.out.println("Hello");
```

`System.out` is a class, just like our `Basics` class and `println` is a pre-defined method in it.

---

We write `comments` using `//` for single-line comments and `/*    */` for multi-line comments.

---

## Data Types

`byte short int long float double char`

1. `byte`

To store integers in the range - `-128 to 127`, we use `byte`.

It takes 8 bits in the memory. (Bit manipulation)

```java
byte num = 100;
System.out.println(num);
```

2. `short`

Again for storing integers, in the range of `-32,768 to 32,767`.

It takes 16 bits in the memory.

3. `int`

Most frequently used data-type for storing integers.

Range is `-2^31 to 2^31-1` or we can say `around 10^9`.

It takes 32 bits in the memory.

4. `long`

Range is `-2^63 to 2^63 - 1`.

It takes 64 bits in the memory.

For storing integers more that 10^9 which `int` can't store.

> Note - We mainly use `int` and not `byte short`.

5. `float`

For storing decimal numbers upto 6-7 decimal places of precision.

It takes 32 bits in the memory.

6. `double`

For storing decimal numbers upto 15 decimal places of precision.

It ends up taking 64 bits in the memory.

7. `char`

To store any of the 256 characters, we use this data-type.

```java
char ch = 'a';
```

8. `boolean`

Stores either `true` or `false`.

```java
boolean didHw = true;
```

---

## Operators

#### Arithmetic Operators -

```java
-, +, /, *, %
int num = 12/5; //stores 2 in num
```

`%` - gives the remainder when we divide one number to another.

```java
int num = 12%5; // stores 2 in num
```

#### Unary Operator -

`+, -, ++, --, !`

```java
int num1 = 6;
int num2 = +num1;
System.out.println(num2); // prints 6
```

```java
int num1 = 6;
int num2 = -num1;
System.out.println(num2); // prints -6
```

```java
int num1 = -6;
int num2 = -num1;
System.out.println(num2); // prints 6
```

Basically unary operators `+, -` are just like multiplying `+1,-1` to the number.

`!` - NOT Operator : `!true = false`, `!false = true`, `!!true = true`

`++` - Plus Plus : Two aspects of it - Either we write `num++` (Post-increment) or `++num` (Pre-increment).

Example of Post-increment  -

```java
int num1 = 6;
int num2 = num1++; // num1 is still 6 while getting assigned
System.out.println("num1: " + num1); // prints 7
System.out.println("num2: " + num2); // prints 6
```

Post-increment means increment happens after the operation at hand where `num++` is mentioned. That is, `num1` is assigned to `num2` then `num1` increases itself by 1.

Example of Pre-increment -

```java
int num1 = 6;
int num2 = ++num1;
System.out.println("num1: " + num1); // prints 7
System.out.println("num2: " + num2); // prints 7
```

Pre-increment means increment happens before the operation at hand. That is, `++num1` means `num1` first increases itself by 1 and then `num1` is assigned to `num2`. 

Similary, we have `--num` (Pre-decrement) and `num--` (Post-decrement).

#### Relational Operators -

` ==, !=, >, <, >=, <= `

Returns `true` or a `false`.

```java
int num1 = 6;
int num2 = 7;
boolean result = num1 == num2; // false
```

#### Logical Operators -

` && , || `

`&&` - returns `true` only if both the expressions around it are `true`.

`||` - return `false` only if both the expressions around it are `false`.

#### Assignment Operators -

` = , += , -= , /= , *= `

Example -

```java
int result = 8;
result /= num1 + num2; // means result = result / (num1 + num2)
```

#### Ternary Operators -

` condition ? first_expression : second_expression `

Example -

```java
int num1 = 6;
int num2 = 9;
int num3 = num1 > num2 ? num1 : num2; // false -> num3 = 9
```

> It's a shorter-way of writing `if...else`.

---

## Strings

```java
String name = "Priyansh";
System.out.println(name + "has length" + name.length()); // prints 
// Priyansh has length 8
```

How to print any one character from the `name` ?

We use **`.charAt(index)` method** on the string. String-indexing starts from 0.

What if we just want `raj` to be printed ? We use **`.substring(int beginIndex, int endIndex)` or `.substring(int beginIndex)`.**

```java
class Basics {
    public static void main(String[] args) {
        String name = "Raj Vikram";
        System.out.println(name.substring(0)); // prints `Raj Vikram`
        System.out.println(name.substring(2)); // prints `j Vikram`
        System.out.println(name.substring(0, 3)); // prints `raj`
    }
}
```

> `System.out.println(0, 3);` 
> 
> It doesn't include the `endIndex`, that is to print first `3` characters, we need `0 1 2 3`, that is, `from 0 to 3` (ONE MORE THAN THE ENDING INDEX). (Does include the beginning index, but doesn't include the ending index)

**String concatenation** - By using `+`.

Example - 

```java
String name = "raj";
String lastName = "vikram";
name += " " + lastName;
System.out.println(name); // prints raj vikram
```

> Note - `String name = "raj";` creates an object in the memory where `raj` is stored. But In JAVA, `Strings are immutable`. Hence, when we did `name += " " + lastName;` , it doesn't change the variable `name` in the same memory location. Instead, it creates another.

**`.equals()`** **method** - checks if the two strings are the same or not.

```java
boolean result = name.equals(lastName); // result = false
boolean result = name == lastName; // result = false
```

---

## Input / Output

Internally, we have something known as `Scanner` class. But it's inside the package `java.util`. But first we need to include it in our program, by writing `import java.util.Scanner`.

In order to access the functions of that `Scanner` class, we need to create an `object` of it.

Syntax for creating an object -

```java
Scanner scanner = new Scanner(System.in);
// CLASSname objectName = newKeyword CLASSname(way to create an object);
```

*To get the input from the user, we write -*

```java
public static void main() {
    Scanner scanner = new Scanner(System.in);
    int num = scanner.nextInt(); // we access the methods of that class by using them on their objects.
    System.out.println(num);
}
```

But, we need to also `close` the object to free out the space of that object, by using the `scanner.close()`.

So, our basic code would be like this -

```java
public static void main() {
    Scanner scanner = new Scanner(System.in); // mandatory to write

    int num = scanner.nextInt(); 
    System.out.println(num);

    scanner.close(); // mandatory to write
}
```

The first and the last line remains the same, between that, we need to think around.

*To take a double input, we have something called `nextDouble` method*.

```java
double num = scanner.nextDouble();
```

*To take string as an input, *

```java
String name = scanner.nextLine();
```

**Note - `.nextLine()` picks up the whole string until the next [ENTER]**.

*To take the strings until the next [space], we use `.next()` method*

```java
input.txt
Raj Vikram

String firstName = scanner.next(); // picks up Raj
String lastName = scanner.next(); // picks up Vikram
```

> Note - Creating an object is important since it remembers what it picked up the last.
> 
> There is a method to pick up the **boolean** also, by using `.nextBoolean()`.
> 
> `BufferedReader` is slightly faster method to get the input from the user than the scanner class method but it always takes the input as a string and we always need to convert it into our required data-type.
> 
> It's best to use `BufferedReader` when we need to pick up large amouts of text data.

---

## Type Casting

#### Implicit Type Casting -

Example -

```java
int x = 10;
double y = x;
System.out.println(y); // prints 10.0
```

Here, 10 was internally converted into a `double` from an `int`.

But, if we do the reverse,

```java
double x = 10;
int y = x; // This will be an error -  Possible lossy conversion from 
// double to int
```

Here, converting a double to an int doesn't work because here we are losing something, that is, the numbers after the decimals.

This is known as **Implicit Type Casting**.

But what if we want to convert a double into an integer, then we use something called as explicit type casting.

#### Explicit Type Casting -

```java
double x = 10.7;
int y = (int) x; // 10.7 gets converted to 10
```

> Implicit Type Casting works only when the compiler identifies that we are loosing on something, it doesn't work when an integer is converted into a double.

---

## Constants (`final` keyword)

When we don't want to change the value of some variable **ever**, we use the `final` keyword while declaring the variable.

```java
final int num = 10; // no one can change the value of the num.
```

---

## Arrays

#### Declaration, length, accessing -

To store multiple variables of the same data-type, we can use a container for them and we call that container **`arrays`**.

Syntax to declare an array -

```java
int[] arr = new int[5];
// int[] says it is an array arrayName = newKeyword to create a new object
// int[5] says that it is a 5-integer object.
```

> Note - All the integers inside the integer array are stored in contiguous memory locations.
> 
> Also, arrays can't store different data-type variables in it.

To store the integers in the array, we again use the 0-based indexing,

example - 

```java
arr[0] = 1;
arr[1] = 2;
arr[2] = 1;
System.out.println(arr[1]); // prints 2
System.out.println(arr[6]); // RUN_TIME ERROR
```

> Note - If our system throws a **RUNTIME ERROR**, it means we are trying to access an inaccessible memory location.

**Length** - To get the length of the array, we use `.length`.

Example - 

```java
System.out.println(arr.length); // gives the length of the array
```

#### `for each` loop -

Used to iterate on the arrays.

Syntax -

```java
// First, let's accept the size and the the numbers of the array
keep in mind that the arrays can only store the variables with the same 
data-type, not different

int size = scanner.nextInt(); // gets the size of the array
int[] arr = new int[size]; // creates an array of the required size
int i;
for (i = 0; i <= size-1; i++) {
    arr[i] = scanner.nextInt(); // builds the array with the numbers we give
}


TO ITERATE OVER THE ARRAY - By using `for...each` loop
// for(dataTypeOfTheArray nameOfTheItem: nameOfTheArray)
for(int num: arr) {
    System.out.print(num + " ");
}
```

#### 2D Array -

At every index, can we store an array ? Yes, by using 2D arrays.

Generic way of defining an array -

```java
int[] arr = {6, 7, 8, 9};
```

To store arrays inside this array, we write -

```java
int[][] = {{6, 5}, {7, 8}, {9}, {2, 3, 5}};
```

Now, to access the array at the zeroth index, we write -

```java
int[] zeroIndex = arr[0]; // stores {6, 5} in the array zeroIndex
System.out.println(zeroIndex[1]); // prints 5
OR WE CAN DO
System.out.println(arr[0][1]); // prints 5
```

> Note - So basically, we are storing arrays inside an array.

---

## Conditional Statements

**`if... else`**

```java
// Given an age, print "adult" if age >= 18, or print "teen"
import java.util.Scanner
class Basics {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int age = scanner.nextInt();
        if (age >= 18) {
            System.out.println("Adult");
        } else {
            System.out.println("Teen");
        }

        scanner.close();
    }
}
```

**`if...else if...else`**

```java
/* 
Given the marks of a student, tell us the grade he is getting using the 
following rules
- Grade A (>=90)
- Grade B (>= 70 and <90)
- Grade C (>= 50 and <70)
- Grade D (>= 35 and <50)
- Fail (<35)
*/


HERE we will use an `else if` clause


import java.util.Scanner
class Basics {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int marks = scanner.nextInt();
        if (marks >= 90) {
            System.out.println("Grade A");    
        }
        else if (marks >= 70) {
            System.out.println("Grade B");
        }
        else if (marks >= 50) {
            System.out.println("Grade C");    
        }
        else if (marks >= 35) {
            System.out.println("Grade D");
        }
        else {
            System.out.println("Fail");
        }

        scanner.close();
    }
}
```

> Note - Every `if` might not have a `else`.
> 
> Tip - `System.out.println()` prints in a new line, that is, it inserts a new line after prinitng whatever we wrote inside the braces, whereas `System.out.print()` prints in the same line.

**`Nested if...else`**

```java
/*
You are given three integers a, b, and c,
print which of these integers is the largest
If two or more integers are equal and are the largest,
the program should indicate that as well.
*/

import java.util.Scanner;
class Basics {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int num1 = sc.nextInt();
        int num2 = sc.nextInt();
        int num3 = sc.nextInt(); // picks up the next integer before the next space
        if (num1 >= num2) {
            // num2 can't be the greatest
            if (num1 >= num3) {
                System.out.println("num1 is the greatest " + num1);
            }
            else {
                System.out.println("num3 is the greatest " + num3);
            }
        }
        else {
            // num1 can't be the greatest
            if (num2 >= num3) {
                System.out.println("num2 is the greatest " + num2);
            }
            else {
                System.out.println("num3 is the greatest " + num3);
            }
        }    

        sc.close();
    }
}
```

---

## Switch Statement

```java
// Given the day number, print which day it is of the week
// assume week starts from Monday and ends on Sunday
multiple checks can slow down the execution and hence we use switch
which directly jumps to the matching case directly without making 
unnecessary checks

import java.util.Scanner;
class Basics {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int dayNumber = scanner.nextInt();

        switch (dayNumber) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesd");
                break;
            case 3:
                System.out.println("Wed");
                break;
            case 4:
                System.out.println("Thurs");
                break;
            case 5:
                System.out.println("Fri");
                break;
            case 6:
                System.out.println("Sat");
                break;
            case 7:
                System.out.println("Sun");
                break;
            default:
                System.out.println("Invalid day");
        }

        scanner.close();
    }
}
```

> Note - `break` statement helps prevent **fall-through** of the break statement, that is, executing the code of all the cases beyond the matched case.

---

## Loops

#### `for` loop

To do some task for a pre-specified number of times, we use `for` loop.

Syntax -

```java
int i;
// initializaion: condition check(run the loop until this condition is true);
// increment/decrement
for (i = 1; i <= 10; i++) {
    System.out.println("I am great.");
}
```

Leaving out the `i++` or `i<=10` and not writing anything may create an infinite loop, that is, when the condition is always true.

`ARRAYS AND FOR LOOP TOGETHER`-

Example -

```java
// Given the No. of numbers we are entering and all the numbers,
// sum all those numbers

int size = scanner.nextInt();
int[] arr = new int[size];
int i;
for (i = 0; i <= size-1; i++) {
    arr[i] = scanner.nextInt(); // .nextInt() function always takes the 
// next Integer there is, never the same integer again and again
}

int sum = 0;

for (i = 0; i <= size-1; i++) {
    System.out.println(arr[i]);
    sum = sum + arr[i];
}
System.out.println(sum);
```

#### `While` loop -

Alternative of `for` loop.

Syntax -

```java
// print multiples of 2 till 50
int i = 2;
while (i <= 50) {
    System.out.println(i);
    i += 2;
}
```

#### `do...while` loop -

Execute minimum of one time for sure.

Syntax -

```java
// write a program that takes an integer till it reaches 10, and prints 
// all of them.
Scanner scanner = new Scanner(System.in);
do {
    int num = scanner.nextInt();
    if (num == 10) {
        break;    
    } while (true); // here we don't depend on the condition inside the 
// while
    System.out.println(num);
}


ANOTHER WAY OF WRITING THE SAME CODE -
int num;
do {
    num = scanner.nextInt();
    System.out.println(num);
} while (num != 10);
```

---

## Exception Handling (`try...catch` block)

Whenever there is an exception or when something is not possible, for example dividing by 0 or trying to access an index of an array which is not there.

Syntax -

```java
try {
    int num1 = 10;
    int num2 = 0;
    int num3 = num1 / num2;
    System.out.println(num3);
}
catch (Exception e) { // catches that exception in the variable `e` of 
// data-type `Exception`
    System.out.println(e); // prints java.lang.ArithmeticException: / by zero
}
finally {
    // doesn't matter if these is an exception/error or not, it always
// runs this code block
    System.out.println("done");
}
```

> Note - Not really required in DSA, but you can use it to catch some RUNTIME error.

---

THAT'S IT FOR JAVA BASICS

Good Luck ! :heart:
