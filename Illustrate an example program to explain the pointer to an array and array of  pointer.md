
### Pointer to an Array

A pointer to an array is a pointer that points to an entire array. Here's an example program demonstrating this concept:

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
- `int arr[5]` declares an array of 5 integers.
- `int (*ptr)[5]` declares a pointer to an array of 5 integers and initializes it to the address of `arr`.
- We access elements of the array using `(*ptr)[i]`.

### Array of Pointers

An array of pointers is an array where each element is a pointer to an individual value (or another array). Here's an example program demonstrating this concept:

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
- `int *ptrArr[3]` declares an array of 3 pointers to integers.
- Each element of `ptrArr` is assigned the address of an integer variable (`a`, `b`, and `c`).
- We access the values pointed to by the pointers using `*ptrArr[i]`.

### Summary
- **Pointer to an array**: Points to an entire array. Access elements using `(*ptr)[i]`.
- **Array of pointers**: An array where each element is a pointer. Access elements using `*ptrArr[i]`.
