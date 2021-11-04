# VARIADIC FUNCTIONS

- Functions with variadic arguments are just functions that has a variable
argument list.
- A huge, really huge believe me, functions has variable arguments. It is the famous printf function.
- Another example/use case: It should be really useful to use a variadic
function for testing our code, by writing a wrapper around prinft that
receives a variable number of arguments to test a code, including the
function to be tested.


# CALLING THE FUNCTION

- One just needs to pass at least one argument. This argument contains information about the other ones. It is usually called as formatter. 

- In printf function it is a string formatter, and contains placeholders that states, sequentialy, the types of variables that should be put in STDOUT file descriptor.

## A typical use case 

```c
// pre-compilation directives, main function, ...

printf("This is a %s formatter in the printf function.\nft_ means fourty-two (%d) at %d Network\n", "string", 42, 42);

> This is a string in the printf function.
> ft means fourty-two (42) at 42 Network.
```

# ACCESSING ARGUMENTS

- As one can see, they don't have any kind of identification. So in order to access the arguments, the following macros should be used, and will be described accordingly: `va_start`, `va_arg` and `va_end`. A variable of the type `va_list` should be declared as well.
  - `va_list`: It receives a pointer that points to the call stack, data structure that holds all the variadic arguments passed into the function. More specifically, it is a data structure that stores information about the active subroutines of a computer program;
  - `va_start(va_list_type_variable, last_argument_before_reticences)`: Passes a reference in the call stack of first variadic element to the `va_list` type variable defined above;
  - `va_arg(va_list_type_variable, typeof(variadic_arguments))`: This macro returns one argument at a time and auto-increments the pointer of the `va_list` variable.
    - int, double, pointer (size_t), char are allowed. 
	- shorts or floats are not allowed
  - `va_end(va_list_type_variable)`: It is a formality that makes possible to the code to be portable to any OS.

# BASIC IMPLEMENTATION

 - This implementation is quite simple. It will print arguments while the index is lower than the numbers passed into the function, and than printed out to the STDOUT fd

```c
#include <stdio.h>
#include <stdarg.h>

void	ft_print_int(int, ...);

int	main(int argc, char **argv)
{
	ft_print_int(3, 24, 26, 256, 312, 512);
	return (0);
}

void	ft_print_int(int num, ...)
{
	va_list	ap;
	int		i;
	int		value;

	i = 0;
	value = 0;
	va_start(ap, num);
	while (i < num)
	{
		value = va_arg(ap, int);
		printf("index %d: %d\n", i, value);
		++i;
	}
	va_end(ap);
}
```