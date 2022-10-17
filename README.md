# This is an implementation of printf() function in C language, implemented solely with the use of C programming language.

*****************************************************************************************

## Project Overview
**_printf()** - This is an ALX-SE (Software Engineering) collaborative project. The objective of this project is to test our overall understanding and implementation into building a custom made version of the printf C fuction in the standard I/O library
Table of Contents
=================
<!--ts-->
   * [Project Overview](#project-overview)
   * [Table of Contents](#table-of-contents)
   * [Project Requirements](#project-requirements)
   * [Allowed Functions and Macros](#allowed-functions-and-macros)
   * [Compilation Instructions](#compilation-instructions)
   * [Available Format Specifiers](#available-format-specifiers)
   * [Task to be Accomplished](#task-to-be-accomplished)
   * [Installation Instruction](#installation-instructions)
   * [Authors](#authors)
<!--te-->

*****************************************************************************************
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
#include "main.h"

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

*****************************************************************************************

## Available Format Specifiers
Function| Function Description | Format Specifier
--- | --- | ---
`print_char`| This function prints a character | `%c`
`print_percent` | This function prints a percentage symbol `%` | `%%`
`print_int` | This function prints integers | `%d` and `%i`
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
## Task to be Accomplished
<details>
<summary>
Click to Collapse
</summary>
<ul>
<li>-)- 0. I'm not going anywhere. You can print that wherever you want to. I'm here and I'm a Spur for life <i>mandatory</i>
</li><li> - 1. Education is when you read the fine print. Experience is what you get if you don't <i>mandatory</i>
</li><li> - 2. Just because it's in print doesn't mean it's the gospel  <i>mandatory</i>
</li><li> - 3. With a face like mine, I do better in print <i>#advanced</i>
</li><li> - 4. What one has not experienced, one will never understand in print <i>#advanced</i>
</li><li> - 5. Nothing in fine print is ever good news <i>#advanced</i>
</li><li> - 6. My weakness is wearing too much leopard print <i>#advanced</i>
</li><li> - 7. How is the world ruled and led to war? Diplomats lie to journalists and believe these lies when they see them in print <i>#advanced</i>
</li><li> - 8. The big print gives and the small print takes away <i>#advanced</i>
</li><li> - 9. Sarcasm is lost in print <i>#advanced</i>
</li><li> - 10. Print some money and give it to us for the rain forests <i>#advanced</i>
</li><li> - 11. The negative is the equivalent of the composer's score, and the print the performance <i>#advanced</i>
</li><li> - 12. It's depressing when you're still around and your albums are out of print <i>#advanced</i>
</li><li> - 13. Every time that I wanted to give up, if I saw an interesting textile, print what ever, suddenly I would see a collection <i>#advanced</i>
</li><li> - 14. Print is the sharpest and the strongest weapon of our party <i>#advanced</i>
</li><li> - 15. The flood of print has turned reading into a process of gulping rather than savoring <i>#advanced</i>
</li><li> - 16. All of the above functionality should work flawlessly <i>#advanced</i>
</ul>
</details>

*****************************************************************************************

## Installation Instruction
To be able to use this custom build `_printf` function, the only library requirement is the `<unistd.h>` library. Procedure for usage commences by first cloning this repo on to your local machine using the command below:
```
 $ git clone https://github.com/mqnifestkelvin/printf.git
```
As soon as cloning is completed, navigate into the printf directory using the command below:
```
 $ cd printf
```
Compilation of your code can be done using the command:
```
 $ gcc *.c code_of_interest_source_file -o output 
```
Another method is to use of the printf function as a static library by making use of the command:
```
gcc *.c
````
```
ar -rc libprintf.a *.o
```
```
ranlib liball.a
```
*****************************************************************************************
*****************************************************************************************
*****************************************************************************************
## Authors
# Manifest Chakalov and Mary Ishola 
