# Section 1: Make Python more elegant

## Keep up with the updates



All the major changes from python2 to python3 [Offical guidance from Python2 to Python3](https://docs.python.org/3/howto/pyporting.html)

| Function print                | print ("hello")                                              | print "hello"                                                |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Division of Integers          | Whenever two integers are divided, you get a float value     | When two integers are divided, you always provide integer value. |
| Unicode                       | In Python 3, default storing of strings is Unicode.          | To store Unicode string value, you require to define them with "u". |
| Syntax                        | The syntax is simpler and easily understandable.             | The syntax of Python 2 was comparatively difficult to understand. |
| Rules of ordering Comparisons | In this version, Rules of ordering comparisons have been simplified. | Rules of ordering comparison are very complex.               |
| Iteration                     | The new Range() function introduced to perform iterations.   | In Python 2, the xrange() is used for iterations.            |
| Exceptions                    | It should be enclosed in parenthesis.                        | It should be enclosed in notations.                          |
| Leak of variables             | The value of variables never changes.                        | The value of the global variable will change while using it inside for-loop. |
| Function annotation syntax    |                                                              |                                                              |



If you are still writing code in Python2, using the `__future__` package:

```python
from __future__ import absolute_import
from __future__ import division
from __future__ import print_function
```



New features of python

1. Python 3.8

   - Assignment expressions

   - Positional-only parameters

2. Python 3.7

   - Postponed Evaluation of Annotations
   - Build-in `breakpoint()` calls 
   - New `dataclass`

3. Python 3.6
   - f-string
   - underscores in numeric literals
   - New `secrets` module

4. Python 3.5
   - `typing` and `zipapp` new build-in module
   -  a new matrix multiplication operator: `a @ b`
5. Python 3.4
   - `asyncio`
   - `pathlib`



Will it happen in Python 4 again? 

## Make your code more readable

1. [Google style](https://google.github.io/styleguide/pyguide.html) and [Numpy doctring](https://google.github.io/styleguide/pyguide.html)

2. `Pylint` style checking and grammar checking (pep8, )

**Import**

1. Never use relative names import.

   ```python
   import x              # import package and modules
   from x import y       # y is the module without prefix
   from x import y as z  # two modules have the same name or the name is too long
   import y as z         # only when z is a standard abbreviation, like np for numpy
   ```

2. Avoid global variables

3. Avoid mixing tab and spaces (always use space)

4. Naming:

   | Type                       | Public               | Internal                          |
   | -------------------------- | -------------------- | --------------------------------- |
   | Packages                   | `lower_with_under`   |                                   |
   | Modules                    | `lower_with_under`   | `_lower_with_under`               |
   | Classes                    | `CapWords`           | `_CapWords`                       |
   | Exceptions                 | `CapWords`           |                                   |
   | Functions                  | `lower_with_under()` | `_lower_with_under()`             |
   | Global/Class Constants     | `CAPS_WITH_UNDER`    | `_CAPS_WITH_UNDER`                |
   | Global/Class Variables     | `lower_with_under`   | `_lower_with_under`               |
   | Instance Variables         | `lower_with_under`   | `_lower_with_under` (protected)   |
   | Method Names               | `lower_with_under()` | `_lower_with_under()` (protected) |
   | Function/Method Parameters | `lower_with_under`   |                                   |
   | Local Variables            | `lower_with_under`   |                                   |

   

5. Avoid nested class and functions, use the '_' prefix instead

6. Lambda functions should only used for one-lines

7. Only use simple conditional expressions in one-lines

   ```python
   x = 1 if (condition) else 2
   #>
   if condition: func(foo)
   ```

8. Use the “implicit” false if possible. In Python, all 'empty' values are False like: `0, '', [], {}`

   ```python
   #> Yes
   users = []
   if not users:
       print('No users')
   #> No    
   if users == []:
       print('No users')
   ```

9. Shebang Line, used for a file that can be execute directly

10. `with` statement to handle files and sockets

   ```python
   with open("hello.txt") as hello_file:
       for line in hello_file:
           print(line)
   ```

11. TODO comments

    ```python
    # TODO(u1@gmail.com): Fix ***bug in March
    # TODO(Tom) Add support for Python 3.8
    ```

12. Main

    ```python
    def main():
        ...
    
    if __name__ == '__main__':
        main()
    ```

12. Be consistent!





**Not decided yet**

1. Doc-string for class and functions. Adding to the package section? Mainly the doc-string style of google and bumpy
2. Function length, keep function short, no more than 40 lines.  Add to the functional programming section



## Make the output more clear

String manipulation

1. Understand the string

```python
b'binary string'
r'row string'
u'unicode'
```

2. Common [string operation](https://docs.python.org/3.8/library/string.html) and string format

   **In the package section, the `__format__()` and `__repr__` should be mentioned**



3. Formatting the output
   - C-style string formatting "%s" % var
   - "{}".format
   - f-string
   - template



## The implementation of Python

Cover the CPython and Jython, IronPython and PyPy

- CPython: The official python implementation

-    Jython: Java implementation, make python run on JVM
- IronPython: A Python written in C#, make python run on .Net virtual machine

- PyPy: just-in-time compilation, 7 times faster than CPython in average

For more complete list of different implementation see [this](https://wiki.python.org/moin/PythonImplementations)

