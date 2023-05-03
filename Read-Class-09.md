# Dunder Methods

Dunder methods, also known as special methods or magic methods, are predefined methods in Python that allow programmers to enrich their classes. These methods have a double underscore before and after their name, such as init and str. They allow developers to emulate the behavior of built-in types and tap into language features like sequences, iteration, operator overloading, attribute access, and more. Dunder methods are essential for writing Pythonic code and for implementing APIs. They can be used to initialize objects, define object representation, enable iteration, overload operators, support context managers, and more. By using dunder methods, developers can make their code more expressive and easier to use.

# Statistics - Probability

This article is a tutorial that explains the basics of probability in Python for data science. Probability is an essential concept to understand when studying statistics as it is used in both working and daily life. At its most basic level, probability seeks to answer the question, "What is the chance of an event happening?" The article uses the example of coin tosses to illustrate how probability works. The sample space is the set of all possible events that can happen, and we count how many times our event of interest can occur and divide it by the sample space to calculate the probability of an event occurring. The article then demonstrates how statistics and probability are related, and how given enough data, statistics enables us to calculate probabilities using real-world observations. The article concludes by highlighting that statistics provides the tools to test theoretical probability using data, and that probability is crucial in making predictions about how often events will happen.

## What is the purpose of dunder methods in Python? Provide an example of a commonly used dunder method.

Dunder methods (short for double underscore methods) in Python are special methods that have double underscores before and after their names. They are also called magic methods or special methods. These methods are used to define how instances of a class behave with respect to built-in operations or behaviors in Python.

For example, the __init__() method is a dunder method used to initialize an instance of a class with some default values. Another commonly used dunder method is __str__() which returns a string representation of the object. When we print an object or convert it to a string, this method is called by Python to get the string representation of the object.

Here's an example of the __str__() method in action:

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"{self.name} is {self.age} years old."

person = Person("John", 30)
print(person) # output: John is 30 years old.
```

## Describe the Python statistics module and give an example of a function within the module that can be used to perform a common statistical operation.

The Python statistics module is a built-in module that provides functions for calculating basic statistical operations on numerical data. The module contains various functions for performing measures of central tendency (such as mean, median, and mode), measures of variability (such as variance and standard deviation), and other statistical operations (such as correlation and regression).

Here is an example of how to use the mean() function from the statistics module to calculate the average of a list of numbers:

```
import statistics

data = [1, 2, 3, 4, 5]

mean_value = statistics.mean(data)

print(mean_value)  # Output: 3
```