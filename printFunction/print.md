# Explanation of Print function 
```python
print(objects,sep='',end='',file=sys.out,flush=False)
```
* **object(s)**	Any object, and as many as you like. Will be converted to string before printed
* **sep='separator'** Optional. Specify how to separate the objects, if there is more than one. Default is ' '

```python
    print("Nripender ","Radhe",sep='\n')
    """ Out put will be 
        Nripender
        Radhe
    """
```

* **end='end'**	Optional. Specify what to print at the end. Default is '\n' (line feed)
```python
   print("Nripender ","Radhe",end="\t")
   print("Nripender ","Radhe")

    """ Output will be 
        Nripender  Radhe        Nripender  Radhe
    """
```
* **file**	Optional. An object with a write method. Default is sys.stdout
* **flush**	Optional. A Boolean, specifying if the output is flushed (True) or buffered (False). Default is False

## Flush 
* Generally, the input and output functions store the data into a buffer to improve the program’s performance. Therefore, to lower the number of system calls, the data is stored in a buffer first and then written on the screen, instead of writing it to the screen or file, character by character, etc.
* The flush argument of the print() function can be set to True to stop the function from buffering the output data and forcibly flush it. If the flush argument is set to True, the print() function will not buffer the data to increase the efficiency and will keep flushing it on each call.
* Example:
```python
 print("This is my string", flush=True)
```
* The example code demonstrates how to make the print() function to forcibly flush the print output in Python
# File Option
* The default value of the file argument is sys.stdout which prints the output on the screen

* Example of **sys.stdout.write**
``` python
import sys
sys.stdout.write("This is my string")
sys.stdout.flush()
```
* We can specify any other output target which must be an object with write(string) method

```python
sourceFile = open('demo.txt', 'w')
print('Hello, Python!', file = sourceFile)
sourceFile.close()
```
* ### Redirect the Standard Output Stream to File

```python
import sys
 
# Saving the reference of the standard output
original_stdout = sys.stdout    
 
with open('demo.txt', 'w') as f:
    sys.stdout = f 
    print('Hello, Python!')
    print('This message will be written to a file.')
    # Reset the standard output
    sys.stdout = original_stdout 
 
print('This message will be written to the screen.')
```



* ## Let us boost our Mind with some Example
* Our main Objective is to Understand the functionality of print statement
* Write a program show your name using ***
* Name is (We have to print this )
```
""" *       * *   * * * *
    * *     * *  *  *    *
    *   *   * * *   *    *
    *     * * *  *  *    *
    *       * *   * * * *    """
```
* Different Programs

1. ```python

    x = """ 
    *       * *   * * * *
    * *     * *  *  *    *
    *   *   * * *   *    *
    *     * * *  *  *    *
    *       * *   * * * *    """
    print(x)
    ```
1. ```python
    print("*        * *  * * * *    ")
    print("* *      * * *  *     *   ")
    print("*   *    * **   *     *   ")
    print("*     *  * * *  *     *   ")
    print("*        * *  * * * *     ")
   ```
1. ```python
    print("*        * *  * * * *    ",
          "* *      * * *  *     *   ",
          "*   *    * **   *     *   ",
          "*     *  * * *  *     *   ",
          "*        * *  * * * *     ",
          sep="\n")
    ```
1. ```python
    print("*","*",sep="\t ",end=' ')
    print("*","*",sep="  ",end=' ')
    print("*","*","*",sep=" ",end='\n')

    print("* *","*",sep="\t ",end=' ')
    print("*","*",sep=" ",end='  ')
    print("*","*",sep="\t\b\b",end='\n')

    print("*   *","*",sep="\t ",end=' ')
    print("*","*",sep="",end='   ')
    print("*","*",sep="\t\b\b",end='\n')

    print("*\t\b\b*","*",sep="  ",end=' ')
    print("*","*",sep=" ",end='  ')
    print("*","*",sep="\t\b\b",end='\n')

    print("*","*",sep="\t ",end=' ')
    print("*","*",sep="  ",end=' ')
    print("*","*","*",sep=" ",end='\n')
    ```

   