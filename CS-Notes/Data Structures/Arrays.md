<font size=5>hi</font>
<strong><font size=5>What is an array?</font></strong> 
- An array is a <u>linear data structure</u> where all elements are arranged sequentially. It is a collection of elements of <strong>same data type</strong> stored at contiguous memory locations. 

![[Pasted image 20240809115148.png|500]]

<strong>Arrays:</strong> 
- Start at [0...Size - 1]
- Size (int) = 4 bytes

<strong>What is contiguous memory allocation?</strong>
- A single contiguous section/point of memory is allocated to the array. 

<strong>Static vs Dynamic Arrays</strong>
1) Static Arrays - Memory is allocated at compile time having fixed size of it. Cannot alter or update the size of static arrays. 
```
Ex. in Java

int a[5] = {1, 2, 3, 4, 5};

a[5] --> [1, 2, 3, 4, 5]
```

2) Dynamic Arrays - Memory is allocated at run time but not having a fixed size. 
```
Ex. in Java

int *a = new int [5];

*a --> [0, 0, 0, 0, 0]
```

<strong><font size=4>Declaring an array</font></strong>:
Java: 
```
data_type name[] = new data_type[size];

int arr[] = new int[5];
```

