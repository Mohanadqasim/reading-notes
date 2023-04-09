# Read-Class-03
## Read & Write Files in Python

File handling is an important activity in every web app. The types of activities that you can perform on the opened file are controlled by Access Modes. These describe how the file will be used after it has been opened.

These modes also specify where the file handle should be located within the file. Similar to a pointer, a file handle indicates where data should be read or put into the file.

In Python, there are six methods or access modes, which are:

1. Read Only ('r’): This mode opens the text files for reading only. The start of the file is where the handle is located. It raises the I/O error if the file does not exist. This is the default mode for opening files as well.

2. Read and Write ('r+’): This method opens the file for both reading and writing. The start of the file is where the handle is located. If the file does not exist, an I/O error gets raised.

3. Write Only ('w’): This mode opens the file for writing only. The data in existing files are modified and overwritten. The start of the file is where the handle is located. If the file does not already exist in the folder, a new one gets created.

4. Write and Read ('w+’): This mode opens the file for both reading and writing. The text is overwritten and deleted from an existing file. The start of the file is where the handle is located.

5. Append Only ('a’): This mode allows the file to be opened for writing. If the file doesn't yet exist, a new one gets created. The handle is set at the end of the file. The newly written data will be added at the end, following the previously written data.
6. Append and Read (‘a+’): Using this method, you can read and write in the file. If the file doesn't already exist, one gets created. The handle is set at the end of the file. The newly written text will be added at the end, following the previously written data.

## Python Exceptions
Python exceptions are a mechanism for handling errors and other exceptional events that occur during program execution. When an error occurs in a Python program, the interpreter raises an exception, which can then be caught and handled by the program.

Exceptions are represented by objects in Python, and there are many built-in exception classes provided by the language. Some common built-in exceptions include SyntaxError, TypeError, ValueError, and KeyError. These exceptions are raised when there is an error in the syntax of the program, when an operation is performed on a data type that is not appropriate for that operation, when a value is invalid, or when a key is not found in a dictionary, respectively.




## File Objects - Reading and Writing to Files
File objects in Python are used to interact with files on the computer's file system. In order to read from or write to a file, you must first open it in the appropriate mode. There are several modes available for opening a file, including 'r' (read), 'w' (write), 'a' (append), and 'x' (exclusive creation).

### What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?
The with statement in Python is used for resource management, and it can be used when working with file objects to manage the resources associated with opening and closing a file.

When a file is opened in Python, system resources are allocated to it, such as memory and input/output operations. If the file is not closed properly, these resources will be unavailable for other processes or programs. The with statement provides a way to ensure that the file is always closed, even if an exception is raised while the program is working with the file.

### Explain the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. Provide examples of when to use each method.
In Python, file objects have two methods for reading data from a file: read() and readline(). While both methods can be used to read data from a file, they work in different ways and are better suited for different use cases.

The read() method reads the entire contents of the file and returns it as a single string. 
On the other hand, the readline() method reads a single line from the file and returns it as a string. 

### Briefly describe the concept of exception handling in Python. How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? Provide a simple example.
Exception handling in Python refers to the process of detecting and responding to errors or unexpected situations that can occur during the execution of a program. When an error occurs in a Python program, it raises an exception, which can be handled using the try, except, and finally blocks.

The try block is used to enclose the code that might raise an exception. If an exception is raised within the try block, it will be caught by one of the except blocks, which are used to handle specific types of exceptions. The finally block is optional and is used to execute code that should always run, regardless of whether an exception was raised or not.

Here's a simple example that illustrates how to use the try, except, and finally blocks to handle exceptions:


```
try:
    # Attempt to divide 10 by 0
    result = 10 / 0
    print(result)
except ZeroDivisionError:
    # Handle the ZeroDivisionError exception
    print("Error: Division by zero!")
finally:
    # Execute this code regardless of whether an exception was raised or not
    print("The program has finished executing.")
```

In this example, we have a try block that attempts to divide the number 10 by zero, which will raise a ZeroDivisionError exception. We then have an except block that specifically handles this type of exception and prints an error message to the console. Finally, we have a finally block that prints a message indicating that the program has finished executing, regardless of whether an exception was raised or not.

The output of this code will be:


```
Error: Division by zero!
The program has finished executing.
```

As you can see, the except block was executed because an exception was raised within the try block, and the finally block was executed afterwards to indicate that the program has finished executing.

By using the try, except, and finally blocks in Python, you can handle exceptions and ensure that your code runs smoothly, even when unexpected errors occur.