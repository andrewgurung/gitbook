# Big O Notation

Big O notation is a language to express how long an algorithm will take to run.   
Instead of measuring the exact runtime of an algorithm \(which depends on the processor's speed\), Big O notation will tell us how quickly the runtime grows relative to its input variable.

### O\(1\) time or constant time

```java
public static void printFirstItem(int[] items) {
    System.out.println(items[0]);
}
```

### O\(n\) time or linear time

```java
public static void printAllItems(int[] items) {
    for (int item : items) {
        System.out.println(item);
    }
}
```

###  **O\(n​^**2​​**\)** time or quadratic time

```java
public static void printAllPossibleOrderedPairs(int[] items) {
    for (int firstItem : items) {
        for (int secondItem : items) {
            System.out.println(firstItem + ", " + secondItem);
        }
    }
} 
```

### Drop constants

* Constants are thrown out when calculating Big O
* As input n gets arbitrarily large, the significance of constant value decreases drastically

```java
  public static void printFirstItemThenFirstHalfThenSayHi100Times(int[] items) {
    System.out.println(items[0]);

    int middleIndex = items.length / 2;
    int index = 0;

    while (index < middleIndex) {
        System.out.println(items[index]);
        index++;
    }

    for (int i = 0; i < 100; i++) {
        System.out.println("hi");
    }
}
```

This is **O\(1 + n/2 + 100\)**, which we just call **O\(n\)**

Links:  
[https://www.interviewcake.com/article/java/big-o-notation-time-and-space-complexity](https://www.interviewcake.com/article/java/big-o-notation-time-and-space-complexity)

