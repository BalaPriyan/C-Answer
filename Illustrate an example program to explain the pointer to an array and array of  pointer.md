
### Pointer to an Array

A **pointer to an array** is a pointer that points to an entire array. This pointer allows you to access and manipulate the entire array via its memory address. 

#### Example Program:

```c
#include <stdio.h>

int main() {
    // Declare an array of 5 integers
    int arr[5] = {1, 2, 3, 4, 5};

    // Declare a pointer to an array of 5 integers
    int (*ptr)[5] = &arr;

    // Access elements of the array using the pointer
    printf("Elements of the array using pointer to an array:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", (*ptr)[i]);
    }
    printf("\n");

    return 0;
}
```

**Explanation:**

1. **Array Declaration**: 
   ```c
   int arr[5] = {1, 2, 3, 4, 5};
   ```
   Here, `arr` is an array of 5 integers, initialized with values 1, 2, 3, 4, and 5.

2. **Pointer to an Array Declaration**:
   ```c
   int (*ptr)[5] = &arr;
   ```
   - `int (*ptr)[5]` declares `ptr` as a pointer to an array of 5 integers.
   - `&arr` gives the address of the entire array `arr`.
   - Thus, `ptr` is assigned the address of `arr`.

3. **Accessing Array Elements**:
   ```c
   for (int i = 0; i < 5; i++) {
       printf("%d ", (*ptr)[i]);
   }
   ```
   - `(*ptr)[i]` accesses the `i`th element of the array pointed to by `ptr`.
   - The `*ptr` dereferences the pointer to access the array, and `[i]` accesses the `i`th element of that array.

### Array of Pointers

An **array of pointers** is an array where each element is a pointer that points to individual values or other arrays.

#### Example Program:

```c
#include <stdio.h>

int main() {
    // Declare three integer variables
    int a = 10, b = 20, c = 30;

    // Declare an array of 3 pointers to integers
    int *ptrArr[3];

    // Initialize the array of pointers
    ptrArr[0] = &a;
    ptrArr[1] = &b;
    ptrArr[2] = &c;

    // Access values using the array of pointers
    printf("Values accessed using array of pointers:\n");
    for (int i = 0; i < 3; i++) {
        printf("%d ", *ptrArr[i]);
    }
    printf("\n");

    return 0;
}
```

**Explanation:**

1. **Variable Declarations**:
   ```c
   int a = 10, b = 20, c = 30;
   ```
   Here, `a`, `b`, and `c` are three integer variables with values 10, 20, and 30, respectively.

2. **Array of Pointers Declaration**:
   ```c
   int *ptrArr[3];
   ```
   - `int *ptrArr[3]` declares `ptrArr` as an array of 3 pointers to integers.
   - Each element in `ptrArr` can hold the address of an integer.

3. **Initializing the Array of Pointers**:
   ```c
   ptrArr[0] = &a;
   ptrArr[1] = &b;
   ptrArr[2] = &c;
   ```
   - `ptrArr[0] = &a` assigns the address of `a` to the first element of `ptrArr`.
   - `ptrArr[1] = &b` assigns the address of `b` to the second element of `ptrArr`.
   - `ptrArr[2] = &c` assigns the address of `c` to the third element of `ptrArr`.

4. **Accessing Values**:
   ```c
   for (int i = 0; i < 3; i++) {
       printf("%d ", *ptrArr[i]);
   }
   ```
   - `*ptrArr[i]` dereferences the pointer at index `i` to access the value it points to.
   - This loop prints the values 10, 20, and 30, which are the values of `a`, `b`, and `c`, respectively.

### Summary
- **Pointer to an Array**:
  - Points to an entire array.
  - Syntax: `int (*ptr)[N] = &array;` where `N` is the number of elements in the array.
  - Access elements using `(*ptr)[i]`.

- **Array of Pointers**:
  - An array where each element is a pointer.
  - Syntax: `int *ptrArr[N];` where `N` is the number of pointers.
  - Access values using `*ptrArr[i]`.
