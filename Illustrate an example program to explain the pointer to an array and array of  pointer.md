
### Pointer to an Array

A pointer to an array points to the entire array, which means it holds the address of the first element of the array.

#### Example:

```cpp
#include <iostream>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int (*ptr)[5]; // Pointer to an array of 5 integers

    ptr = &arr; // ptr now points to the array arr

    // Accessing elements using the pointer to the array
    for(int i = 0; i < 5; i++) {
        std::cout << "Element " << i << " is " << (*ptr)[i] << std::endl;
    }

    return 0;
}
```

#### Explanation:

1. `int arr[5] = {10, 20, 30, 40, 50};` declares and initializes an array of 5 integers.
2. `int (*ptr)[5];` declares a pointer to an array of 5 integers.
3. `ptr = &arr;` assigns the address of the array `arr` to `ptr`.
4. `(*ptr)[i]` is used to access elements of the array through the pointer.

### Array of Pointers

An array of pointers is an array where each element is a pointer.

#### Example:

```cpp
#include <iostream>

int main() {
    int a = 10, b = 20, c = 30;
    int *arr[3]; // Array of 3 integer pointers

    arr[0] = &a; // arr[0] points to a
    arr[1] = &b; // arr[1] points to b
    arr[2] = &c; // arr[2] points to c

    // Accessing values using the array of pointers
    for(int i = 0; i < 3; i++) {
        std::cout << "Value pointed by arr[" << i << "] is " << *arr[i] << std::endl;
    }

    return 0;
}
```

#### Explanation:

1. `int a = 10, b = 20, c = 30;` declares and initializes three integers.
2. `int *arr[3];` declares an array of 3 integer pointers.
3. `arr[0] = &a;`, `arr[1] = &b;`, and `arr[2] = &c;` assign the addresses of `a`, `b`, and `c` to the elements of the array of pointers, respectively.
4. `*arr[i]` is used to access the values pointed to by the array of pointers.

### Summary

- **Pointer to an array**: Points to the entire array, accessing elements through dereferencing and indexing.
- **Array of pointers**: Each element is a pointer, and values are accessed by dereferencing the individual pointers in the array.

Both concepts are essential in different scenarios and provide powerful ways to manage and manipulate data in C++.
