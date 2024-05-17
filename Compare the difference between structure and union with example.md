
### Structure (`struct`)

**Definition**: A structure is a collection of variables of different data types, under a single name. Each member of the structure has its own memory location, so all members can be accessed and modified independently.

**Memory Allocation**: Each member of a structure is allocated its own memory space. The total memory occupied by a structure is the sum of the memory required by each member, possibly adjusted for alignment.

**Usage Example**:
```c
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float salary;
};

int main() {
    struct Employee emp1;
    
    emp1.id = 101;
    snprintf(emp1.name, 50, "Alice");
    emp1.salary = 50000.50;
    
    printf("Employee ID: %d\n", emp1.id);
    printf("Employee Name: %s\n", emp1.name);
    printf("Employee Salary: %.2f\n", emp1.salary);
    
    return 0;
}
```

In this example:
- `struct Employee` defines a structure with three members: `id`, `name`, and `salary`.
- Each member occupies separate memory, so modifying one member does not affect the others.

### Union (`union`)

**Definition**: A union is similar to a structure in that it groups different types of variables under a single name. However, all members of a union share the same memory location. Only one member can hold a value at any given time.

**Memory Allocation**: All members of a union share the same memory space. The total memory occupied by a union is equal to the memory required by its largest member.

**Usage Example**:
```c
#include <stdio.h>

union Data {
    int intValue;
    float floatValue;
    char str[20];
};

int main() {
    union Data data;
    
    data.intValue = 10;
    printf("Int: %d\n", data.intValue);
    
    data.floatValue = 220.5;
    printf("Float: %.2f\n", data.floatValue);
    
    snprintf(data.str, 20, "Hello");
    printf("String: %s\n", data.str);
    
    printf("Int after assigning string: %d\n", data.intValue);  // Undefined behavior
    printf("Float after assigning string: %.2f\n", data.floatValue);  // Undefined behavior
    
    return 0;
}
```

In this example:
- `union Data` defines a union with three members: `intValue`, `floatValue`, and `str`.
- All members share the same memory space, so changing the value of one member will overwrite the others.
- When `data.intValue` is assigned a value, it overwrites the memory for `floatValue` and `str`.
- When `data.floatValue` is assigned a value, it overwrites the memory for `intValue` and `str`.
- When `data.str` is assigned a value, it overwrites the memory for `intValue` and `floatValue`.

### Key Differences

1. **Memory Usage**:
   - **Structure**: Memory is allocated for all members independently.
   - **Union**: Memory is shared among all members, equal to the size of the largest member.

2. **Member Access**:
   - **Structure**: All members can be accessed independently without affecting each other.
   - **Union**: Only one member can be accessed at a time; accessing one member overwrites the others.

3. **Use Case**:
   - **Structure**: Useful when you need to store multiple attributes together where each attribute can be accessed and modified independently.
   - **Union**: Useful when you need to work with different data types in the same memory location, typically in scenarios involving type conversion or memory-saving techniques.

### Summary

- **Structure** is like a record in a database where each field (member) has its own storage.
- **Union** is like a variant record where different fields share the same storage space, useful when a variable may hold any one of several types but only one at a time.
