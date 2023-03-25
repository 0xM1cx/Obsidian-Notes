```toc
```

## Basics
- `print()` - The word print is the function name. This is a function that is used to print an output in the terminal.

>To distinguish ordinary words from function names, place **a pair of empty parentheses**

The function name(e.g. print) along with the parentheses and argument(s), forms the **function invocation**

What happens when Python encounters an invocation like below?
```python
function_name(argument)
```

-   First, Python checks if the name specified is **legal** (it browses its internal data in order to find an existing function of the name; if this search fails, Python aborts the code);
-   second, Python checks if the function's requirements for the number of arguments **allows you to invoke** the function in this way (e.g., if a specific function demands exactly two arguments, any invocation delivering only one argument will be considered erroneous, and will abort the code's execution);
-   third, Python **leaves your code for a moment** and jumps into the function you want to invoke; of course, it takes your argument(s) too and passes it/them to the function;
-   fourth, the function **executes its code**, causes the desired effect (if any), evaluates the desired result(s) (if any) and finishes its task;
-   finally, Python **returns to your code** (to the place just after the invocation) and resumes its execution.