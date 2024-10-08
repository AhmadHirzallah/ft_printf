<p align="center">
   <img src="https://github.com/AhmadHirzallah/ft_printf/blob/main/banner.png">
</p>

<p align="center">
   <img src="https://img.shields.io/badge/ft_printf-122%2F100-brightgreen?style=flat-square"/>
   <img src="https://img.shields.io/badge/language-C-blue.svg?style=flat-square"/>
   <img src="https://img.shields.io/badge/variadic-functions-important.svg?style=flat-square"/>
</p>

# 🖨️ ft_printf - Custom printf Implementation

**ft_printf** is a custom implementation of the C standard library's `printf()` function, developed as part of the 42 school curriculum. This project challenges developers to handle **variadic functions**, **formatted output**, and **multiple argument types**, making it a foundational step in mastering advanced C programming.

## 📚 Overview

The **ft_printf** project recreates the functionality of `printf()`, focusing on variadic functions and formatted output. It supports a wide range of format specifiers (e.g., `%d`, `%s`, `%x`) and provides additional features like flag handling and precision management.

The project aims to build a reusable library (`libftprintf.a`) that can be integrated into other projects, such as the **Libft** library. This is an excellent opportunity to strengthen your understanding of low-level C programming, memory management, and function handling.

---

## ✨ Features

- **Core Functionality**:
  - Implements the core features of the `printf()` function.
  - Supports the following format specifiers:
    - `%c`: Character
    - `%s`: String
    - `%p`: Pointer (in hexadecimal)
    - `%d`, `%i`: Signed integers
    - `%u`: Unsigned integers
    - `%x`, `%X`: Hexadecimal (lowercase/uppercase)
    - `%%`: Literal `%` symbol

- **Variadic Functions**:
  - Uses `va_start()`, `va_arg()`, `va_copy()`, and `va_end()` to manage variable-length arguments.
  
- **Memory Management**:
  - Ensures proper allocation and deallocation of memory during execution.

- **Bonus Features**:
  - Handles additional formatting flags: `-`, `0`, `.`, `#`, `+`, and space.
  - Supports field width and precision management for more advanced formatting.

---

## 📂 File Structure

The project is organized into several key files:

### 📜 Core Files

- `ft_printf.c`: Main function that parses the format string and handles different argument types.
- `ft_flush_buffer.c`: Manages buffered output to improve efficiency by reducing system calls.
- `ft_render_char_to_buf.c`, `ft_render_str_to_buf.c`, `ft_render_nbrs_to_buf.c`: Functions responsible for rendering characters, strings, and numbers into the output buffer.
- `ft_itoa_base_into_bfr.c`: Converts numbers to different bases and stores them in the buffer.
- `ft_set_pad_spaces_nbr_cases.c`, `ft_set_pad_zeros_nbr_cases.c`: Handles padding with spaces and zeros for formatted output.

### 📜 Bonus Files

- `ft_printf_bonus.c`: Handles extended formatting features like flags (`-`, `0`) and field width/precision management.

---

## 🔗 Libft Integration

This project builds on top of the **Libft** library, which provides essential utility functions for string manipulation, memory handling, and list management. These functions are used extensively in **ft_printf** to simplify development and ensure reusability.

You can find the **Libft** repository [here](https://github.com/AhmadHirzallah/Libft).

---

## ⚙️ Compilation

The project includes a `Makefile` to automate compilation:

- `make`: Compiles the core **ft_printf** library and generates `libftprintf.a`.
- `make bonus`: Compiles the bonus implementation with extended flag support.
- `make clean`: Removes object files.
- `make fclean`: Removes both object files and the compiled library.
- `make re`: Cleans and recompiles everything from scratch.

---

## 🛠️ Installation

To compile and use the **ft_printf** library in your own projects:

```bash
# Clone the repository
git clone https://github.com/AhmadHirzallah/ft_printf.git

# Navigate to the project directory
cd ft_printf

# Compile the library
make
```

To compile the bonus version:

```bash
make bonus
```

---

## 🧪 Usage

Once compiled, you can use **ft_printf** just like the standard `printf()` function:

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Character: %c\n", 'A');
    ft_printf("String: %s\n", "Hello, World!");
    ft_printf("Pointer: %p\n", &main);
    ft_printf("Decimal: %d\n", 42);
    ft_printf("Unsigned: %u\n", 123456);
    ft_printf("Hex: %x\n", 255);
    ft_printf("Percent: %%\n");

    return 0;
}
```

---

## 🔍 Variadic Functions

A crucial aspect of **ft_printf** is its use of **variadic functions**, which allow the function to accept a variable number of arguments. This is achieved using macros from the `stdarg.h` library:

- **`va_start`**: Initializes the argument list.
- **`va_arg`**: Retrieves the next argument in the list.
- **`va_copy`**: Copies one argument list to another.
- **`va_end`**: Cleans up the argument list.
