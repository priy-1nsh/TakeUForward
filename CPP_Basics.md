# CPP Basics

## Basic Skeleton

```cpp
#include <iostream.h>
#include <math.h>

int main() {
    return 0;
}
```

Just like we need to know English in order to read a certain book written in English, similarly, we need to include libraries which are basic C++ rules in order to run our cpp program.

For taking an input and give an output, for that, we need a library called `iostream`, that is, we need to `include` it in our program.

Similarly if we need to do a lot of math functions, we simply `include` `math.h`, which are simply the math rules.

Hence, whatever rules we require, we will add them on, like `strings.h`.

Now, how we will know which library to include ?

Basically what we do is, we simply include one library which contains all the other libraries like this -

```cpp
#include <bits/stdc++.h>
```

In this way, all the libraries get pre-included and we don't need to individually add them one-by-one.

But there is one catch here, even the libraries we are not using in our program, they also get included and compiled, hence the compilation time is slightly more, but it's like a fraction of seconds.

Entry-point where the machine starts reading the code and that entry-point is `main()` function. Since it is a function, it has to `return` something as well and the `data-type` of this return is `int`(short for integer).

What if the function doesn't return anything ? It just does something but doesn't return anything, then we end up writing `void`. 

```cpp
void main() {}
```

To print a string, we use `cout << "Hello World!"` and the strings are written in double quotes. It gives the string `"Hello World!"` to the function `cout`.

But this will give an error - `cout identifier undefined`. Instead we need to use `std::cout << "Hello World!"` because cout is defined inside the `std` package. But it's annoying to write `std::` again and again. Hence, we use the `namespace std` by writing -

```cpp
using namespace std;
```

---

## Data Types

Syntax to declare variables -

1. For storing integers
- `int`

```cpp
int numInt = 10;
cout << numInt; // 10 will be printed.
```

```cpp
int numInt = 10.7;
cout << numInt; // 10 will be printed again.
```

Range of `int` is -2,147,483,648(INT_MIN) to 2,147,483,648(INT_MAX). `[-10^9, 10^9]`.

- `long`

```cpp
int numInt = INT_MAX;
cout << numInt << endl; // endl is a newline character, basically an `Enter`
long numLong = 1000000000000;
cout << numLong;
```

Range is `[-10^12, 10^12]`.

- `long long`

Range is around `[-10^18, 10^18]`.

> NOTE - Till 10^9 : use `int`
> 
> Till 10^12 : use `long`
> 
> Till 10^18 : use `long long`

2. Decimal Numbers
- `float`

To store decimal numbers till 7 decimal places, we use `float`.

- `double` 

To store decimal numbers upto the precision of 15 decimal places, we use `double`.

3. Character

To store any of the 256 characters, we use `char`.

Example - `char ch = 'a'`.

4. Strings

To store strings, we don't have a data-type, instead we have a class called `string`.

This `string` class is also under `std` package.

```cpp
std::string str = "tuf";
std::cout << str;
```

If we use `namespace std`, we can write like this -

```cpp
string str = "tuf";
cout << str;
```

---

## Input / Output

First, we need to determine what is the data-type of the input.

Example -

```cpp
int bdate;
cin >> bdate; // reads the input file and stores the input in bdate variable.
```

To get multiple inputs,

```tex
input.txt

79 89
```

```cpp
int main() {
    int bdate, num;
    cin >> bdate; // takes the number 79, it reads the first possible 
                  // integer, not the line number.
    cin >> num; // takes the number 89
    // we can also write like this - cin >> bdate >> num
    cout << bdate << endl << num;
    return 0;
}
```

If, we don't assign the variable any value, and tries to print it, it will give some garbage value.

```tex
output.txt

79
89
```

```cpp
// If we write like this -
int main() {
    char bdate, num;
    cin >> bdate >> num;
    cout << bdate << endl << num;
    // prints 7 [Enter] 9, treating `79 89` as a string 
}
```

```cpp
// if we write like this -
int main() {
    string bdate num;
    cin >> bdate >> num;
    cout << bdate << endl << num;
    return 0;
    // prints `79` [Enter] `89` treating them as separate strings.
    // If the input.txt is 'tuf is amazing', then we get the output as 
    // `tuf` [ENTER] `is`
}
```

So, to pick up the entire string, 

```cpp
string str;
getline(cin, str); // picks up the whole `tuf is amazing`, that is 
                    // it reads till the next [ENTER].
cout << str;
return 0;
```

---

## If...else

```cpp
// Given an integer age ,print 'adult' if age >= 18, otherwise print 'teen'
if (age >= 18) {
    cout << "Adult";
}
if (age < 18) {
    cout << "Teen";
}
```

Here, we are doing an unnecessary check, instead we can just write `else` to avoid it.

```cpp
if (age >= 18) {
    cout << "Adult";
} else {
    cout << "Teen";
}
```

#### Another Example - use of `else if`

```cpp
// Given an integer age
// - if age >= 18, print "Adult"
// - if age < 18 and age >= 10, print "teen"
// - if age < 10, print "child"
if (age >= 18) {
    cout << "Adult";
} else if (age < 18 && age >= 10) {
    cout << "Teen";
} else {
    cout << "Child"
}
```

```cpp
/*
Given the marks of a student, tell us the grade he is getting following 
the below rules - 
- Grade A (>=90)
- Grade B (>=70 and <90)
- Grade C (>=50 and <70)
- Grade D (>= 35 and < 50)
- Fail
*/
#include<bits/stdc++.h>
using namespace std;

int main(){
    int marks;
    cin >> marks;
    if (marks >= 90) {
        cout << "A";
    }
    else if (marks >= 70 && marks < 90) {
        cout << "B";
    }
    else if (marks >= 50 && marks < 70) {
        cout << "C";
    }
    else if (marks >= 35 && marks < 50) {
        cout << "D";
    }
    else {
        cout << "Fail";
    }
}
```

Optimized code -

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    int marks;
    cin >> marks;
    if (marks >= 90) { // if false, marks < 90, so no need to compare < 90
        cout << "A";
    }
    else if (marks >= 70) {
        cout << "B";
    }
    else if (marks >= 50) {
        cout << "C";
    }
    else if (marks >= 35) {
        cout << "D";
    }
    else {
        cout << "Fail";
    }
}
```

#### Nested if...else

```cpp
/*
You are given three integers, a, b, and c,
print which of these is the largest.
If two or more integers are equal and are the largest, 
the program should indicate that as well
*/
int main(){
    int a, b, c;
    cin >> a >> b >> c;
    if (a >= b) { // false -> a can't be largest
        if (a >= c) {
            cout << "A is the largest number";
        }
        else {
            cout << "C is the largest number";
        }
    }
    else if (b >=c) {
        cout << "B is the largest number";
    }
    else {
        cout << "C is the largest number";
    }
}
```

---

## Switch - Case

A different format of writing if..else where we know what can be the possible conditions.

Example -

```cpp
// Given the day number print which day it is of the week,
// Assume week starts from Monday and ends on Sunday
SINCE WE KNOW THAT THERE ARE 7 DAYS AND WHAT CAN BE THE POSSIBLE CASES, 
WE USE SWITCH STATEMENTS
#include<bits/stdc++.h>
using namespace std;

int main() {
    int day;
    cin >> day;
    switch(day) { // Directly goes to the day which matches the case 
// without checking the above cases, so it's better than if...else, but 
// ends up executing everything beyond the matched case if break keyword
// is not used.
        case 1:
            cout << "Monday" << endl;
            break; // ALWAYS EXITS THE OUTER LOOP, HERE SWITCH.
        case 2:
            cout << "Tuesday" << endl;
            break;
        case 3:
            cout << "Wednesday" << endl;
            break;
        case 4:
            cout << "Thursday" << endl;
            break;
        case 5:
            cout << "Friday" << endl;
            break;
        case 6:
            cout << "Saturday" << endl;
            break;
        case 7:
            cout << "Sunday" << endl;
            break;
        default:
            cout << "Invalid day" << endl; // no need to give break in 
// the last line of the code.
    }
}
```

---

## Loops

#### For Loop -

```cpp
// Take input of 10 numbers and print it the hard way.

int main() {
    int num;
    cin >> num;
    cout << num << endl;

    cin >> num;
    cout << num << endl; // and so on for 10 times
}
```

For the repetitive tasks like above, 

```cpp
// Take 10 integers as input and print them
#include<bits/stdc++.h>
using namespace std;

int main() {
    int num;
    // initializer, valid break statement, increment or decrement.
    // for(int i = 1; ; i++) invalid break statement.
    for(int i = 1; i <=10; i++) {
        cin >> num;
        cout << num << endl;
    }
}
```

Another Examples -

```cpp
// Printing all the numbers from 10 to 1
int main() {
    for (int i = 10; i >= 1; i--) {
        cout << i << endl;
    }
}

// Printing all the even numbers from 10 to 1
int main() {
    for (int i = 1; i >=1; i = i - 2) {
         cout << i << endl;   
 }
}

// print multiples of 5
int main() {
    for (int i = 5; i <= 100; i += 5) {
        cout << i << endl;
    }
    return 0;
}
```

#### While Loop -

Another syntactical way to write a for loop

```cpp
// print multiples of 5
int main() {
    for (int i = 5; i <= 100; i += 5) {
        cout << i << endl;
    }
    return 0;
}

// equivalent while loop
int main() {
    int i = 5;
    while (i <= 100) {
        cout << i << endl;
        i += 5;
    }
}
```

#### Do...while Loop -

```cpp
// print multiples of 5
int main() {
    int i = 5;
    do { // does the operations inside the do block before checking the 
// condition even once. Always execute atleast once.
        cout << i;
        i += 5;
    } while (i <= 100);
    return 0;
}
```

---

## Arrays

Why is it important ? What if I say, take these 5 numbers and do something with them. In that case, we can declare 5 variables or we can just use an array to store those 5 numbers.

Arrays is something which holds similar data-type variables, a sort of container in which we can keep similar data-type things.

> Note - To get the memory location of the variable we are building.
> 
> ```cpp
> int main() {
>     int num = 5;
>     cout << &num;
>     return 0;
> }
> ```

What arrays does is, it figures out a memory address and stores all the variables inside it in that sequential memory locations, or say, contiguous memory locations(kinds of bind them).

Syntax -

`int num[5] = {5, 2, 1, 3, 7};`

This means an array of 5 integers.

To access the elements - We use 0-based-indexing

```cpp
cout << num[0];
// To print all the numbers in the array, let's use a for loop
#include<bits/stdc++.h>
using namespace std;

int main() {
    int num[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i <= 4; i++) {
        cout << num[i] << endl;
    }
    return 0;
}
```

To take 5 numbers and store them in an array - 

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    int num[5];
    for (int i = 0; i <= 4; i++) {
        cin >> num[i];
        cout << num[i] << endl;
    }

    cout << "The size of the array is: " << sizeof(num) / sizeof(num[0]) << endl;
    return 0;
}
```

Let's say the size of an array is `N` and the last index is `N-1`.

> Note - When we try to access an `invalid memory location`, we get a runtime_error.

---

## Strings

Syntax to define a string -

```cpp
string str = "tufplus";
// OR
string str("tufplus");
```

Here, actually we have a character array of 8 characters. Why 8, here we have just 7 characters ?

The last character is `null` element, which tells that the string has ended.

So, under the hood, string is a character array of size 1 more than the size of the string (only under the hood). But remember that the string is of the same `size()` as it can be seen.

To print the size of the string - 

```cpp
string str = "tufplus";
cout << str.size(); // .size() is a method
```

Example to use the `.size()` method -

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    string str = "tufplus";
    int len = str.size();
    cout << len << endl; // prints 7 [ENTER]
    for (int i = 0; i <= len-1; i++) {
        cout << str[i] << " "; // prints t u f p l u s
    }
}
```

---

## Functions

`main` is also a function, which is the entry-level of our program.

Example -

```cpp
void print() { // this function doesn't return anything
    cout << "I am a print function";
}
int main() {
    print();
    return 0;
}
```

```cpp
void inputAndAddTwoNumbers() {
    int num1, num2;
    cin >> num1 >> num2;
    cout << num1 + num2;
}
int main() {
    inputAndAddTwoNumbers();
    inputAndAddTwoNumbers();
    return 0;
}
If input is 2 3 5 6. The output will be 5 [ENTER] 11.
```

A function which gives us something, that is, return us something.

```cpp
int sumOfTwoNumbers(int num1, int num2) { // Parametrized function
    int res = num1 + num2;
    return res; // returns something
}
int main() {
    int res = sumOfTwoNumbers(4, 5);
    cout << res;
    return 0;
}
```

> Note - `main` functions doesn't take any parameters.
> 
> No. of arguments passed while calling a function should be same as the no. of parameters in the function.
> 
> Also, we need functions to break the code into simpler bits (readable) and do repetitive tasks.

---

## Pass by Value and Reference

```cpp
void explainPassByValueAndReference(int x) {
    x = x + 10;
}
int main() {
    int num = 5;
    explainPassByValueAndReference(num);
    cout << num; // doesn't print 15, instead prints 5
    return 0;
}
```

This happens because we pass the copy of the value, not the actual variable and it's memory location. It simply takes the value of that variable and passed that. This is what we call as `Pass By Value` or `Passing the copy of the value`.

To change the num at it's original memory location, what we can do is -

```cpp
void explainPassByValueAndReference(int &x) {// it says that take the 
// original memory of the integer passed, it's expecting a memory of an
// integer, not the value of that integer.
    x = x + 10;
}
```

This is known as `Pass By Reference`.

> Note - We usually use `&x` instead of `x` since we need to make changes to the value of the variable at its original memory location. This way we don't end up creating many copies and use a lot of memory.

But there is an edge-case :

```cpp
#include <bits/stdc++.h>
using namespace std;
void explainPassByValueAndReference(int arr[]) {
    arr[0] = 100;
}
int main() {
    int arr[] = {6, 7, 8, 1, 2};
    explainPassByValueAndReference(arr);
    cout << arr[0];
    retrun 0;
}
```

When we pass on an array, it actually takes up the memory location or the reference to it.  OR We can also do this -

```cpp
void explainPassByValueAndReference(int *arr) { // here we wrote *arr 
// instead of arr[]
    arr[0] = 100;
}
int main() {
    int arr[] = {6, 7, 8, 1, 2};
    explainPassByValueAndReference(arr);
    cout << arr[0];
    retrun 0;
}
```

> Note - We cannot pass a copy in case of an array, as it ends up taking the memory location.

---
