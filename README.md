# This is an implementation of printf() function in in C language implemented solely with the use of C programming language.

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://github.com/narnat/printf)

## Project Overview
**_printf()** - This is an ALX-SE (Software Engineering) collaborative project. The objective of this project is to test our over understanding and its implementation into building a custom made version of the printf C fuction in the standard I/O library.

Table of Contents
=================
<!--ts-->
   * [Project Overview](#project-overview)
   * [Table of Contents](#table-of-contents)
   * [Project Requirements](#project-requirements)
   * [Allowed Functions and Macros](#allowed-functions-and-micros)
   * [Compilation Instructions](#compilation-instructions)
   * [Available Format Specifiers](#available-format-specifier)
   * [Task to be Accomplished](#task-to-be-accomplished)
   * [Installation Instruction](#installation-instructions)
   * [Code Test](#Code-Test)
   * [Authours](#Authours)
<!--te-->

*******************************************************************
## Project  Requirements
- Allowed editors: vi, vim, emacs
- All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
- All your files should end with a new line
- A README.md file, at the root of the folder of the project is mandatory
- Your code should use the Betty style. It will be checked using [betty-style.pl](https://github.com/holbertonschool/Betty/blob/master/betty-style.pl) and [betty-doc.pl](https://github.com/holbertonschool/Betty/blob/master/betty-doc.pl)
- You are not allowed to use global variables
- No more than 5 functions per file
- In the following examples, the main.c files are shown as examples. You can use them to test your functions, but you don’t have to push them to your repo (if you do we won’t take them into account). We will use our own main.c files at compilation. Our main.c files might be different from the one shown in the examples
- The prototypes of all your functions should be included in your header file called main.h
- Don’t forget to push your header file
- All your header files should be include guarded
- Note that we will not provide the _putchar function for this project

*****************************************************************************************
## Allowed Functions and Macros
- `write (man 2 write)`
- `malloc (man 3 malloc)`
- `va_start (man 3 va_start)`
- `va_end (man 3 va_end)`
- `va_copy (man 3 va_copy)`
- `va_arg (man 3 va_arg)`

*****************************************************************************************
## Compilation Instructions
- Your code will be compiled this way:
```$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c```
- As a consequence, be careful not to push any c file containing a `main` function in the root directory of your project (you could have a test folder containing all your tests files including `main` functions)
- Our main files will include your main header file (`main.h`): `#include main.h`
- You might want to look at the gcc flag `-Wno-format` when testing with your `_printf` and the standard `printf`. Example of test file that you could use:
```
arthur@ubuntu:~/printf$ cat main.c
#include <limits.h>
#include <stdio.h>
#include "holberton.h"

/**
 * main - Entry point
 *
 * Return: Always 0
 */
int main(void)
{
    int len;
    int len2;
    unsigned int ui;
    void *addr;

    len = _printf("Let's try to printf a simple sentence.\n");
    len2 = printf("Let's try to printf a simple sentence.\n");
    ui = (unsigned int)INT_MAX + 1024;
    addr = (void *)0x7ffe637541f0;
    _printf("Length:[%d, %i]\n", len, len);
    printf("Length:[%d, %i]\n", len2, len2);
    _printf("Negative:[%d]\n", -762534);
    printf("Negative:[%d]\n", -762534);
    _printf("Unsigned:[%u]\n", ui);
    printf("Unsigned:[%u]\n", ui);
    _printf("Unsigned octal:[%o]\n", ui);
    printf("Unsigned octal:[%o]\n", ui);
    _printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    _printf("Character:[%c]\n", 'H');
    printf("Character:[%c]\n", 'H');
    _printf("String:[%s]\n", "I am a string !");
    printf("String:[%s]\n", "I am a string !");
    _printf("Address:[%p]\n", addr);
    printf("Address:[%p]\n", addr);
    len = _printf("Percent:[%%]\n");
    len2 = printf("Percent:[%%]\n");
    _printf("Len:[%d]\n", len);
    printf("Len:[%d]\n", len2);
    _printf("Unknown:[%r]\n");
    printf("Unknown:[%r]\n");
    return (0);
}
arthur@ubuntu:~/printf$ gcc -Wall -Wextra -Werror -pedantic -Wno-format *.c
arthur@ubuntu:~/printf$ ./printf
Let's try to printf a simple sentence.
Let's try to printf a simple sentence.
Length:[39, 39]
Length:[39, 39]
Negative:[-762534]
Negative:[-762534]
Unsigned:[2147484671]
Unsigned:[2147484671]
Unsigned octal:[20000001777]
Unsigned octal:[20000001777]
Unsigned hexadecimal:[800003ff, 800003FF]
Unsigned hexadecimal:[800003ff, 800003FF]
Character:[H]
Character:[H]
String:[I am a string !]
String:[I am a string !]
Address:[0x7ffe637541f0]
Address:[0x7ffe637541f0]
Percent:[%]
Percent:[%]
Len:[12]
Len:[12]
Unknown:[%r]
Unknown:[%r]
arthur@ubuntu:~/printf$
```
## Available Format Specifiers
Function| Function Description | Format Specifier
--- | --- | ---
`print_char`| This function prints a character | `%c`
`print_percent` | This function prints a percentage symbol `%` | `%%`
`print_int` | This function prints integers | `%d` and `%i
`print_string` | This function prints a strive | `%s`
`print_binary` | This function prints binary numbers | `%b`
`print_octal` | This function prints numbers in base 8 | `%o`
`print_hex` | This function prints hexaldecimal numbers in lower case | `%x`
`print_HEX` | This function prints hexaldecimal numbers in upper case | `%X`
`print_unsigned` | This function prints unsigned integers | `%u`
`print_S` | This function prints hex value of non visible characters | `%S`
`print_address` | This function prints a pointer memory address | `%p`
`print_rev` | This function prints any string passed in reverse | `%r`
`print_rot13` | This function prints strings in rot13 format | `%R`
*****************************************************************************************
This repository contains the implementation of printf C function
Done by MaryIshola and Manifest
