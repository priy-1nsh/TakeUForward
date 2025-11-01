# 1. Custom classes

We can create custom data-types by creating custom classes.

Example -

```java
class Data {
    public Integer num;
    public String name;
    Data(int _num, String _name) {
        this.num = _num;
        this.name = _name;
    }
}


public class Basics {
    public static void main(String[] args) {
        Data dataObj1 = new Data(9, "Raj");
        Data dataObj2 = new Data(7, "TUF");
        dataObj1.name = "Striver"; // this is how we can change the varaible
        System.out.println(dataObj2.name);
    }
}
```

This is a custom class.

But in industry, we usually use `private` instead of `public`.

```java
class Data {
    private Integer num;
    private String name;
    Data(int _num, String _name) {
        this.num = _num;
        this.name = _name;
    }
    // setters
    public void setNum(Integer _num) {
        this.num = _num;
    }
    public void setName(String _name) {
        this.name = _name;
    }

    //getter
    public Integer getNum() {
        return num;
    }
    public String getName() {
        return name;
    }
}

public class Basics {
    public static void main(String[] args) {
        Data dataObj1 = new Data(9, "Raj");
        Data dataObj2 = new Data(7, "TUF");
        dataObj1.setName("Striver"); // this is how we can change the varaible
        System.out.println(dataObj2.getName();
    }
}
```

Can we create another custom class inside this class ?

Example -

```java
// new internal class
class InternalData {
    public Integer revenue;
    InternalData(Integer _revenue) {
        this.revenue = _revenue;
    }
}


// and then add it in our Data class
class Data {
    private Integer num;
    private String name;
    private InternalData internalData;
    Data(int _num, String _name, int _revenue) {
        this.num = _num;
        this.name = _name;
        this.internalData = new InternalData(_revenue);
    }
}
```

And, this is how we write custom classes inside another custom class, and we can have all different types of logic written in it as well.

# 2. Collection Interface

This Collection Framework falls under `java.util` package. Import it using `java.util.Collection`.

It is an interface. So, it doesn't have the implementation.

Let's go one way down -

## 1. List Interface

This is also an interface and it is the child interface to the Collections interface.

It extends to the Collections Interface. So, any functionality which is to be implemented in the Collections interface also has to be implemented in the List interface.

But since these are interfaces, we need to implement them using classes.

### - ArrayList

Example -

```java
public class basics {
    public static void main(String[] args) {
        ArrayList<Data> aList = new ArrayList<>(); //custom data type
        ArrayList<Integer> aList = new ArrayList<>(); //integer
    }
}
```

Arrays are constant in size and are 0-based indexed.

```java
int arr[] = new int[100];
```

ArrayLists are dynamic in nature. We can keep adding elements.

```java
aList.add(10);
aList.add(16);
aList.add(20);
aList.add(12);
System.out.println(aList); // prints [10, 16, 20, 12]
```

This `add()` functionality is written inside the ArrayList class.

```java
aList.size(); //4
aList.get(3); //12 - takes the index and returns the element
aList.remove(2); // removes the element at the 2nd index
```

> Note that remove() function returns the value whivh is removed.

```java
aList.add(index:1, element:17); // takes the index and the element to be 
// added at that index
aList.clear(); // clears up the array
aList.contains(element:17); //returns the true or false
```

> Remenber that it is a one-ended list, that is, we can only add from the end.

### - LinkedList

Class which is implementing the List interface.

```java
LinkedList<Integer> ll = new LinkedList<>();
```

It is a two-ended list. We can add from the front as well as the end.

```java
ll.add(e:1);
ll.add(e:2);
ll.addFirst(e:3); // to add at the front
ll.addLast(e:e:6); // to add at the last
```

```java
ll.removeFirst();
ll.removeLast(); // removes at the last and also return that element
```

```java
ll.getFirst();
ll.getLast(); // returns the last element
```

### - Stack

LIFO (Last In First Out)

```java
Stack<Integer> st = new Stack<>();
st.push(2);
st.push(6);
st.push(4);

[2, 6, 4]
```

```java
st.peek(); // gives you the last element which was pushed (last element)
```

```java
st.pop(); // removes the last element and returns it.
```

```java
st.isEmpty(); // returns true or false
```

### - Vector Class

Similar to ArrayList very much but it is thread safe. To prevent race conditions, we use vectors.

```java
Vector<Integer> vec = new Vector<>();
vec.capacity();
```

Same functionalities.

## 2. Set Interface

### - HashSet

Class which stores unique elements in any random order. No guarantee of the sorted order. O(1)

```java
HashSet<Integer> hs = new HashSet<>();
```

```java
.add()
.conatins()
.size()
.equals(anotherSet)
.isEmpty()
.remove(elemnetToBeRemoved);
// To iterate 
for (Integer num : hs) {
    System.out.println(num);
}

// better to use -
for (var num: hs) {
    System.out.println(num);
}
```

### - TreeSet

DS that stores unique elements in sorted order. O(logN)

```java
TreeSet<Integer> ts = new TreeSet<>();
ts.add(1);
ts.add(2);
ts.add(1);
ts.add(-1);
System.out.println(ts); // [-1, 1, 2]
```

```java
ts.floor(8); // prints the value in ts which is just less than or equal to 8, just
// less than or equal to 8
ts.ceiling(8); // prints the value which is just more than or equal to 8, just 
// more than or equal to 8
```

## 3. Queue Interface (FIFO)

### - ArrayDeque Class

implements the Dequeue Interface which extends the Queue interface.

```java
ArrayDeque<Integer> ad = new ArrayDeque<>();
ad.offer(2);
ad.offer(6);
ad.offer(9);
ad,offer(10);
// [2, 6, 9, 10]
System.out.println(ad.peek());// ad,peek() returns the first element which
// was added - FIFO

ad.poll(); // takes out the first element which was added

ad.offerFirst(7); // adds from front
ad.offerLast(8); // adds from the last
// (Dequeue is a double-ended queue)
```

```java
.offer(); - adds at the last
.peek(); - gives the first element which was added
.poll(); - taks out the first element which was added
```

Also, since this is a dequeue, it is double ended, and hence you can use .offerFrist(), .offerLast(), etc.

### - LinkedList Class

Already done, this also implements the Queue interface

### - PriorityQueue (Min heap)

Stores the elements

and whenever you ask for peek, it gives you the smallest element

(It implements the Tree DS)

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.offer(1);
pq.offer(0);
pq.offer(5);
pq.offer(4);
System.out.println(pq);
// [0, 1, 5, 4] - no order
pq.peek(); // gives the smallest element
pq.poll(); // removes the smallest element

// To iterate over it
while (pq.isEmpty() == false) {
    System.out.println(pq.peek());
    pq.poll();
}
```

If we implement the custom comparator here, we can get the max element as well, also - it will then become the max-heap DS.

# 3. Map Interface

Key-value pairs and doesn't store duplicate keys.

## - HashMap class

Does not store keys in the sorted order.

If the order doesn't matter, use HashMap

```java
// key, value
// rollnumber is the key
// name is the value
HashMap<Integer, String> mp = new HashMap<>();
mp.put(1, "Raj");
mp.put(2, "Vikram");
mp.put(3, "Rima");
System.out.println(mp);
// {1=Raj, 2=Vikram, 3=Rima}
```

```java
mp.get(key:2); // Rima
mp.size(); // 3
mp.remove(2); // remove the key 2
mp.get(6); // null
```

## - TreeMap class

Implements the Map Interface

Always stores the sorted order of keys.

Uses O(logN)

Some more functionalities -

```java
mp.ceilingKey(key:2); // gives the key which is greater than or equal to 
// this key
mp.floorKey(key:2); // gives the key which is less than or equal to 2
```

```java
Set<Integer> st = mp.keySet(); // return the set of all the keys
```

# 4. Iterator Interface

```java
ArrayList<Integer> al = new ArrayList<>();
al.add(4);
al.add(5);
al.add(1);

Iterator<Integer> iterator = al.iterator(); // just before 1
while (iterator.hasNext()) {
    Integer num = iterator.next();
    System.out.println(num);
}
```

> Note that iterator always points to an element which is just before the first element we can see.

> Also, note that we can always write the name of the interface which the class is implementing instead of the class name to declare an object of that class.

# 5. Common Algorithms

```java
List<Integer> al = new ArrayList<>();
al.add(1);
al.add(5);
al.add(4);
// [1, 5, 4]
Collections.sort(al);
```

```java
Collections.min(al);
Collections.max(al);
Collections.reverse(al);
```

To sort an array, use `Array.sort(array);`

```java
Collections.frquency(al, 5); // how many times 5 occurs in al
```

```java
Collections.binarySearch(List, key);
```

```java
Math.pow(2,5); // returns 2^5 but returns the double
```

# 6. Custom Comparator

```java
List<Integer> al = new ArrayList<>();
al.add(1);
al.add(5);
al.add(4);

// sort it in the descending order
Collections.sort(al, new Comparator<Integer>() {
    @Override
    // order [num1, num2]
    public int compare(Integer num1, Integer num2) {
        if (num1 < num2) {
            // order is wrong - return 1
            return 1;
        }
        else if (num1 > num2) {
            // order is correct - so return -1
            return -1;
        }
        return 0; // if both are equal
    }
});
```

Need to create a comparator object of the same type as the objects we want to compare. Also, we need to override it since it's an interface nethod which needs to be overridden and we also need to implement the compare() function which is a compulsory thing to do.

*We return 1 if we want to swap the order which we naturally assume to be same as what we have passed as parameters to the compare method.*

Also, a nice way to write comparator for the descending order is so that we can use it at many places -

```java
java.util.*;
public class basics {
    public static Comparator<Integer> getComparator() {
        return new Comparator<Integer>() {
            @Override
            // order [num1, num2]
            public int compare(Integer num1, Integer num2) {
            if (num1 < num2) {
                // order is wrong - return 1
                return 1;
            }
            else if (num1 > num2) {
                // order is correct - so return -1
                return -1;
            }
            return 0; // if both are equal
        }
    }

    public static void main(String[] args) {
        // max heap which returns the mac element when you poll the top
        // element
        PriorityQueue<Integer> pq = new PriorityQueue<>(getComaparator()) {
            pq.add(1);
            pq.add(5);
            pq.add(3);
            System.out.println(pq.poll()); // max element returned by poll
        }
    }
}
```
