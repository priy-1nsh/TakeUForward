Identifying Patterns in a problem is very very important skill in problem-solving when we are solving Data Structures and Algorithms.

Solving the takeoff and landing problem on an airport requires an algorithm. If I am able to solve this problem for a single day, I will also be able to solve this problem for the 2nd, 3rd, 4th day... and every upcoming day as well using the same algorithm.

Basically, what we have done is - we identify a pattern and then replicate it multiple times. For repeating any task, we use a loop. In DSA, loops are very important. We break the problem into a smaller problem and then use the concept of loops. To understand loops in the best way, we use loops.

To solve the generic patterns, we have certain rules.

## Rules

1. Figure out the number of lines to be printed and write your outer loop on it. (Outer loop will be dependent on the number of lines basically)

2. Figure out what is happening at every line and try to connect with outer loop **if possible**. Write your inner loop on this basis.

3. Execute the print when needed, observe where the print statement needs to go.

4. Observe Symmetry ( optional )

---

**Pattern 1 - Given a value of N, print N number of lines containing stars `*`, each line containing N stars.**

PseudoCode -

```tex
for (i = 0 to N): (outer loop)

    for (j = 0 to N): (inner loop)

        print("*")

    print(newLine)
```

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    //Function to print pattren1
    void pattern1(int n) {

        // Outer loop will run for rows.
        for (int i = 0; i < n; i++) {

            // Inner loop will run for columns.
            for (int j = 0; j < n; j++) {
                cout << "*";
            }
            /* As soon as n stars are printed, move
            to the next row and give a line break.*/
            cout << endl;
        }
    }

};

int main() {
    int N = 4;

    //Create an instance of the Solution class
    Solution sol;

    sol.pattern1(N);

    return 0;
}
```

```java
class Solution {
    // Function to print pattern1
    public void pattern1(int n) {

        // Outer loop will run for rows.
        for (int i = 0; i < n; i++) {

            // Inner loop will run for columns.
            for (int j = 0; j < n; j++) {
                System.out.print("*");
            }
            /* As soon as n stars are printed, move
            to the next row and give a line break. */
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int N = 4;

        // Create an instance of the Solution class
        Solution sol = new Solution();

        sol.pattern1(N);
    }
}
```

**Pattern 2**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-00-07-20-image.png)

PseudoCode -

```arduino
// Remember to connect with outer loop if possible
IF N = 4
WE PRINT -
* -> I = 1
** -> I = 2
*** -> I = 3
**** -> I = 4
--------------------
FOR (I = 1 TO N):
    FOR (J = 1 TP I):
        PRINT("*")
    PRINT(\n)
```

```cpp
class Solution {
public:
    // Function to print pattern2
    static void pattern2(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 0; j <= i; j++) {
                cout << "*";
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            cout << endl;
        }
    }
};
```

```java
class Solution {
    // Function to print pattern2
    public static void pattern2(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 0; j <= i; j++) {
                System.out.print("*");
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int N = 5;

        // Create an instance of Solution class
        Solution sol = new Solution();

        sol.pattern2(N);
    }
}
```

**Pattern 3**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-01-01-32-image.png)

PseudoCode -

```tex
FOR (I = 1 TO N) {
    FOR (J = 1 TO I) {
        PRINT (J)
    }
    PRINT(NEWLINE)
}
```

```cpp
class Solution {
public:
    void pattern3(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                cout << j;
            }
            cout << endl;
        }
    }
};
```

```java
class Solution {
    // Function to print pattern3
    public static void pattern3(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 1; i <= n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 1; j <= i; j++) {
                System.out.print(j);
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int N = 5;

        // Create an instance of Solution class
        Solution sol = new Solution();

        sol.pattern3(N);
    }
}
```

**Pattern 4**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-01-21-46-image.png)

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:

    // Function to print pattern4
    static void pattern4(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 1; i <= n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 1; j <= i; j++) {
                cout << i;
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            cout << endl;
        }
    }
};

int main() {
    int N = 5;

    //Create an instance of Solution class
    Solution sol;

    sol.pattern4(N);

    return 0;
}
```

**Pattern 5**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-01-27-51-image.png)

PseudoCode -

```tex
N = 4
**** -> I = 1 PRINT 4 STARS
*** -> I = 2 PRINT 3 STARS  (N-I+1)
** -> I = 3 PRINT 2 STARS
* -> I = 4 PRINT 1 STAR
-------------------------------------
FOR (I = 1 TO N):
    FOR (J = 1 TO N-I+1):
        PRINT("*")
    PRINT(NEWLINE)
```

```cpp
class Solution {
public:
    void pattern5(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n-i+1; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
};
```

```java
class Solution {
    // Function to print pattern5
    public void pattern5(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 0; j < n-i; j++) {
                System.out.print("*");
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            System.out.println();
        }
    }
}
```

> Note - It doesn't matter if we start the count from 0 or 1. As long as the logic is correct it is fine. Outer and inner loop must function properly.

**Pattern 6**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-01-55-28-image.png)

Based on previous question -

```java
class Solution {
    public void pattern6(int n) {
        for (int i = 0; i < n; i++) { // 0 1 2 3 4
            for (int j = 1; j <= n - i; j++) { 
                // till 5-0, till 5-1, till 5-2, till 5-3, till 5-4
                System.out.print(j);
            }
            System.out.println();
        }
    }
}

class Main {
    public static void main(String[] args) {
        int n = 5;
        Solution sl = new Solution();
        sl.pattern6(n);
    }
}
```

```cpp
class Solution {
public:

    // Function to print pattern6
    static void pattern6(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 0; j < n-i; j++) {
                cout << j+1;
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            cout << endl;
        }
    }
};
```

**Pattern 7**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-02-33-51-image.png)

PseudoCode -

```tex
N = 4
   *     -> I = 1 
  ***    -> I = 2
 *****   -> I = 3
*******  -> I = 4

SPACES STARS SPACES
(N-I)  (2I-1) (N-I)
----------------------------------
FOR (I = 1 TO N):
    FOR (J = 1 TO N-I):
        PRINT(" ")
    FOR (J = 1 TO 2I-1):
        PRINT("*")
    FOR (J = 1 TO N-I):
        PRINT(" ")
    PRINT(NEWLINE)
----------------------------------
Although the 3rd for loop is unnecessary sinve we don't even see the end
spaces.
```

```cpp
class Solution {
public:

    // Function to print pattern7
    void pattern7(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            //This loop will print the spaces
            for(int j = 0; j < n-i-1; j++){
                cout << " ";
            }

            // This loop will print asterisk.
            for (int j = 0; j < 2*i+1; j++) {
                cout << "*";
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            cout << endl;
        }
    }
};
```

```java
class Solution {
    // Function to print pattern7
    public void pattern7(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // This loop will print the spaces
            for(int j = 0; j < n-i-1; j++){
                System.out.print(" ");
            }

            // Inner loop will print asterisks 
            for (int j = 0; j < 2*i+1; j++) {
                System.out.print("*");
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            System.out.println();
        }
    }
}
```

**Pattern 8**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-16-40-14-image.png)

PseudoCode - 

```tex
*******  -> i = 0
 *****   -> i = 1
  ***    -> i = 2
   *     -> i = 3
Spaces Stars Spaces
(i) (2N-1-2i) (i)
---------------------------
START
FOR (I = 0 TO < N):
    FOR (J = 0 TO < I):
        PRINT(" ")
    FOR (J = 0 TO < (2N-1-2I)):
        PRINT("*")
    PRINT(NEWLINE)
END
```

```cpp
class Solution {
public:
    void pattern8(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                cout << " ";
            }
            for(int j = 0; j < (2*n-1-2*i); j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
};
```

```java
class Solution {
    // Function to print pattern8
    public static void pattern8(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            //This loop will print the spaces
            for(int j = 0; j < i; j++){
                System.out.print(" ");
            }

            // This loop will print asterisk.
            for (int j = 0; j < 2*n-(2*i+1); j++) {
                System.out.print("*");
            }

            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int N = 5;

        // Create an instance of Solution class
        Solution sol = new Solution();

        sol.pattern8(N);
    }
}
```

**Pattern 9**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-17-05-38-image.png)

PseudoCode -

```tex
We can clearly see that pattern 9 is just pattern 7 followed by pattern 8
Hence we are gonna use the same code of pattern 7 and pattern 8.
-----------------------------------
pattern7(n);
pattern8(n);
```

```cpp
class Solution {
private:
    void pattern7(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n-i; j++) {
                cout << " ";
            }
            for (int j = 1; j <= 2*i - 1; j++) {
                cout << "*";
            }
            for (int j = 1; j <= n-i; j++) {
                cout << " ";
            }
            cout << endl;
        }
    }

    void pattern8(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                cout << " ";
            }
            for(int j = 0; j < (2*n-1-2*i); j++) {
                cout << "*";
            }
            cout << endl;
        }
    }

public:
    void pattern9(int n) {
        pattern7(n);
        pattern8(n);
    }
};
```

> Note - We wrote our functions as `private` so that nobody can use it outside this class `Solution`. We need to write `private` only once and all the methods under it will become `private` until it hits the keyword `public`.
> 
> **Important Rule** - Observe Symmetry. 

**Pattern 10**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-23-16-05-image.png)

> In contrast, languages like **C** or **JavaScript** allow `if (i % 2)` because they treat non-zero values as `true`. But **Java** does not allow this.

PseudoCode -

```tex
Observe symmetry.
Clearly, it's -
pattern2(n);
pattern5(n-1);
```

```cpp
class Solution {
private:
    void pattern2(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j <= i; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
    void pattern5(int n) {

        // Outer loop which will loop for the rows.
        for (int i = 0; i < n; i++) {

            // Inner loop which loops for the columns.
            for (int j = 0; j < n-i; j++) {
                cout << "*";
            }
            /* As soon as stars for each iteration are printed,
             move to the next row and give a line break */
            cout << endl;
        }
    }
public:
    void pattern10(int n) {
        pattern2(n);
        pattern5(n-1);
    }
};
```

**Pattern 11**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-12-23-53-34-image.png)

PseudoCode -

```tex
N = 5
1             -> I = 1        START = 1 
0 1           -> I = 2        IF(I % 2 == 0) START = 0
1 0 1         -> I = 3
0 1 0 1       -> I = 4        FLIP START = 1-START
1 0 1 0 1     -> I = 5
-------------------------------------------------------
FOR (I = 1 TO <= N):
    START = 1
    IF (I%2 == 0):
        START = 0
    FOR (J = 1 TO <= I):
        PRINT (START + " ")
        START = 1 - START
    PRINT(NEWLINE)
```

```cpp
class Solution {
   public:
    void pattern11(int n) {
        for (int i = 1; i <= n; i++) {
            int start = 1;
            if (i % 2 == 0) start = 0;
            for (int j = 1; j <= i; j++) {
                cout << start << " ";
                start = 1 - start;
            }
            cout << endl;
        }
    }
};
```

Alternative -

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    //Function to print pattern11
    void pattern11(int n) {
        // First row starts by printing a single 1.
        int start = 1;

        // Outer loop for the no. of rows
        for (int i = 0; i < n; i++) {

            /* if the row index is even then 1
            is printed first in that row.*/
            if (i % 2 == 0) start = 1;

            /* if odd, then the first 0 
            will be printed in that row*/
            else start = 0;

            /* We alternatively print 1's and 0's 
            in each row by using inner for loop*/
            for (int j = 0; j <= i; j++) {
                cout << start << " ";
                start = 1 - start;
            }

            /*As soon as the numbers for each 
            iteration are printed, we move to the
            next row and give a line break */
            cout << endl;
        }
    }

};

int main() {
    int N = 5;

    //Create an instance of Solution class
    Solution sol;

    sol.pattern11(N);

    return 0;
}
```

---

## Hard

**Pattern 12**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-13-00-08-42-image.png)

PseudoCode -

```tex
numbers | spaces | numbers
1        1           -> i = 1
12      21           -> i = 2
123    321           -> i = 3
1234  4321           -> i = 4
1234554321           -> i = 5
---------------------------------
FOR (I = 1 TO <= N):
    FOR (J = 1 TO <= I):
        PRINT(J)
    FOR (J = 1 TO <= 2N-2I):
        PRINT(" ")
    FOR (J = I TO >= 1):
        PRINT(J)
    PRINT(NEWLINE)
```

```cpp
class Solution {
public:
    void pattern12(int n) {
        for (int i = 1; i <= n; i++) {
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

**Pattern 13**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-13-00-46-55-image.png)

PseudoCode -

<img src="file:///C:/Users/DEll/OneDrive/Desktop/Take%20U%20Forward/PseudoCode%20Optional/WhatsApp%20Image%202025-07-19%20at%2013.25.16_64a14ded.jpg" title="" alt="" width="631">

```tex
N = 4

1               I = 1
2 3             I = 2
4 5 6           I = 3
7 8 9 10        I = 4
-----------------------------
FOR (I = 1 TO <= N):
    FOR (I = 1+((I-1)*I/2)) TO <= (I*(I+1)/2)):
        PRINT (J + " ")
    PRINT (NEWLINE)
```

```cpp
class Solution {
   public:
    void pattern13(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1 + ((i * (i - 1)) / 2);
                 j <= ((i * (i + 1) / 2)); j++) {
                cout << j << " ";
            }
            cout << endl;
        }
    }
};
```

Another Approach -

```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    //Function to print pattern13
    void pattern13(int n) {
        // starting the number
        int num =1;

        // Outer loop for the number of rows.
        for(int i=1;i<=n;i++){

            /*Inner loop will loop for i times and
            print numbers increasing by 1 each time*/
            for(int j=1;j<=i;j++){
                cout<<num<<" ";
                num =num+1;
            }
            /* As soon as the numbers for each iteration
            are printed, we move to the next row and give
            a line break otherwise all numbers would get
            printed in 1 line*/
            cout<<endl;
        }
    }

};

int main() {
    int N = 5;

    //Create an instance of Solution class
    Solution sol;

    sol.pattern13(N);

    return 0;
}
```

**Pattern 14**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-13-02-29-00-image.png)

> Note that characters are stored as ASCII values.
> 
> Example -
> 
> ```cpp
> char ch = 'A';
> char ch1 = ch + 3;
> cout << ch1; // prints D
> ```

> Also, note that we don't necessarily require to run loops on integers, we can run them on characters as well.

PseudoCode -

```tex
N = 4

A                 -> I = 0 ('A' TILL 'A' + 0)
A B               -> I = 1 ('A' TILL 'A' + 1)
A B C             -> I = 2
A B C D           -> I = 3
--------------------------------------
FOR (I = 0 TO N-1):
    FOR (CHAR CH = 'A'; CH <= 'A' + I; CH++):
        PRINT(CH + " ")
    PRINT(NEWLINE)
```

```cpp
class Solution {
public:
    void pattern14(int n) {
        for (int i = 0; i < n; i++) {
            for (char ch = 'A'; ch <= 'A' + i; ch++) {
                cout << ch;
            }
            cout << endl;
        }
    }
};
```

**Pattern 15**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-19-13-38-25-image.png)

PseudoCode -

```tex
LET N = 4
ABCD      -> i = 1     'A' TILL 'A' + N - I
ABC       -> i = 2
AB        -> i = 3
A         -> i =4
--------------------------------
FOR(INT I = 1 TILL <= N):
    FOR (CHAR CH = 'A' TILL <= 'A' + N - I):
        PRINT(CH)
    PRINT(NEWLINE)
```

```cpp
class Solution {
public:
    void pattern15(int n) {
        for(int i = 1; i <= n; i++) {
            for (char ch = 'A'; ch <= 'A' + n - i; ch++) {
                cout << ch;
            }
            cout << endl;
        }
    }
};
```

**Pattern 16**

![](C:\Users\DEll\AppData\Roaming\marktext\images\2025-07-19-13-45-10-image.png)

PsedoCode

```tex
N = 4
A         -> I = 0
BB        -> I = 1
CCC       -> I = 2
DDDD      -> I = 3
-----------------------------
FOR (INT I = 0 TILL < N):
    FOR (INT J = 0 TILL <= I):
        PRINT('A' + I)
    PRINT(NEWLINE)
---------------------------------
1. Changed inner loop to j <= i to print correct number of characters per line.

2. Moved char ch = 'A' + i; outside the inner loop for efficiency (no need to recalculate in every iteration).
```

```cpp
class Solution {
public:
    void pattern16(int n) {
        for (int i = 0; i < n; i++) {
            char ch = 'A' + i; // Calculate the character for the current row
            for (int j = 0; j <= i; j++) { // j <= i to get (i+1) times
                cout << ch;
            }
            cout << endl;
        }
    }
};
```

**Pattern 17**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-19-16-33-39-image.png)

PseudoCode -

```tex
LET N = 4
   A      -> I = 1
  ABA     -> I = 2
 ABCBA    -> I = 3
ABCDCBA   -> I = 4
----------------------------
FOR (INT I = 1 TILL <= N):
    CHAR CH = 'A'
    FOR (INT J = 1 TILL <= I):
        PRINT (" ")

    FOR (INT J = 1 TILL J <= 2I-1):
        PRINT (CH)
        IF (J < I) CH++
        ELSE (CH >= I) CH--

    FOR (INT J = 1 TILL <= I):
        PRINT (" ")

    PRINT(NEWLINE)
```

```cpp
class Solution {
public:
    void pattern17(int n) {
        for(int i = 1; i <= n; i++) {
            char ch = 'A';
            for (int j = 1; j <= n-i; j++)
                cout << " ";

            for (int j = 1; j <= 2*i-1; j++) {
                cout << ch;
                if (j < i)
                    ch++;
                else
                    ch--;
            }

            for (int j = 1; j <= n-i; j++)
                cout << " ";

            cout << endl;
        }
    }
};
```

**Pattern 18**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-19-17-18-49-image.png)

PseudoCode -

```tex
LET N = 4
D             -> I = 0
CD            -> I = 1
BCD           -> I = 2
ABCD          -> I = 3
-----------------------
CHAR CH = 'A' + N - 1
FOR (INT I = 0; I < N; I++):
    FOR (CHAR EL = CH - I; EL <= CH; EL++):
        PRINT(EL)
    PRINT(NEWLINE)
```

```CPP
class Solution {
public:
    void pattern18(int n) {
        char ch = 'A' + n - 1;
        for (int i = 0; i < n; i++) {
            for (char el = ch - i; el <= ch; el++) {
                cout << el << " ";
            }
            cout << endl;
        }
    }
};
```

**Pattern 19**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-19-17-39-28-image.png)

PseudoCode -

```tex
Basic Pattern - stars spaces stars
LET N = 4
********
***  ***
**    **
*      *
*      * I = 0
**    ** I = 1
***  *** I = 2
******** I = 3
---------------------------
UPPERHALF
FOR (I = 0 TILL <= N-1):
    FOR (INT J = 1 TILL J <= N-I):
        PRINT("*")
    FOR (INT J = 0 TILL < 2I):
        PRINT(" ")
    FOR (INT J = 1 TILL J <= N-I):
        PRINT("*")
    PRINT(NEWLINE)

LOWERHALF
I + 1 STARS, 2N - 2 - 2I SPACES, I + 1 STARS
FOR (INT I = 0 TILL I < N):
    FOR (INT J = 1 TILL <= I + 1):
        PRINT("*")
    FOR (INT J = 1 TLL <= 2N-2-2I):
        PRINT(" ")
    FOR (INT )J = 1 TILL <= I + 1):
        PRINT("*")
```

```cpp
class Solution {
private:
    void printUpperHalf(int n) {
        for (int i = 0; i < n; i++) {
            for(int j = 1; j <= n - i; j++) {
                cout << "*";
            }
            for(int j = 0; j < 2*i; j++) {
                cout << " ";
            }
            for(int j = 1; j <= n - i; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
    void printLowerHalf(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i + 1; j++) {
                cout << "*";
            }
            for (int j = 2*n-2-2*i; j > 0; j--) {
                cout << " ";
            }
            for (int j = 0; j < i+1; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }

public:
    void pattern19(int n) {
        printUpperHalf(n);
        printLowerHalf(n);
    }
};
```

**Pattern 20**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-20-00-15-06-image.png)
PseudoCode -

```ar
N = 4
STARS SPACES STARS
*      * I = 0  (I+1)STARS (2N-2-2I)SPACES (I+1)STARS    |
**    ** I = 1  (I+1)STARS (2N-2-2I)SPACES (I+1)STARS    |
***  *** I = 2  (I+1)STARS (2N-2-2I)SPACES (I+1)STARS    |  upperHalf(n)
******** I = 3  (I+1)STARS (2N-2-2I)SPACES (I+1)STARS    |
***  *** I = 0  (N-I)STARS (2I + 2)SPACES (N-I)STARS            \                                   
**    ** I = 1  (N-I)STARS (2I + 2)SPACES (N-I)STARS            \    lowerHalf(n-1)                                
*      * I = 2  (N-I)STARS (2I + 2)SPACES (N-I)STARS            \                                   
---------------------
UPPERHALF (N):
FOR (INT I = 0 TILL I < N):
    FOR (INT J = 1 TILL <= I + 1):
        PRINT ("*")
    FOR (INT J = 1 TILL <= 2N-2-2I):
        PRINT (" ")
    FOR (INT J = 1 TILL <= I + 1):
        PRINT ("*")
    PRINT(NEWLINE)

LOWERHALF(N-1):
FOR (INT I = 0 TILL < N):
    FOR (INT J = 1 TILL <= N -I):
        PRINT("*")
    FOR (INT J = 1 TILL <= 2I+2):
        PRINT(" ")
    FOR (INT J = 1 TILL <= N -I):
        PRINT("*")
    PRINT(NEWLINE)
```

```cpp
class Solution {
private:
    void upperHalf(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 1; j <= i + 1; j++) {
                cout << "*";
            }
            for (int j = 1; j <= 2*n - 2 - 2*i; j++) {
                cout << " ";
            }
            for (int j = 1; j <= i + 1; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
    void lowerHalf(int n) {
        for (int i = 0; i < n; i++) {
            for (int j = 1; j <= n - i; j++) {
                cout << "*";
            }
            for (int j = 1; j <= 2*i+2; j++) {
                cout << " ";
            }
            for (int j = 1; j <= n - i; j++) {
                cout << "*";
            }
            cout << endl;
        }
    }
public:
    void pattern20(int n) {
        upperHalf(n);
        lowerHalf(n-1);
    }
};
```

Another Approach -

```cpp
class Solution {
public:
    //Function to print pattern20
    void pattern20(int n) {
        // Initialising the spaces.
        int spaces = 2*n-2;

        // Outer loop to print the row.
        for(int i = 1; i <= 2*n-1; i++){

            // Stars for first half
            int stars = i;

            // Stars for the second half.
            if(i > n) stars = 2*n - i;

            //For printing the stars
            for(int j = 1; j <= stars; j++){
                cout<<"*";
            }

            //For printing the spaces
            for(int j = 1; j <= spaces; j++){
                cout<<" ";
            }

            //For printing the stars
            for(int j = 1; j <= stars; j++){
                cout<<"*";
            }

            //Give a line break for new row.
            cout<<endl;

            if(i<n) spaces -=2;
            else spaces +=2;
        }
    }
};
```

**Pattern 21**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-20-01-39-29-image.png)

PseudoCode -

```arduino
N = 4
****  I = 1
*  *  I = 2
*  *  I = 3
****  I = 4
----------------
FOR (INT I = 1 TILL I <= N):
    IF (I == 1 OR I == N):
        FOR(INT J = 1 TILL J <= N):
            PRINT("*")
    ELSE:
        PRINT("*")
        FOR (INT J = 1 TILL J <= N - 2):
            PRINT(" ")
        PRINT("*")
    PRINT(NEWLNE)
```

OR

```arduino
FOR (INT I = 1 TILL I <= N):
    IF (I == 1 OR I == N):
        FOR(INT J = 1 TILL J <= N):
            PRINT("*")
    ELSE:
        FOR(INT J = 1 TILL <= N):
            IF (J == 1 OR J == N) PRINT("*")
            ELSE PRINT (" ")
    PRINT(NEWLNE)
```

```cpp
class Solution {
public:
    void pattern21(int n) {
        for (int i = 1; i <= n; i++) {
            if (i == 1 || i == n) {
                for (int j = 1; j <= n; j++) {
                    cout << "*";
                }
            }
            else {
                cout << "*";
                for (int j = 1; j <= n-2; j++) {
                    cout << " ";
                }
                cout << "*";
            }
            cout << endl;
        }
    }
};
```

**Pattern 22**

![](C:\Users\DEll\OneDrive\Desktop\Take%20U%20Forward\PseudoCode%20Optional\2025-07-20-01-58-19-image.png)

PsedoCode -

```arduino
N = 4
4444444   I = 0    
4333334   I = 1
4322234   I = 2
4321234   I = 3
---------------------------
4322234   I = 4
4333334   I = 5
4444444   I = 6
---------------------------
FOR (INT I = 0 TILL < 2N-1):
```