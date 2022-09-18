---
layout: post
title: C Pointers
published: true
category: cs 
---

In this post, we will learn about pointers C. 

## I. What is a pointer?
If you have a variable `var` in your program, `&var` will give you its address in the memory.
__Pointers__ are special variables that are used to store addresses rather than values.


### Pointer Syntax
Here is how we can declare pointers.
```c
int* p; // pointer of type int
```
There are other ways of declaring pointers,
```c
int *p;
int * p1;
```
Another example,
```c
int* pc, c;     //pc is a pointer, c is an integer
```


### Assigning addresses to Pointers

Let's take an example.

```c
int* pc, c;
c = 5;
pc = &c;
printf(pc);    // will print the address of c
```

Here, 5 is assigned to the  c  variable. And, the address of  c  is assigned to the  pc  pointer.


### Get Value of Thing Pointed by Pointers

To get the value of the thing pointed by the pointers, we use the  `*`  operator.
```c
int* pc, c;
c = 5;
pc = &c;
printf("%d", *pc);   // Output: 5
```
Here, the address of  `c`  is assigned to the  pc  pointer. To get the value stored in that address, we used  `*pc`.



### Changing Value Pointed by Pointers

Let's take an example.
```c
int* pc, c;
c = 5;
pc = &c;
c = 1;
printf("%d", c);    // Output: 1
printf("%d", *pc);  // Ouptut: 1
```
Since  pc  and the address of  c  is the same,  `*pc`  gives us the same value as c.

Let's take another example.

```c
int* pc, c;
c = 5;
pc = &c;
*pc = 1;
printf("%d", *pc);  // Ouptut: 1
printf("%d", c);    // Output: 1
```
In the same way, `c` and `*pc` have the same values. 

<ins>__Quick illustration__:</ins>

1.  `pc = &c;`  
    
    ![Address of variable c is assigned to pointer pc.](https://cdn.programiz.com/sites/tutorial2program/files/pointer-3.jpg)
    
      
    This assigns the address of variable  c  to the pointer  pc.  
    
2.  `c = 11;`  
    
    ![11 is assigned to variable c.](https://cdn.programiz.com/sites/tutorial2program/files/pointer-4.jpg)

<ins>__Remark__:</ins>
We can also define a pointer directly using the address of an already created variable, 

```c
int c = 9;
int *p = &c;     
// or 
int* p = &c;
```
Note that, in `int *p`, the `*` is used to define the pointer, not to refer to its value. 


### Why to use pointers?

1.  Pointers save memory space.
2.  Execution time with pointers is faster because data are manipulated with the address, that is, direct access to memory location.
3.  Memory is accessed efficiently with the pointers. The pointer assigns and releases the memory as well.


## II. Pointers and Arrays 
An array is a block of sequential data. Let us print out addresses of an array elements:

```c
int x[4];
int i;
for(i = 0; i < 4; ++i) {
   printf("&x[%d] = %p\n", i, &x[i]);
}
printf("Address of array x: %p", x);
}
```

<ins>**Output**</ins>

>`&x[0] = 1450734448`
`&x[1] = 1450734452`
`&x[2] = 1450734456`
`&x[3] = 1450734460`
`Address of array x: 1450734448`

There is a difference of 4 bytes between two consecutive elements of array `x`, because the size of `int` is 4 bytes.

<ins>__Important remark__</ins>
Notice that, the address of `&x[0]` and `x` is the same. It's because the variable name `x` ___points to the first element of the array___.

And,  `x[0]`  is equivalent to  `*x`.

Similarly,

-   `&x[1]`  is equivalent to  `x+1`  and  `x[1]`  is equivalent to  `*(x+1)`.
-   `&x[2]`  is equivalent to  `x+2`  and  `x[2]`  is equivalent to  `*(x+2)`.
-   ...
-   Basically,  `&x[i]`  is equivalent to  `x+i`  and  `x[i]`  is equivalent to  `*(x+i)`.

Let's see another example,
```c
int x[5] = {1, 2, 3, 4, 5};
int* ptr;

// ptr is assigned the address of the third element
ptr = &x[2]; 

printf("*ptr = %d \n", *ptr);   // 3
printf("*(ptr+1) = %d \n", *(ptr+1)); // 4
printf("*(ptr-1) = %d", *(ptr-1));  // 2
```

## III. Passing Addresses to Functions
To pass an address to a function, we can use pointers. 
```c
void swapValues(int *p1, int *p2){
	// this function swaps values of pointers
	int temp; 
	temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}
```

## IV. C Dynamic Memory Allocation
As you know, an array is a collection of a fixed number of values. Once the size of an array is declared, you cannot change it.

Sometimes the size of the array you declared may be insufficient. To solve this issue, you can __allocate memory manually _during run-time___. This is known as __dynamic memory allocation__ in C programming.

For this, we use functions defined in the `<stdlib.h>` header file.


### `malloc()` function 
The `malloc()` function reserves a block of memory of the specified number of bytes. And, it returns a pointer of `void` which can be casted into pointers of any form.

<ins>**Syntax**</ins>
```c
ptr = (castType*) malloc(size);
```

<ins>**Example**</ins>

```c
ptr = (float*) malloc(100 * sizeof(float));
```

The above statement allocates 400 bytes of memory. It's because the size of  `float`  is 4 bytes. And, the pointer  ptr  holds the address of the first byte in the allocated memory.

The expression results in a  `NULL`  pointer if the memory cannot be allocated.


### `calloc()` function 
The name "calloc" stands for contiguous allocation.

The  `malloc()`  function allocates memory and leaves the memory _uninitialized_, whereas the  `calloc()`  function allocates memory and _initializes_ all bits to zero.


<ins>**Syntax**</ins>
```c
ptr = (castType*) calloc(n, size);
```

<ins>**Example**</ins>

```c
ptr = (float*) calloc(20, sizeof(float));
```

The above statement allocates contiguous space in memory for 25 elements of type `float`.


### `free()` function 

Dynamically allocated memory created with either  `calloc()`  or  `malloc()`  doesn't get freed on their own. You must explicitly use  `free()`  to release the space.

<ins>**Syntax**</ins>

```c
free(ptr);
```

This statement frees the space allocated in the memory pointed by  `ptr`.


<ins>__Example 1: malloc() and free()__</ins>

```c
// Program to calculate the sum of n numbers entered by the user
int n, i, *ptr, sum = 0;
printf("Enter number of elements: ");
scanf("%d", &n);

ptr = (int*) malloc(n * sizeof(int));  // calloc() can be used too 

// if memory cannot be allocated
if(ptr == NULL) {
  printf("Error! memory not allocated.");
  exit(0);
}

printf("Enter elements: ");
for(i = 0; i < n; ++i) {
  scanf("%d", ptr + i);
  sum += *(ptr + i);
}

printf("Sum = %d", sum);

// deallocating the memory
free(ptr);
```


### `realloc()` function 

If the dynamically allocated memory is insufficient or more than required, you can change the size of previously allocated memory using the  `realloc()`  function.

<ins>__Syntax__</ins>

```c
ptr = realloc(ptr, newsize);
```

Here,  `ptr`  is reallocated with a new size  `newsize`.