In C programming, storage classes define the scope (visibility) and lifetime of variables and functions within a C program. There are four primary storage classes in C: `auto`, `register`, `static`, and `extern`. Each serves a different purpose, and understanding these classes helps in managing the variables effectively in your programs.

### 1. `auto`
- **Scope**: Local to the block in which it is defined.
- **Lifetime**: The variable exists only within the block or function; it is destroyed once the block or function terminates.
- **Default Storage Class**: If no storage class is specified for a local variable, `auto` is assumed.

**Example**:
```c
#include <stdio.h>

void exampleAuto() {
    auto int num = 10; // 'auto' is optional here
    printf("Value of num: %d\n", num);
}

int main() {
    exampleAuto();
    return 0;
}
```
In this example, `num` is an automatic variable with local scope.

### 2. `register`
- **Scope**: Local to the block in which it is defined.
- **Lifetime**: The variable exists only within the block or function; it is destroyed once the block or function terminates.
- **Special Feature**: Suggests to the compiler to store the variable in a CPU register instead of RAM for faster access. However, this is a suggestion, and the compiler may ignore it.

**Example**:
```c
#include <stdio.h>

void exampleRegister() {
    register int count = 0;
    for (register int i = 0; i < 10; ++i) {
        count += i;
    }
    printf("Count: %d\n", count);
}

int main() {
    exampleRegister();
    return 0;
}
```
Here, `count` and `i` are register variables that may be stored in CPU registers for quick access.

### 3. `static`
- **Scope**: Local scope if defined within a function, but retains its value across function calls. If defined globally, its scope is limited to the file in which it is declared.
- **Lifetime**: Exists for the entire duration of the program.

**Example (local static variable)**:
```c
#include <stdio.h>

void exampleStatic() {
    static int counter = 0; // Retains its value between function calls
    counter++;
    printf("Counter: %d\n", counter);
}

int main() {
    exampleStatic();
    exampleStatic();
    exampleStatic();
    return 0;
}
```
Each call to `exampleStatic` will increment the `counter` variable, retaining its value between calls.

**Example (global static variable)**:
```c
#include <stdio.h>

static int globalVar = 5; // Global variable, accessible only in this file

void printGlobalVar() {
    printf("Global Variable: %d\n", globalVar);
}

int main() {
    printGlobalVar();
    return 0;
}
```
Here, `globalVar` is only accessible within the file it is declared in, providing file-level encapsulation.

### 4. `extern`
- **Scope**: Global, allowing access across multiple files.
- **Lifetime**: Exists for the entire duration of the program.
- **Usage**: Used to declare a global variable or function in another file.

**Example**:

**File1.c**:
```c
#include <stdio.h>

int num = 10; // Definition of the global variable

void printNum() {
    printf("Num: %d\n", num);
}
```

**File2.c**:
```c
#include <stdio.h>

extern int num; // Declaration of the global variable

void incrementNum() {
    num++;
}

int main() {
    incrementNum();
    printNum(); // Assuming this function is defined elsewhere
    return 0;
}
```
In this example, `num` is declared in `File2.c` using `extern`, which references the definition in `File1.c`. This allows `File2.c` to access and modify `num`.

### Summary
- **`auto`**: Default for local variables, block scope, temporary lifetime.
- **`register`**: Hint to store in CPU registers, block scope, temporary lifetime.
- **`static`**: Persistent lifetime across function calls, limited scope depending on where it's declared.
- **`extern`**: Global scope across multiple files, persistent lifetime.

Each storage class serves a specific purpose, and choosing the right one helps optimize memory usage and variable accessibility in your C programs.
