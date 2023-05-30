# C - printf

## Overview
This project is an implementation of our own `printf` function for educational purposes. We have named it `print()`. It takes one string argument (`str`) and any number of variable arguments. Variable arguments are managed by macros like `va_start`, `va_arg`, and `va_end`. A temporary buffer (`buff`) is used to construct the output buffer.

## Implementation
A while loop scans each character in the input string. Characters are copied to the output string one by one. When a `%` character is encountered, it is not copied to the output string. Instead, the next character is checked to determine the formatting character. This character specifies how to format the argument for output. Our implementation supports the following formatting characters: `c` for character, `d` for decimal integer, `x` for hexadecimal, and `s` for strings.

The appropriate argument variable is selected using `va_arg()` and converted to a string format before being appended to the output string. Characters can be copied as-is, while integers are converted to strings using the `itoa()` function.

This process repeats until the input string is fully processed. The resulting output string is then passed to `fwrite()` for printing to `stdout`. The function returns the number of characters printed (excluding the null byte used to end output to strings).

## Tasks
1. Write a function that produces output according to a format.
    - Prototype: `int _printf(const char *format, ...);`
    - Returns: the number of characters printed (excluding the null byte used to end output to strings)
    - Writes output to `stdout`, the standard output stream
    - Handles the following conversion specifiers: `c`, `s`, `%`
2. Handle the following conversion specifiers: `d`, `i`
3. Create a man page for your function.
4. Handle the following custom conversion specifier: `b` (converts an unsigned int argument to binary)
5. Handle the following conversion specifiers: `u`, `o`, `x`, `X`
6. Use a local buffer of 1024 chars in order to call write as little as possible.
7. Handle the following custom conversion specifier: `S` (prints a string with non-printable characters printed as `\x` followed by their ASCII code value in hexadecimal)

## Limitations
- Flag characters are not handled
- Field width is not handled
- Precision is not handled
- Length modifiers are not handled


Authors:
ISMAEL ABDULAHI
DINAR TSEGAEAB
