# A Brief on Programming Paradigms

Before discussing the various concepts around OOP, let's first understand what a programming paradigm is.

A programming paradigm is a way of thinking about and approaching problems. It is a way of structuring your thoughts and actions to solve a problem. It is a way of organizing your code to solve a problem. Each paradigm consists of certain structures, features, and opinions about how common programming problems should be tackled.

Programming paradigms are not languages or tools. You can't "build" anything with a paradigm. They're more like a set of ideals and guidelines that many people have agreed on, followed, and expanded upon.

Programming languages aren't always tied to a specific paradigm. There are languages that have been built with a certain paradigm in mind and have features that facilitate that kind of programming more than others (Haskel and functional programming is a good example). But most languages are multi-paradigm, meaning they can be used to write code in different paradigms. Eg: Python, Java, C++, etc.

## Popular Programming Paradigms

### 1. Imperative Programming

Simply said, Imperative programming focuses on describing how a program operates, step by step.

It consists of sets of detailed instructions that are given to the computer to execute in a given order. It's called "imperative" because as programmers we dictate exactly what the computer has to do, in a very specific way.

For instance, if we want to find the factorial of a number:

```python
def factorial(n):
    result = 1
    for i in range(1, n+1):
        result *= i
    return result
```

Here, we are telling the computer to first assign the value 1 to the variable `result`, then iterate over the range of numbers from 1 to `n+1` and multiply the value of `result` with the current value of `i` and assign the result to `result`, and finally return the value of `result`.

### 2. Procedural Programming

Procedural programming is a style of writing code where you organize your program as a sequence of procedures or functions. Each procedure represents a specific task or action, and the program's execution follows a linear flow, moving from one procedure to the next. It's like following a set of ordered steps to achieve a goal, similar to a recipe or a manual. The focus is on breaking down the program's logic into smaller reusable units. It's about how to achieve a task using a sequence of steps.

For instance, let's look at a complex example of a program that calculates the average of a list of numbers:

```python
def get_sum(numbers):
    sum = 0
    for number in numbers:
        sum += number
    return sum

def get_average(numbers):
    sum = get_sum(numbers)
    average = sum / len(numbers)
    return average

numbers = [1, 2, 3, 4, 5]
average = get_average(numbers)
print(average)
```

Here, we have two functions, `get_sum` and `get_average`. The `get_sum` function calculates the sum of all the numbers in the list, and the `get_average` function calculates the average of the numbers in the list. The `get_average` function uses the `get_sum` function to calculate the sum of the numbers in the list and then divides it by the length of the list to get the average.

### 3. Functional Programming

Functional programming is a style of writing code where you organize your program as a set of functions. Each function represents a specific task or action, and the program's execution follows a flow of function calls, moving from one function to the next. It's like following a set of ordered steps to achieve a goal, similar to a recipe or a manual. The focus is on breaking down the program's logic into smaller reusable units. It's about how to achieve a task using a sequence of steps.

Functional programming is a way of writing code where you treat actions like mathematical functions. These functions take input and provide an output, but they don't change anything outside themselves. It's like putting together building blocks that do specific tasks without affecting other blocks.

#### How is it different from procedural programming?

The difference between procedural programming and functional programming is that in procedural programming, the functions are not independent of each other. They depend on each other to achieve a task. Whereas in functional programming, the functions are independent of each other. They don't depend on each other to achieve a task.

Still not clear? Okay, let's look at an example.

Imagine you're writing a program to calculate discounts on shopping items. In functional programming:

```python
def get_discounted_price(price, discount):
    discounted_price = price - (price * discount)
    return discounted_price

original_price = 100
discount = 0.1

discounted_price = get_discounted_price(original_price, discount)
print(discounted_price)
```

Here, we have a function called `get_discounted_price` that takes the original price and the discount as input and returns the discounted price. The function doesn't depend on any other function to calculate the discounted price. It's independent. It doesn't modify any external variables or have side effects.

Now, let's see how the same discount calculation might look in a procedural programming style:

```python
def calculate_discount(item_price, discount_rate):
    discount = item_price * discount_rate
    discounted_price = item_price - discount
    return discounted_price

original_price = 100
discount_rate = 0.2 

final_price = calculate_discount(original_price, discount_rate)
print("Original price:", original_price)
print("Discounted price:", final_price)
```

In this procedural example, the calculate_discount function not only calculates the discount but also updates the original_price variable within the function. The main program then prints both the original and discounted prices. The calculate_discount function calculates the discount and directly modifies the original_price variable, which could affect other parts of the program.

> The main difference here is that functional programming emphasizes separate, isolated functions that don't change external state, while procedural programming may involve functions that modify shared variables or data.

### 4. Declarative Programming

Declarative programming is all about hiding away complexity and bringing programming languages closer to human language and thinking. It's the direct opposite of imperative programming in the sense that the programmer doesn't give instructions about how the computer should execute the task, but rather on what result is needed.

For instance, let's look at a simple example of a program that calculates the average of a list of numbers:

```python
numbers = [1, 2, 3, 4, 5]
average = sum(numbers) / len(numbers)
print(average)
```

Here, we are not telling the computer how to calculate the average of the numbers in the list. We are just telling it what we want, and it figures out how to do it.

Another good example coule be:

```python
numbers = [1, 4, 3, 6, 7, 8, 9, 2]
filtered_numbers = list(filter(lambda num: num > 5, numbers))
print(filtered_numbers)  # Output: [6, 7, 8, 9]
```

Here, we are not telling the computer how to filter the numbers in the list. We are just telling it what we want, and it figures out how to do it. What's nice about this is that it's easier to read and comprehend, and often shorter to write. It's also easier to maintain and debug. Python's filter, map, and reduce functions are good examples of declarative programming.

> An important thing to notice about declarative programming is that under the hood, the computer processes this information as imperative code anyway.  the computer still iterates over the array like in a for loop, but as programmers we don't need to code that directly. What declarative programming does is to hide away that complexity from the direct view of the programmer.