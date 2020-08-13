---
description: Making a single variable hold multiple values
---

# Arrays and ArrayLists

Right now, we know that a variable can store a single value of a specific type, but sometimes it is more efficient to have a single variable hold multiple values. To make a variable hold multiple values of a specific type, we use a concept known as _arrays_ and, in Java, _ArrayLists_.

## Array

In Java, an array is a data structure that **holds a** _**fixed**_ **amount of values of a specific type**. To create an array, we use the following syntax:

```java
int[] array           = new int[3];
// or, if we know the values we will use
int[] arrayWithValues = { 3, 8, 72 };
```

This might remind you of how we create a new instance of a class by using the `new` keyword. However, you will notice that instead of using parenthesis, we use square brackets. Inside the square brackets, we enter the amount of values the array can hold. We can visualize this array as follows:

```text
       | col 0 | col 1 | col 2 |
-------|-------|-------|-------|
 row 0 |  [0]  |  [1]  |  [2]  |
-------|-------|-------|-------|
```

You might notice that this looks like a spreadsheet, or a table of values. That's because that exactly what an array is!

{% hint style="info" %}
Arrays are index from `0` and upwards, meaning that the first element of the array will be located at index `0`, the second at `1`, and so forth.
{% endhint %}

To access a value of the array, use brackets on the name of the variable. Inside the brackets, type the _index_, or the location, of the element inside the array. For example, to access the second value of the array:

```java
int secondVal = array[1];
```

### 2D Array

Before, we created what is known as a 1D array, meaning that it only has one dimension of values. To create a 2D array, we use 2 square brackets instead of one.

```java
int[][] array2d = new int[2][3];
```

This array can be visualized as:

```text
       | col 0  | col 1  | col 2  |
-------|--------|--------|--------|
 row 0 | [0][0] | [0][1] | [0][2] |
-------|--------|--------|--------|
 row 1 | [1][0] | [1][1] | [1][2] |
-------|--------|--------|--------|
```

{% hint style="info" %}
A 2D array is essentially an _array of arrays_.
{% endhint %}

In Java, arrays are usually accessed in what is called _row-major order_, meaning that in a 2D array, the first pair of brackets refers to the row of the array, and the second bracket pair refers to the column of the array. Using this principle, to access the second column of the first row:

```java
int secondColFirstRow = array2d[0][1];
```

### Looping through arrays

Writing loops through arrays is a fundamental part of Java. Arrays have a `length` property that allows us to determine how long the array is. We can use this `length` property in the ending condition of a for loop like this:

```java
int[] array = new int[4];

for(int i = 0; i < array.length; i++) {
    int element = array[i]; // accesses the i'th element of array
    // ...
}
```

This for loop will run through every element of the array until it is complete.

We can use this same looping principle with 2D arrays:

```java
int[] array2d = new int[4][3];

for(int row = 0; row < array.length; row++) {
    // each element of a 2d array is a 1d array
    int[] array1d = array2d[row];
    for(int col = 0; col < array1d.length; col++) {
        int element     = array1d[col];
        // or...
        int sameElement = array2d[row][col];
    }
}
```

## ArrayLists

Now we know how to make a variable hold a fixed amount of multiple values. But what if we need the variable to hold a _dynamic_ amount of values? Introducing `ArrayList`.

ArrayLists are dynamic arrays that allow us to do a lot more than regular arrays. The main advantage of ArrayLists over arrays is that we can create, read, update, and delete \([CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete)\) elements.

To use an ArrayList, the first thing we need to do is at the top of our Java program, import `java.util.ArrayList`.

```java
import java.util.ArrayList;
```

This tells Java that we will be using ArrayLists in this program.

Here is how you create a new ArrayList:

```java
ArrayList<Double> list = new ArrayList<Double>();
```

Notice that you can't immediately specify which values you need in the ArrayList. Also, what's with the angle brackets `<` and `>` ? Those are called _generic type specifiers_, a higher level Java principle. Basically, they tell the ArrayList what type of values it can accept. In this case, the `ArrayList<Double> list` can only accept values of `double` type.

{% hint style="info" %}
The generic type of an ArrayList can't be a primitive data type; to use a primitive data type in an ArrayList, use their respective object forms: Integer for int, Double for double, Boolean for boolean, etc.
{% endhint %}

Let's go over some of the methods of an ArrayList:

```java
list.add(57.0);    // adds a value to the list
list.get(0);       // gets the first value of the list
list.remove(0);    // removes the first value of the list
list.remove(57.0); // removes the given value from the list
list.set(0, 89.0); // sets the first value of the list to the given value
```

To see a full list of the methods on the ArrayList class, read the [complete ArrayList API](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html).

### Using integers with ArrayList

You might notice that the `get`, `set`, and `remove` methods all take integers as a parameter. Say you are using `Integer` as the generic type for an ArrayList:

```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(90);
```

Now, the list has the element `90` and index `0`. What if we wanted to remove the value `90` from the list?

```java
list.remove(90); // java.lang.IndexOutOfBoundsException
```

We receive an error from Java that notifies us that there is no 3rd element in the ArrayList. Why wouldn't it just remove the value `2`? Java thinks, when you enter an `int` as the parameter for this method, that you are requesting to remove the given index from the ArrayList. To fix this issue, we have to _cast_ the `int` into an `Integer`.

```java
list.remove((Integer)90);
```

This is just one of the quirks of the Java language.

### Looping through ArrayLists

Similarly to the `length` property on arrays, ArrayLists offer a `size` _method_ that returns the size of the list. This is how you would loop through an ArrayList using the `size` method:

```java
ArrayList<Integer> list = new ArrayList<Integer>();

for(int i = 0; i < list.size(); i++) {
    int element = list.get(1); // accesses the i'th element of array
    // ...
}
```

When using an ArrayList, you have to use the `get` method to get the element of a specific index, unlike in arrays when you can use a bracket pair.

