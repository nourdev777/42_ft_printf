# 42_ft_printf 🖨️

---

## 🌟 About the Project

`42_ft_printf` is my reimplementation of the classic C `printf()` function, created as part of the **42 Abu Dhabi Common Core**. This project challenged me to handle variable arguments and mimic the behavior of the original `printf()` without its buffer management. It’s a powerful tool I can now add to my `libft` for future projects!

---

## 🛠️ Features

### Mandatory Part
- Handles the following conversions:  
  - `%c` — Character  
  - `%s` — String  
  - `%p` — Pointer address  
  - `%d` & `%i` — Signed integer  
  - `%u` — Unsigned integer  
  - `%x` & `%X` — Hexadecimal (lowercase and uppercase)  
  - `%%` — Literal percentage sign  
- Uses variadic arguments (`va_list`) to process inputs dynamically.  
- Returns the number of characters printed, just like the original `printf()`.

---

## 🚀 How to Use

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/nourdev777/42_ft_printf.git
```

### 2️⃣ Compile the Library
```bash
make
```

Clean up:
```bash
make fclean
```

### 3️⃣ Test the Library
Create a file named `main.c` with the following test code:

```c
#include "ft_printf.h"
#include <stdio.h>
#include <limits.h>

int main(void)
{
    int ret1, ret2;

    // Test characters
    printf("\n----- Testing %%c -----\n");
    ret1 = printf("Original: %c %c %c\n", 'a', '1', '\0');
    ret2 = ft_printf("Custom  : %c %c %c\n", 'a', '1', '\0');
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test strings
    printf("\n----- Testing %%s -----\n");
    ret1 = printf("Original: %s %s %s\n", "hello", "", NULL);
    ret2 = ft_printf("Custom  : %s %s %s\n", "hello", "", NULL);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test integers
    printf("\n----- Testing %%d and %%i -----\n");
    ret1 = printf("Original: %d %i %d %i\n", 42, -42, INT_MAX, INT_MIN);
    ret2 = ft_printf("Custom  : %d %i %d %i\n", 42, -42, INT_MAX, INT_MIN);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test unsigned integers
    printf("\n----- Testing %%u -----\n");
    ret1 = printf("Original: %u %u %u\n", 42, UINT_MAX, 0);
    ret2 = ft_printf("Custom  : %u %u %u\n", 42, UINT_MAX, 0);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test hexadecimal
    printf("\n----- Testing %%x and %%X -----\n");
    ret1 = printf("Original: %x %X\n", 42, 42);
    ret2 = ft_printf("Custom  : %x %X\n", 42, 42);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test pointers
    int num = 42;
    void *ptr = &num;
    printf("\n----- Testing %%p -----\n");
    ret1 = printf("Original: %p %p\n", ptr, NULL);
    ret2 = ft_printf("Custom  : %p %p\n", ptr, NULL);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test percentage
    printf("\n----- Testing %%%% -----\n");
    ret1 = printf("Original: %%\n");
    ret2 = ft_printf("Custom  : %%\n");
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    // Test mixed formats
    printf("\n----- Testing mixed formats -----\n");
    ret1 = printf("Original: %c %s %d %i %u %x %X %p %%\n", 'A', "test", 42, -42, 42, 42, 42, ptr);
    ret2 = ft_printf("Custom  : %c %s %d %i %u %x %X %p %%\n", 'A', "test", 42, -42, 42, 42, 42, ptr);
    printf("Return values - Original: %d, Custom: %d\n", ret1, ret2);

    return (0);
}
```

### 4️⃣ Compile and Run the Test
```bash
gcc -Wall -Wextra -Werror main.c libftprintf.a && ./a.out
```

---

## 💡 What I Learned
- Working with variadic arguments (`va_list`, `va_start`, `va_arg`, `va_end`).
- Managing string formatting and conversion specifiers.
- Handling memory allocation with `malloc` and `free` to avoid leaks.
- Writing clean and modular C code for extensibility.
- Using Makefiles to build a library (`libftprintf.a`).

---

## 📜 Original Task
Check out the full assignment details: [here](ft_printf_assignment.pdf)

---

Built with precision at **42 Abu Dhabi**! ☕🚀

