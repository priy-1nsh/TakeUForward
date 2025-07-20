# JAVA OOPS Basics

*Why do we need to know Object Oriented Programming ?*

**Problem Statement** - Complete the function `printNumber` which takes an integer input from the user and prints it on the screen.

```java
class Solution {
// we are already given the scanner object in the parameter of the function
    public void printNumber(Scanner sc) {
        int num = sc.nextInt();
        System.out.println(num);
    }
}
```

But in the above code, how is it running ? This particular class `Solution` doesn't have a `main` method.

---

## Classes and Objects -

We remember we have to create a class with the same name as the file name.

`Class` is nothing but a <mark>blueprint in java</mark> which has everything you want to do. Every function/method/functionality we write will always be inside a class because **java is an object-oriented programming language**.

`public private protected` - These are the **access-specifiers**. `public` means this class is available everywhere. `private` means it is only accessible to the current class.

`protected` means it is accessible only to the current package and all the other sub-packages that you have.

Thus, 

`public -> everywhere`

`private -> current class`

`protected -> current package and all other sub-packages`

Example -

```java
public class Basics { // this class is accessible everywhere, anyone can 
// use this class
    public static void main(String[] args) {

    }
}
```

But if we don't write `public` before the `class Basics`, then by default, the class is `package-private`, that is, it is only accessible under this package 'Basics'.

 `main` method/function is the **default entry-point** of the execution.

`static` is a keyword which allows us to use this `main` method without creating an object, which means we can call it from anywhere by simply writing `Basics.main`(className.methodName).

`void` means that this `main` method doesn't need to return anything.

`String[] args` are the command-line arguments, for if we are taking input via command-line.

*What is an object ?*

```java
class Test { // we defined a class here
    public static void printTest() {
        System.out.println("Hello");
    }
}
```

Now, how do we trigger the printTest method ?

We can see that `printTest()` is a `static` method.So, in order to access it, we just write `Test.printTest();`.

```java
class Basics {
    public static void main(String[] args) {
        Test.printTest(); // prints "Hello"
    }
}
```

> Note - This means if the method is `static`, we don't need to create an object.

*So, when do we create objects and what for ?*

If we remove the `static` keyword from the definition of the `printTest` method, we will get an error - `non-static method printTest() cannot be referenced from a static context`. This means to reference/access a non-static method, we need to create an object of that class in which that method is present.

**Object** basically gives you an instance of the class, more like a copy of that class.

Syntax to create an object - 

```java
Test test = new Test();
```

> We usually name the object name same as the class name so that it is easily identifiable.

Now, to use the `printTest()` method, we write - 

```java
test.printTest();
```

*Why do we actually need an object ?*

 Let's understand using an example -

> First note that, if we are not writing any access specifier with the declaration of the variable, then it is by default `public`, that is, if I write `int num = 10` then `num` is by-default a `public` variable.

```java
class Test {
    int age;
    public void assignAge(int num) {
        age = num;
    }
}

class Basics {
    public static void main(String[] args) {
        Test test1 = new Test();
        test1.assignAge(10);

        Test test2 = new Test();
        test2.assignAge(19);

        System.out.println(test1.age); // prints 10
        System.out.println(test2.age); // prints 19

    }
}
```

This happend because `test1` and `test2` are two different instances of the same class `Test`. Any work done on one instance doesn't affect the other instance. That's why objects are important, because in this way, we have a certain set of code which could be used by anyone and it doesn't impact any use.

Analogy - When you go to buy a car, they already have a design ready, they just make the copy and give it to you by making probably some customisations.

Thus, we can say that - Initially we had a `Solution` class. But there was some code which we couldn't see, probably on the backend. It would be something like -

```java
class Solution {
// we are already given the scanner object in the parameter of the function
    public void printNumber(Scanner sc) {
        int num = sc.nextInt();
        System.out.println(num);
    }
}

// the code we can't see
import java.util.Scanner;
class Basics {
    public static void main(String[] args) {
        Scanner sc = new Scanner();

        Solution sl = new Solution();
        sl.printNumber(sc);
    }
}
```

> Note that we always write the **data-type** of the parameter we need to pass inside the method while writing the definition of that method.

---

## Methods and Functions

Anything that returns anything.

```java
class Test {
    int age;
    // void method
    public void assignAge(int num) {
        age = num;
    }
}

class Basics {
    // using `private` keyword to make the method accessible only
    // inside the Basics class
/* Also this method can be called only when it is static itself,like 
it's ofcourse as we are not creating an object of this class under the 
same class. */
    private static void prinnt() {
        System.out.println("prinnt is called.");
    }

    public static void main(String[] args) {
        // To access a private method, we can use
        prinnt();

        Test test1 = new Test();
        test1.assignAge(10);

        Test test2 = new Test();
        test2.assignAge(19);

        System.out.println(test1.age); // prints 10
        System.out.println(test2.age); // prints 19

    }
}
```

> Now, this `prinnt` method can't be called from any other class since it's a private method.

*A private Method with a return type -*

```java
class Basics {
    // a prvate method that can only be accessed from within this Basics
    // class
    private static int num() {
        return 10;
    }

    public static void main(String[] args) {
        System.out.println(num()); // prints 10
    }
}
```

> `static` signifies where we are trying to access that method or a variable. Read the above content.

#### Parametrized Methods -

Example -

```java
class Test {
    public int sum(int num1, int num2) {
        return num1 + num2;
    }
}

class Basics {
    public static void main() {
        Test test = new Test();
        System.out.println(test.sum(10, 15));
    }    
}
```

Here, such functions like `sum(int num1, int num2)` are known as parametrized functions.

---

## Constructor (default and parametrised)

```java
class Test {

}
class Basics {
    public static void main(String[] args) {
        Test test = new Test();
    }
}
```

When we create an object `Test test = new Test();` , we are calling a default constructor which is not visible to you. Basically, here we are calling a method, a default `Test` method. But we can also change the default function which will be called when we create a new object.

```java
class Test {
    // This is how we over-write the default constructor of a class
    // which is nothing but the method which is called when a new 
    // object is created - remember this syntax to change the default
    // constructor
    public Test() {
        System.out.println("Test constructor called.");
    }
    public void printHello() {
        System.out.println("Hello");
    }
}
class Basics {
    public static void main(String[] args) {
        Test test = new Test(); // prints `Test constructor called`
        test.printHello(); // prints `Hello`
    }
}
```

*Now, why do we need a default constructor ?*

Suppose you are working to make software for a bank, and we want to deposit 100 rupees in the balance if the user opens a bank accout in the bank.

```java
class BankAccount {
    double balance; // assign 0 or a decimal garbage value to `balance`
    public BankAccout {
        balance = 100.0;
    }

    public void printBalance() {
        System.out.println(balance);
    }
}

class Basics {
    public static void main(String[] args) {
        BankAccount test = new BankAccount();
        test.printBalance(); // prints 100.0
    }    
}  
```

**Parametrized Constructors**

Let's understand it by using an example - let's say we are assigning the initial balance in the default-consructor according to the branch-name of the bank where we are opening our bank account. In such cases, we use **Parametrized Constructors**.

```java
class BankAccount {
    double balance;
    public BankAccount(_balance) {
        balance = _balance;
    }

    public void printBalance() {
        System.out.println(balance);
    }
}
class Basics {
    public static void main(String[] args) {
        BankAccount test = new BankAccount(100.0); // Parametrized constructor
        test.printBalance();
    }
}
```

When we created the BankAccount on our end (here, creating a BankAccount object) using the parametrized constructor, we ended up sending the value.

> Thus, `public className {}` is known as the default constructor, whereas, `public className(_variableName) {}` is known as the parametrized constructor. Default and Parametrised Constructors basically change the default method to be called when creating an object.

We can have many constructors for the same class and we can have many parameters to be passed inside the constructor.

For example -

```java
class BankAccount {
    double balance;
    String accountType;

    // default constructor to be called 
    public BankAccount (double _balance) {
        balance = _balance;
        accountType = "Savings";
    }

    // parametrised constructor which also takes the accountType
    public BankAccount(double _balance, String _accountType){
        balance = _balance;
        accountType = _accountType;
    }

    public void printBalance() {
        System.out.println(balance);
    }

    public void printAccountType() {
        System.out.println(accountType);
    }
}


class Basics {
    public static void main(String[] args) {
        BankAccount accountPerson1 = new BankAccount(200.0);
        accountPerson1.printBalance(); // prints 200.0
        accountPerson1.printAccountType(); // prints "Savings"

        BankAccount accountPerson2 = new BankAccount(200.0, "Current");
        accountPerson2.printBalance(); // prints 200.0
        accountPerson2.printAccountType(); // prints "Current"
    }
}
```

Thus we can have more than one default constructors as well which is gonna support multiple use-cases.

`.this` keyword -

```java
class BankAccount {
    double balance;
    String accountType;

    // default constructor to be called 
    public BankAccount (double balance) {
        this.balance = balance; // this.balance means the balance of this
// current object. this.balance is the one created inside the class
// using `double balance` and balance is the balance which we passed 
// inside the parametrized constructor.
        this.accountType = "Savings";
    }

    // parametrised constructor which also takes the accountType
    public BankAccount(double balance, String accountType){
        this.balance = _balance;
        this.accountType = _accountType;
    }

    public void printBalance() {
        System.out.println(balance);
    }

    public void printAccountType() {
        System.out.println(accountType);
    }
}


class Basics {
    public static void main(String[] args) {
        BankAccount accountPerson1 = new BankAccount(200.0);
        accountPerson1.printBalance(); // prints 200.0
        accountPerson1.printAccountType(); // prints "Savings"

        BankAccount accountPerson2 = new BankAccount(200.0, "Current");
        accountPerson2.printBalance(); // prints 200.0
        accountPerson2.printAccountType(); // prints "Current"
    }
}
```

Basically, `this.` refers to the current object. So, `this.balance` refers to the `balance` of the object we created whereas the one we pass inside the constructor is different which gets assigned to the object's `balance` by using `this.balance(the current object's balance) = balance(the one we passed inside the constructor);`

So, we can say instead of writing `_balance` as the parameter of the constructor and assigning it to the current object's balance by writing `balance(current object's balance) = _balance(passed as the parameter);`, we write `this.balance = balance;`.

---

## Encapsulation (getter and setter)

If we want to print the balance of the person, we can write -

```java
System.out.println(accountPerson1.balance); // prints 200.0
```

But don't you think that it's risky ?

And if I write -

```java
accountPerson1.balance = 0.0;
```

It changes the `balance` of the person1.

So, what we can do here is - trun the access to these variables to `private`. 

```java
class BankAccount {
    // we turn the access of these variables to private.
    private double balance;
    private String accountType;

    // default constructor to be called 
    public BankAccount (double balance) {
        this.balance = balance;
        this.accountType = "Savings";
    }

    // parametrised constructor which also takes the accountType
    public BankAccount(double balance, String accountType){
        this.balance = balance;
        this.accountType = accountType;
    }

    public void printBalance() {
        System.out.println(balance);
    }

    public void printAccountType() {
        System.out.println(accountType);
    }
}

class Basics {
    public static void main(String[] args) {
        BankAccount accountPerson1 = new BankAccount(200.0);
        accountPerson1.printBalance(); // prints 200.0
        accountPerson1.printAccountType(); // prints "Savings"

        BankAccount accountPerson2 = new BankAccount(200.0, "Current");
        accountPerson2.printBalance(); // prints 200.0
        accountPerson2.printAccountType(); // prints "Current"

        accountPerson1.balance = 0.0; // Will give the ERROR that the 
// variable balance has the private access.
    }
}
```

This is known as **encapsulation**. That is, the data is now encapsulated to the current class.

Then, the question arises - How do we change it ?

This introduces the concept of **getters and setters**.

```java
class BankAccount {
    private double balance;
    private String accountType;

    public BankAccount (double balance) {
        this.balance = balance;
        this.accountType = "Savings";
    }

    public BankAccount(double balance, String accountType){
        this.balance = balance;
        this.accountType = accountType;
    }

    public void printBalance() {
        System.out.println(balance);
    }

    public void printAccountType() {
        System.out.println(accountType);
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }
}

class Basics {
    public static void main(String[] args) {
        BankAccount accountPerson1 = new BankAccount(200.0);
        accountPerson1.printBalance(); // prints 200.0
        accountPerson1.printAccountType(); // prints "Savings"

        BankAccount accountPerson2 = new BankAccount(200.0, "Current");
        accountPerson2.printBalance(); // prints 200.0
        accountPerson2.printAccountType(); // prints "Current"

        accountPerson1.setBalance(0.0); `SETTER`
        accountPerson1.printBalance(); // prints 0.0
    }
}
```

This is known as `SETTER`. Basically, this is how we set/modify the variable depending on the use cases.

For Example -

```java
class BankAccount {
    private double balance;
    private String password;
    private String correctPassword;
    public BankAccount (double balance) {
        this.balance = balance;
    }
    public void setBalance (double balance, String password) {
        if (password == correctPassword) {
            this.balance = balance;
        }
    }

    public void printBalance() {
        System.out.println(balance);
    }
}


// use-case
class Basics {
    public static void main(String[] args) {
        BankAccount accountPerson1 = new BankAccount(100.0);
        accountPerson1.printBalance(); // prints 0.0
        accountPerson1.setBalance(900.0, "Rainbow@31"); // sets balance to 900.0
        accountPerson1.printBalance(); // prints 900.0
    }
}
```

This is just an example. Depending on the use-cases, we allow the modification.

**Encapsulation** doesn't allow you to directly modify. You have to communicate **via Methods**.

Similarly, we can write a `GETTER` method.

```java
public void getBalance {
    // logic of checking if the person trying to access is the account's owner or not.
    return balance; // returns the object's balance
}
```

Thus, by using **Encapsulation**, we don't allow direct modification. Getting and setting of the encapsulated variables can only be done by methods which have logic written inside them.

---

## Inheritance ( Parent-child concept )

Let's take the example of Car -

```java
class Car {
    private String numberOfCar; // encapsulated variable numberOfTheCar of this object

    // default parametrised-constructor to be called when we purchase a new Car
    public Car(String numberOfCar) {
        this.numberOfCar = numberOfCar;
    }

    public void printCarNumber() {
        System.out.println(numberOfCar);
    }
}


class Basics {
    public static void main(String[] args) {
        Car car = new Car("KA01k9876"); // bought a new car
        car.printCarNumber();
    }
}
```

Now, let's suppose we also have a Bus. Then,

```java
class Car {
    private String numberOfCar;

    // default constructor
    public Car(String numberOfCar) {
        this.numberOfCar = numberOfCar;
    }

    // GETTER
    public void printCarNumber() {
        System.out.println(numberOfCar);
    }

    // Honk method
    public void honk() {
        System.out.println("HONK!!!!!!!!!!!!!");
    }
}


class Bus {
    private String numberOfBus;

    // default constructor
    public Bus(String numberOfBus) {
        this.numberOfBus = numberOfBus;
    }

    // GETTER
    public void printBusNumber() {
        System.out.println(numberOfBus);
    }

    // Honk method
    public void honk() {
        System.out.println("HONK!!!!!!!!!!!!!");
    }
}

class Basics {
    public static void main(String[] args) {
        Car car = new Car();
        car.printCarNumber();
        car.honk();

        Bus bus = new Bus();
        bus.printBusNumber();
        bus.honk();
    }
}
```

But, here we can observe that `honk()` is the same functionality in both `Car` and `Bus` classes. So, how can we use the same `honk()` for both the `Car` and the `Bus` ? Like how can we use the same design in some other class (same design in multiples classes) ? 

What we do is shift the similar functionality in some other class, let's say `Vehicle`, and add the same functionality/method `honk()` in that class and remove the repetitive same functionality from both the other classes. We will try to reuse the functionalities of `Vehicle` class in some other class by simple writing the `extends` keyword.

Example -

```java
class Vehicle {
    // Honk method
    public void honk() {
        System.out.println("HONK!!!!!!!!!!!!!");
    }
}

// class childClass extends parentClass
class Car extends Vehicle{
    private String numberOfCar;

    // default constructor
    public Car(String numberOfCar) {
        this.numberOfCar = numberOfCar;
    }

    // GETTER
    public void printCarNumber() {
        System.out.println(numberOfCar);
    }

    // removed the honk() method
}


class Bus extends Vehicle{
    private String numberOfBus;

    // default constructor
    public Bus(String numberOfBus) {
        this.numberOfBus = numberOfBus;
    }

    // GETTER
    public void printBusNumber() {
        System.out.println(numberOfBus);
    }

    // removed the honk() method
}

class Basics {
    public static void main(String[] args) {
        Car car = new Car();
        car.printCarNumber();
        car.honk();

        Bus bus = new Bus();
        bus.printBusNumber();
        bus.honk();
    }
}
```

In this way, we extended the functionality of `Car` to `Vehicle`. This way, class `Car` will **inherit** the functionalities of the `Vehicle` class. WHAT happens here is that, when we create an object for `Car`, it also creats an object for `Vehicle`.

Here, `Vehicle` class is called the **Base Class** and the `Car` and `Bus` classes are known as **Derived Classes**. Let's try to shift the functionality of assigning the carNumber and BusNumber to the same `Vehicle` class.

```java
`Base Class` or the `Parent Class`

class Vehicle {
    String numberOfVehicle;
    // default constructor
    public Vehicle(String numberOfVehicle) {
        this.numberOfVehicle = numberOfVehicle;
    }

    public void honk() {
        System.out.println("HONK!!!!!!!!!!!");
    }

    public void printNumberOfVehicle() {
        System.out.println(numberOfVehicle);
    }
}

`Derived Classes`

class Car extends Vehicle {
    // default constructor for the Car class
    public Car(numberOfCar) {
        super(numberOfCar); // calls the default constructor of the parent class.
    }
}


class Bus extends Vehicle {
    // default constructor for the Vehicle class
    public Bus(numberOfBus) {
        super(numberOfBus); // calls the default constructor of the parent class.
    }
}

class Basics {
    public static void main(String[] args) {
        Car car = new Car();
        Bus bus = new Bus();
        car.printNumberOfVehicle();
        bus.printNumberOfVehicle();
    }
}
```

Thus, `super()` method helps to call the **default constructor** of the parent class, and we can pass the argument of the parent constructor inside the parenthese of `super()`

---

## Polymorphism ( Override ) - Payment Mechanism (Cash, card)

Let's say we have a `Vehicle` class and then there are so many derived classes like `Car Bus Truck` etc. Now there is a functionality of `honk()` written inside the `Vehicle` class which all the derived classes are using , but what if we want to `override` this `honk()` functionality for some of the derived classes ?

This can be done by writing an `@Override` rule for the required derived class.

```java
class Car extends Vehicle {
    public Car (numberOfCar) {
        super(numberOfCar);
    }

    @Override
    public void honk() {
        System.out.println("Give me way!!!!!!");
    }
}
```

Here, we are just overriding a certain functionalities, not all of them, hence we are still `extend`ing the derived class to the parent class because we want all other functionalities of the parent class in our derived class.

This is known as **Polymorphism**.

> Note that when we create an object for the `Car` class, we also create an object for the `Vehicle` class as well. This is done in Polymorphism.

---

## Abstraction

Now, The thing is - that we cannot create an object from the Abstract class.

Syntax for creating an abstract class -

```java
abstract class BankAccount {

}
class Basics {
    public static void main(String[] args) {
        BankAccount ba = new BankAccount(); // ERROR - Abstract class cannot be instantiated.
    }
}
```

**Definition of Abstraction** - There are a lot of things which we don't need to know. For example - we press on the START button and the car starts, we don't need to know what happens inside the car. Similarly, Abstraction class don't give you internal details.

How do they do it internally, we shouldn't care about it. This is the concept of **Abstraction.**

We just know what the functionality is, we don't know how it is implemented.

For example -

```java
abstract class BankAccount {
    double balance;
    abstract void addMoney(double amount); // we can see what this method does
// but we don't care how it does that.
    abstract void withdrawMoney();
}


class Basics {
    public static void main(String[] args) {
        BankAccount ba = new BankAccount();
    }
}
```

When we try to `extend` our class to the `absract` class, we get an error - 

```java
class SavingsAccount extends BankAccount {
    // ERROR - SavingsAccount is not abstract and does not override abstract method withdrawMoney() in BankAccount
}
```

Basically, we can't `extends` our non-abstract class to an abstract class.

So , we can either turn the `SavingsAccount` into an `abstract` class, but in that case, we can't create an object of the `SavingsAccount` class. But what if we want to create an object of `SavingsAccount` class.

There are two `abstract methods` or `implementations` -

### 1st method - `abstract` class method

```java
abstract class BankAccount {
    double balance;
    abstract void addMoney(double amount);
    abstract void withdrawMoney();


}
class SavingsAccount extends BankAccount {
    public void addMoney(double amount) {

    }

    public void withdrawMoney() {

    }
}
```

Basically, In this way,  we have implemented the abstract methods inside the `SavingsAccount` class.

Here, we can see that we have an `abstract` class `BankAccount` and there are `abstract` methods written inside it but no **implemented** methods. We **extended** our **non-abstract** class to an **abstract** class and wrote the implementations of the **abstract** methods inside the extended non-abstract class. But it is not necessary that any **abstract** class cannot have any **implemented** methods.

```java
abstract class BankAccount {
    double balance;
    abstract void addMoney(double amount);
    abstract void withdrawMoney();

    // a non-abstract method but no one can use this method since it is 
    // inside an abstract class, but only our derived-classes can use it.
    void updateBalance(_balance) {
        balance = _balance;
    }

    public double getBalance() {
        return balance;
    }
}
class SavingsAccount extends BankAccount {
    public void addMoney(double amount) {

    }

    public void withdrawMoney() {

    }
}
```

Okay, we can create another class for the CurrentAccount as `CurrentAccount`. Let's say we can keep zero balance in the `SavingsAccount` but we have a minimum balance limit for the `CurrentAccount`.

We are writing implementations(say logic) of the same methods of the **abstract** class in the **extended** class because the implementations of the same method may differ for different classes.

```java
// This is what the people can see
abstract class BankAccount {
    double balance;
    abstract void addMoney(double amount);
    abstract void canUserWithdrawMoney(double amount);

    // a non-abstract method but no one can use this method since it is 
    // inside an abstract class, but only our derived-classes can use it.
    void updateBalance(_balance) {
        balance = _balance;
    }

    public double getBalance() {
        return balance;
    }
}
// Implementation is inside the SavingsAccount which people can't see.
class SavingsAccount extends BankAccount {
    public void addMoney(double amount) {
        super.updateBalance(super.getBalance() + amount);
    }

    public void canUserWithdrawMoney(double amount) {
        if (amount <= super.getBalance) {
            System.out.println("User can!");
        }
        else {
            System.out.println("User cannot!")
        }
    }
}

class CurrentAccount extend BankAccount {
    double minimumLimit = 1000.0;
    public void addMoney(double amount) {
        super.updateBalance(super.getBalance() + amount);
    }

    // different implementation of the same method
    public void canUserWithdrawMoney(double amount) {
        if (super.getBalance() - amount >= minimumLimit) {
            System.out.println("User can!");
        }
        else {
            System.out.println("User cannot!");
        }
    } 
}


class Basics {
    public static void main(String[] args) {

    }
}
```

Here, we can see that `addMoney` and `canUserWithdrawMoney` methods have different implementations for the **SavingsAccount** and the **CurrentAccount**, but `getBalance` and `updateBalance` methods have the same implementations for both **SavingsAccount** and **CurrentAccount**. That's why we wrote `addMoney` and `canUserWithdrawMoney` methods as `abstract` methods and wrote their implementations differently in different classes.

This is known as **Abstraction**. - We cannot instantiate an object of it. We can't see the internal details.

Hence, whenever we need to hide implementation details, we use an `abstract` class.

### 2nd Method - `interface` class

Interface again has the same definition - we know what the interface does - but we don't know what are the internal implementations of the methods. Also we can't create objects of the `interface` class, that is, `interface` classes can't be instantiated.

```java
interface Animal {
    void bark(); // we know animal will bark but how ? that we don't know
// the derived classes of this interface are gonna have the implementation
// of these abstract methods of this interface.

    // default implementation of sleep 
    default void sleep() {
        System.out.println("Sleeping zzz...");
    }
}
```

> Note - We need to write the `default` keyword to show that this is the default implementation of the `sleep` method.

> Also, we can write the static methods inside the interface and call them directly, for example -
> 
> ```java
> interface Animal {
>     void bark();
>     static void sleep() {
>         System.out.println("Sleeping zzz...");
>     }
> }
> 
> class Basics {
>     Animal.sleep(); // prints 
> }
> ```

> This means we can have a method in `interface` which we can directly call.

Now, to implement the methods/functionalities of the `interface` class, we use the `implements` keyword.

Example -

```java
interface Animal {
    void bark();
    default void sleep() {
        System.out.println("Sleeping zzz...");
    }
}

class Dog implements Animal {
    public void bark() {
        System.out.println("Bark!!!!");
    }

    // we can over-write the default methods of the interface methods in 
    // the implemented classes as well
    @Override
    public void sleep() {
        System.out.println("Dog is sleeping zzzz....");
    }
}

class Basics {
    Dog dog = new Dog();
    dog.bark(); // prints Bark!!!!
    dog.sleep(); // prints Dog is sleeping zzzz....
}
```

Let's create another class, but for Cats and let's change the implementation of the `bark` method since the cat meows and not bark and let's keep the implementation of `sleep` method same as `default` for the Cat.

```java
interface Animal {
    void bark();
    default void sleep() {
        System.out.println("Sleeping zzz...");
    }
}

class Dog implements Animal {
    public void bark() {
        System.out.println("Bark!!!!");
    }

    // we can over-write the default methods of the interface methods in 
    // the implemented classes as well
    @Override
    public void sleep() {
        System.out.println("Dog is sleeping zzzz....");
    }
}

class Cat implements Animal {
    public void bark() {
        System.out.println("Meow!!!!");
    }
}

class Basics {
    Dog dog = new Dog();
    dog.bark(); // prints Bark!!!!
    dog.sleep(); // prints Dog is sleeping zzzz....

    Cat cat = new Cat();
    cat.bark(); // prints Meow!!!!
    cat.sleep(); // prints Sleeping zzz...
}
```

> Now, **important** thing is that - 
> 
> `Derived classes`cannot be extended to multiple `abstract` classes, but only one.
> 
> **Whereas**, An `implemented` class can be extended to many `interface` classes.
> 
> Example -
> 
> ```java
> interface Animal {
>     void bark();
>     default void sleep() {
>         System.out.println("Sleeping zzz...");
>     }
> }
> 
> // another interface class
> interface Pet {
>     void ownerName();
> }
> 
> // implemented class extended to multiple interface classes
> class Dog implements Animal, Pet {
>     public void bark() {
>         System.out.println("Bark!!!!");
>     }
> 
>     // we can over-write the default methods of the interface methods in 
>     // the implemented classes as well
>     @Override
>     public void sleep() {
>         System.out.println("Dog is sleeping zzzz....");
>     }
> 
>     public void ownerName() {
>         System.out.println("XYZZZZZ");
>     }
> }
> 
> class Cat implements Animal {
>     public void bark() {
>         System.out.println("Meow!!!!");
>     }
> }
> 
> class Basics {
>     Dog dog = new Dog();
>     dog.bark(); // prints Bark!!!!
>     dog.sleep(); // prints Dog is sleeping zzzz....
>     dog.ownerName(); // prints XYZZZZZ
> 
>     Cat cat = new Cat();
>     cat.bark(); // prints Meow!!!!
>     cat.sleep(); // prints Sleeping zzz...
> }
> ```

So, basically we can say that `interface` is a set of rules to be implemented in the implemented classes or we can say a checklist for all the methods to be implemented in all the implemented classes of that interface class.

---

JAVA OOPS BASICS 

-- Classes and Objects

-- Method and Function

-- Public Private Protected

-- Constructor (default and parametrised, multiple constructors with different number of parameter and ofcourse the same name as the class name)

-- Encapsulation (getter and setter) - `private` keyword to safeguard the variables of the objects and using methods to get and set the values of those variables.

    -- Bank Example

-- Inheritance - `extends` keyword to use methods of one class in another class.

    -- Parent child concept

-- Polymorphism (`@Override` to override the functions of the parent class in the child class)

    -- Payment Mechanism

-- Abstraction (cannot be instantiated - )

    -- `abstract` keyword and `extends` keyword.

    -- `interface` and `implements` keyword.  

---

For more notes - Read Striver Notes ! :heart:
