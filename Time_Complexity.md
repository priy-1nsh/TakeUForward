# Complexity Analysis - Deep Analysis

With every code we write in DSA, or in software engineering, we have to do complexity analysis.
Two ways to analyse complexity -

1. Time Complexity
2. Space Complexity

# Time Complexity

When the code gets executed, it takes some time. **Does this time taken to execute our code define our code ?** Yes but how ?
You cannot judge your time by the time taken. In a cheaper machine, the time taken to execute the code may be higher due to it's lower specs, whereas in another high spec machine, the time taken to execute our code may be much lesser. Hence, we cannot define our code by the time taken to execute it by the server, which can be your personal computer or some other machine on the cloud.
Thus, time taken cannot be called as the time complexity, as it cannot deifne the quality of our code because it is dependent on the machine configuration or machine specs as well.
Hence, we can definitely say that - `Time Complexity != Time taken`.
So, what's Time Complexity ?
Imagine we have written a code and we are sending it to a windows machine along with the input. Now, an important thing is that - bigger the input size, slower the response.For example, if you order one item on a food delivery app, it will get delivered faster but if we order like 1000 items, it will be delivered much slower.
So, back to our example, let's say if we give an input of 1 in the windows machine, let's say it takes 10 seconds to get executed and get an output and an input of 2 takes 20 seconds to return the output on the same machine. So, here the change in the time taken of 10 seconds when we change the input is important.

If I have to plot a graph for this windows machine, let's say the graph looks like this -

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-21-00-46-23-image.png)

**Input Size** is on the X-axis whereas **Time taken** is on Y-axis. We can see that there is a change in Time taken according to the input size and we can measure that change by **THETA**.

To get this theta, we do -

```tex
\[
\frac{\text{Input}_2 - \text{Input}_1}{T_2 - T_1} = \text{Rate of Increase}
\]
```

The **theta** that we get, also known as**Rate of Change** is known as **Time-Complexity**. The rate of change will remain the same for the same machine when we give different types of inputs, the change seen will be same/similar and this rate of change is what is known as Time Complexity.

## How do we measure Time-Complexity when we write a code ?

There are certain notations to measure it, the one we will be using is known as **Big-O Notation**. It is denoted by the symbol **O**.

We cannot run every code we write and hence we need to analyse our code before running them on any machine.

Let's take an example of a code:

```arduino
FOR (I = 1; I <= 5; I++):
    PRINT(I)
```

If I ask you, how many operations is it taking ? Let's count it.

Initialization , check , printing , increment , check , print and so on. . .

We will see that it's taking roughly ~ 15 operations or 15 steps.

So, we can say that our time complexity is - **Big-O of 15**, that is, **O(15)**.

`TC -> O(15)`.

Let's take a general case:

```arduino
FOR(I = 1; I <= N; I++):
    PRINT(I)
```

Now, let's count the number of operations -

- 1st iteration - 1(initialization) + 1(check) + 1(print)

- 2nd Iteration - 1(increment) + 1(check) + 1(print)

- . . . and so one

We can see that on every iteration, we have 3 operations. Hence, for N iterations, we have **3N** operations. Hence, the time-complexity of this simple code can be written as - **Big - O of (10 cross 3)**, that is, **O(10 x 3)**.

There are some rules while writing Time-Complexity. What we had 

```arduino
FOR (INT I = 2; I <= N; I++):
    PRINT(I)
```

Would the TC be **O(3N + 1)** ? We will see.

## Rules for writing Time Complexity :

- Avoid Constants

- Consider the worst possible case

### Avoid Constants -

Let's say we write a code which gives us the Time-Complexity of **O(5N^3 + 3N+ 8)**.

If input size of say N = 1000 is given to you, then this will mean -> 5 X (1000)^3 + 3 X 1000 + 8 operations. But tell this - will this `+8` contribute that much ? It won't. Similarly, this `3 x 1000` is also very small compared to `5 x 10^9`, so will this matter ? Again No.

Hence, any term in our time complexity which doesn't have a significance, we can drop them. And, we can simply write that the time-complexity is **O(5N^3)**.

So, coming back to our last unanswered question - Will the TC be **O(3N + 1)** ? The answer is **No**. Since `1` is a constant and we will drop it as it doesn't contribute that much, and thus, the TC will be **O(3N)** still.

### Consider the worst possible case -

Remembering the grading-question we did -

```arduino
IF (MARKS >= 90):
    PRINT("A")
ELSE IF (MARKS >= 70):
    PRINT("B")
ELSE IF (MARKS >= 50):
    PRINT("C")
ELSE IF (MARKS >= 35):
    PRINT("D")
ELSE:
    PRINT("FAIL")
```

Consider the case - if the marks is 92 then how many operations this code performs ? - 

`check if MARKS >= 90` and `Printing A`, none of the other operations get performed. Hence, we can say that our TC is **O(2)**. But this is wrong as we need to consider the worst possible case.

Here, the worst possible case is when the  **Marks = 30**. Then, we can calculate the number of operations - `check-false`, `check-false`, `check-false`, `check-false`, `print`, so total of 5 operations. Hence, we can say that the TC is of **O(5)**.

We run the code to it's extreme and then figure out the time-complexity.

## Other types of Time Complexity Notations

- Big - O - ( The worst Complexity )

- Theta (theta_symbol) - ( The average complexity ) - Take the worst and the best case, add them and divide by 2 to find out the average.

- Omega (w) - The best possible complexity - the input which yields the least number of operations.

> Focus just on Big - O Notation

## Examples to calculate TC -

1 . 

```arduino
for (i = 1; i <= N; i++):
    for (j = 1; j <= N; j++):
        code which which takes less operations which we can ignore
```

Here, let's say the value of N is 3. Then, the outer loop will run for 3 times and the inner loop will run 3 times for each iteration of the outer loop. So,

```arduino
i = 1 {1, 2, 3}
i = 2 {1, 2, 3}
i = 3 {1, 2, 3}
```

We can clearly say that the number of operaions is - 3 + 3 + 3 = 3^2.

Thus, the TC is **O(N^2)**.

2 .

```arduino
for (i = 1; i <= N; i++):
    for (j = 1; j <= i; j++):
        code
```

Let's analyse the Time-Complexity for this one -

Let's say N = 5. Then, 

```arduino
i = 1 {1}
i = 2 {1, 2}
i = 3 {1, 2, 3}
i = 4 {1, 2, 3, 4}
i = 5 {1, 2, 3, 4, 5}
```

Number of Operations - 1 + 2 + 3 + 4 + 5 when N = 5.

For N, we can say number of operatons = 1 + 2 + 3 + ... + N = `N(N+1)/2` =`N^2/2 + N/2` which means **O(N^2/2 + N/2)** and for a very big N, it is **O(N^2/2)** WHICH YOU CAN STILL SAY AS - **O(N^2)** (dividing by 2 won't matter much if N is very large). But the exact TC will still be - **O(N^2/2 + N/2)**. But, on an average, let's say **O(N^2)**.

---

# Space Complexity

Definiton of Space Compexity is `Auxilliary Space + Input Space`.

- Auxilliary Space - Space that your code uses.

- Input Space - Data given by the operator.

Let's take an example -

```arduino
sum(a, b):
    c = a + b
    return c
```

Here, auxilliary space is `c` which is **O(1)** and the input space is `a` and `b` which is **O(2)**. Now, while determining the space-complexity, we neglect the input space as it is something given by the user and we cannot optimise it.

Let's take another example -

```arduino
sum(a, b):
    a = a + b
```

Our program is typically using the `a` , hence `a` will be considered under the auxilliary space now and not the input space. Usually we do not Modify the Inputs.

**NEVER MODIFY THE INPUTS GIVEN** - Bad Practice as in industry we can't really modify the inputs or datasets given to us.

Let's say if we define an array of size N, `int[] arr = new arr[N]`, our space-complexity will be **O(N)**.

There is other space-complexity as well - Recursive Stacks Spaces - We will talk about it in recursion.

---

# Quick practice of TC and SC on Patterns that We Did

- Pattern 1 -  TC : O(N^2) AS TWO FOR LOOPS ARE BEING USED AND BOTH ARE RUNNING FOR N TIMES. SC : `INT I` AND `INT J` BUT WE IGNORE CONSTANT, AS NO ADDIDTIONAL SPACE IS BEING USED , SC IS O(1).

- Patter 2 - **Time Complexity :** O(N2). As the outer loop runs for N time and the inner loop runs incrementally in each iteration(1+2+3+...+N), which is equal to (N*(N+1)/2). So, overall it is O(N2). **Space Complexity :** O(1). As no extra space is being used to print the patterns. 

- Pattern 3 - **Time Complexity :** O(N2). As the outer loop runs for N time and the inner loop runs incrementally in each iteration(1+2+3+...+N), which is equal to (N*(N+1)/2). So, overall it is O(N2).  
  
  **Space Complexity :** O(1). As no extra space is being used to print the patterns.

- Pattern 4 - **Time Complexity :** O(N2). As the outer loop runs for N time and the inner loop runs incrementally in each iteration(1+2+3+...+N), which is equal to (N*(N+1)/2). So, overall it is O(N2).  
  
  **Space Complexity :** O(1). As no extra space is being used to print the patterns.

- Pattern 5 - **Time Complexity :** O(N2). As the outer loop runs for N times and the inner loop runs in decreasing manner in each iteration(N + (N-1) + (N-2) + ... + 1), which is equal to (N*(N+1)/2). So, overall it is O(N2).  
  
  **Space Complexity :** O(1). As no extra space is being used to print the patterns.

- Pattern 6 - **Time Complexity :** O(N2). As the outer loop runs for N times and the inner loop runs in decreasing manner in each iteration(N + (N-1) + (N-2) + ... + 1), which is equal to (N*(N+1)/2). So, overall it is O(N2).  
  
  **Space Complexity :** O(1). As no extra space is being used to print the patterns.

- Pattern 7 - No matter how many for loops we have written inside the outer for loop, all of these inner loops take O(N) and the outer loop runs for N times and hence, TC is O(N^2) overall. And SC is O(1).

- Pattern 8 - TC : O(N^2), SC : O(1)

- Pattern 9 - TC : O(2N^2), SC : O(1)

- Pattern 10 - TC : O(N^2) + O((N-1)^2) = O(N^2) OVERALL, and SC : O(1).

- Pattern 11 - TC : O(2N^2), SC : O(1)

- Pattern 12 - 

```cpp
class Solution {
public:
    void pattern12(int n){ 
        // O(N)
        for (int i = 1; i <= n; i++) { 
            // OVERALL O(2*N)
            for (int j = 1; j <= i; j++) {
                cout << j;
            }
            for (int j = 1; j <= 2*n-2*i; j++) {
                cout << " ";
            }
            for (int j = i; j >= 1; j--) {
                cout << j;
            }
            cout << endl;
        }
    }
};
```

Hence, TC is (2N^2) and SC is O(1).

- Pattern 13 - TC is O(N^2) and SC is O(1)

- Pattern 14 - TC is O(N^2) and SC is O(1)

- Pattern 15 - TC is O(N^2) and SC is O(1)

- Pattern 16 - TC is O(N^2) and SC is O(1)

- Pattern 17 - TC is O(2N^2) and SC is O(1)

- Pattern 18 - TC is O(N^2) and SC is O(1)

- Pattern 19 - UpperHalf has TC of O(2N^2) and the lowerHlaf has TC of O(2N^2) so overall TC is O(4N^2) and SC is O(1)

- Pattern 20 - again the same - TC of O(4N^2) and SC of O(1)

- Pattern 21 - In the worst case you will print all the N characters in the inner loop which makes the TC of inner loop to be N and the outer loop is also running for N times so overall - TC is O(N^2) and SC is O(1)

- Pattern 22 - TC is O((2N -1)^2) and SC is O(1) since no extra space is being used.

---
