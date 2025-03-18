# Section 3
This section is our first look at actually doing code in Java. We will be working with JShell first and then move into an IDE. 

## Table of Contents
- [Chapter 15 - Writing our First Code](#chapter-15---writing-our-first-code)
- [Chapter 16 - Introduction to variables, keywords and integer data types](#chapter-16---introduction-to-variables-keywords-and-integer-int-data-types)
- [Chapter 17 - Comprehensive Introduction to using variables in Java](#chapter-17---comprehensive-introduction-guide-to-using-variables-in-java-expressions)
- [Chapter 18 - Exploring Integer Ranges and Wrapper Classes](#chapter-17---comprehensive-introduction-guide-to-using-variables-in-java-expressions)
- [Chapter 19 - Understanding Short, Byte, and Long Data Types](#chapter-19---understanding-byte-short-and-long-data-types)
- [Chapter 20 - Understanding Casting with Numeric Primitives in Java](#chapter-20---understanding-casting-with-numeric-primitives-types-in-java)
- [Chapter 21 - Primitive Types Challenge: Appying Your Knowledge](#chapter-21---primitive-types-challenge-applying-your-knowledge)
- [Chapter 22 - Working with Float and Double: Precision in Floating Point Nubmers](#chapter-22---working-with-float-and-double-precision-in-floating-point-numbers)
- [Chapter 23 - Understanding Floating-Point Precision: A Practical Challenge in Java](#chapter-23---understanding-floating-point-precision-a-practical-challenge-in-java)

---

## Chapter 15 - Writing Our First Code
This will be the "Hello World" program and discusses basic error handling. 
 - We created our first code, the standard, HelloWorld program but did it from JShell instead of actual code like the one seen in Section 2. 
 - In JShell we typed, `System.out.print("Hello World");`
 - After hitting `Enter` the code does exactly what you might expect, it prints "Hello World" on the command prompt. 
 - **Challenge** The instructor asks us to modify the command to make it say "Hello Tim". 
 - **Solution** this was easily solved by typing `System.out.print("Hello, Tim");` but we did so using the `Up` arrow and overwriting the words. 

### Error Handling
In order to learn some of the common mistakes made by programmers, we tried a few different things that caused Java to report errors. 
- First, if we omit the closing parenthesis `System.out.print("Hello, Tim"` we will be prompted wth the `...>` prompt because JShell assumes we wanted to add more lines to our code. If we just type the closing statements on the line `...> );` the code will work. 
- Next, if we forget to close the string of text, `System.out.print("Hello, Tim);` we get a different error: 

    ```java
    
        Error:
        Unclosed string literal
        System.out.print("Hello, Tim);
    
    ```
   
    - This is because the double quotes are considered a String Literal that we did not close. 
- Unlike JavaScript or Python, we cannot enclose strings in a single quote ('). If we tried that, `System.out.print('Hello, Tim');` we will get basically the same error as the one above:

    ```java
    
        Error:
        Unclosed character literal
        System.out.print('Hello, Tim');
    
    ```
    
    - This is because the only acceptable way to designate a string in Java is with double quotes. 

[Back to Top](#table-of-contents)

---

## Chapter 16 - Introduction to Variables, Keywords, and Integer (int) data types. 
This section will delve deeper into using some basic Java elements to produce more detailed code. 

### Keywords
- A keyword is **any one of a number of reserved words, that have a predefined meaning in the Java Language**
- In Java, all code is *case sensitive* including ***keywords***
    - `int` in Java is **NOT** the same thing as `Int`
    - in this example, `int` is a keyword in Java but `Int` is not. 
- To review keywords at any time, go to this link: [Java 17 Keywords](https://docs.oracle.com/javase/specs/jls/se17/html/jls-3.html#jls-3.9)
    - Some of the most important keywords in this list include:
        - boolean
        - byte
        - char
        - double
        - float
        - int
        - long
        - short

### Variables
- Variables are **a way for our programs to store information on the computer**
- They can be defined in our program and can be **accessed by any name we give them**
- Most of the variables will be stored in the computer's RAM. 
- Variables can also be changed throughout the program's life.
- We established a variable using `int myFirstNumber = 5;` and the JShell shows us that it accepted that value: `myFirstNumber ==>5`
- When we create a statement like this, it is considered a *Declaration Statement*
    - A *declaration statement* is used to define a variable by indicating the data type, and the name, then optionally set the variable to a specific data type. The statement is broken down here:
        - Declaring a type of *int* 
        - Naming the variable *myFirstNumber*
        - Set the value of myFirstNumber to *5*
    - An *expression*  is a coding construct **that evaluates to a single value**

### Challenge
In this challenge, the instructor wants us to find a way to have Java print out the value we have stored in our myFirstNumber variable. 

- The code that seems to make the most sense to accomplish this is:
    ```java
    int myFirstNumber = 5;
    System.out.print(myFirstNumber);
    ```
- When I performed this line of code, I did get the expected result with the console printing out the number 5. 
- Had I put `System.out.print("myFirstNumber")` it would have simply typed the word *myFirstNumber* because we declared a string literal. 

### Updating a variable
Should we want to change a variable to something new in the code, it will work very similar to how we initially declare a variable but without the data type. 
- We want to change the value of *myFirstNumber* to 10 instead of 5. 
- By typing: 
    ```java
    myFirstNumber = 10;
    System.out.print(myFirstNumber);
    ```
the system will change the number to *10* and then display that. 

### Challenge - Update and Print the variable
In this challenge, the instructor wants us to modify the value of myFirstNumber to *one thousand* and then display it. 
- To do this, we want to set the value the same way as we did before. However, we do not want to include the comma because that is **not** an integer and will cause an error. 
- The code to do this is as follows:
    ```java
    myFirstNumber = 1000;
    System.out.print(myFirstNumber);
    ``` 
- This presents the value as it should be. 
- Note, if we included the comma `myFirstNumber = 1,000;` we will get the following error:
    ```java
    Error:
    ';' expected 
    myFirstNumber = 1,000;
    ```
- This is because the colon was an attempt to change the data style. 

### Using Lists to display changes in the JShell session.
If we wanted to be able to check all code executions we have performed in a given session, we can use the JShell command `/list`. 
- Typing `/list` will generate a list of all commands and code we have executed this time. 
- An important item to note is that if we had used the up arrow to return to our first integer command, or had typed the full command `int myFirstNumber = 1000;` we would get the same results in `/list`. 
    - However, if you do this, you are actually re-declaring the variable, striking all previous actions. 
    - The JShell program will let you do this, but a standard program created in an IDE will not. 
    - You can certainly change the variable as you would like, but if you try to re-delcare the variable, it will throw an error. 

### Using Complex Variables
In the previous examples, we have only used a single variable value after the equal sign. This will work but would make programming much more complicated and require lots of variable declarations and changes.

- You can do a math operation as part of a varaiable if you would like. 
- An example of this would be:
    ```java
    myFirstNumber = 10 + 5;
    System.out.print(myFirstNumber);
    ```

    - This will produce a value of *15* because Java added these values together.
- If you want to make this more complicated, you can do something like this:
    ```java
    myFirstNumber = (10 + 5) + (2 * 10);
    System.out.print(myFirstNumber);
    ```

    - This should give you a total of *35* because we added 10 and 5 to get 15, we then multiplied 2 by 10 to get 20, and finally added both values together (15 + 20 = 35).

### Operators
Operators are an example of what we did in the complex variable activity above. You will use operators throughout your time coding in Java (or any language, really). The most common operators are simple mathematical ones but you will use much more in the future. 
- Some common operators include:
    - Addition
    - Subtraction
    - Division
    - Multiplication
- These can be used with numbers to do most common math. 

[Back to Top](#table-of-contents)

---

## Chapter 17 - Comprehensive Introduction Guide to Using Variables in Java Expressions
In this chapter, we will take the basics we learned in Java Expressions and do a lot more with them. 

- Remember that an *expression* is **the code segment that is on the right side of the equals sign in an assignment or declaration statement**

### Challenge
In this challenge, the instructor wants us to create two new variables. 
- Create a new variable called *mySecondNumber*, make it an *int* type, and set it to *12*
- Create another new variable called *myThirdNumber*, make it an *int* type, and set it to 6. 
- The code to do this is as follows:
    ```java
    int mySecondNumber = 12;
    int myThirdNumber = 6;
    ```
- At any time, we can confirm all variables we have currently declared using `/var`
- If we would like to declare a new variable to store the total of all of the values we have established, here is how to do that:
    ```java
    int myTotal = myFirstNumber + mySecondNumber + myThirdNumber;
    ```
    - If desired, we could continue adding values together for as long as we want. 
    - This equates to: 35 + 12 + 6 which is 53. 
- We now want to change the value of myThirdNumber to the value of myFirstNubmer * 2. 
    - The code for this is:
        ```java
        myThirdNumber = myFirstNumber * 2; 
        ```
    - This will set the value of myThirdNumber to be 70 (35 * 2). 
    - To confirm that this code worked, we want to retype the code we used to add the numbers together. 
    ```java
    myTotal = myFirstNumber + mySecondNumber + myThirdNumber;
    ```
    - now, the value should be 35 + 12 + 70 which equals 117. 

### Challenge
In this challenge, the instructor wants us to do a few steps to show our knowledge of operators. 
- Created a new variable called *myLastOne*
- Make sure it is set to a data type of *int*
- It's value should be set to the value of **1000** *minus* the value of **myTotal**
- Finally, print out the value on the screen. 

- The code for this challenge is as follows:
    ```java
    int myLastOne = 1000 - myTotal;
    System.out.print(myLastOne);
    ```
    - This should result in a value of 883 since 1000 - 117 (the value of myTotal) = 883. 

- In order to explain a potential error, the instructor showed us what happens if we accidentally mistyped the variable name. 
    - In this case, let's say we accidentally typed `System.out.print(MyLastOne);` (note the capitalized My instead of my). 
    - This would generate the following error:
        ```java
        Error:
        cannot find symbol
            symbol: variable MyLastOne
        System.out.print(MyLastOne);
        ```

#### Important note about Java and Syntax
Java is **case-sensitive** meaning that it expects words to be in the correct format. This includes not only *keywords* and *language syntax* but variable names and data types as well.

- In this example, **MyLastOne** is considered a completely different variable than **myLastOne** only because of the capital M. 
- Furthermore, **int**, **Int**, and **INT** are all considered *different values*
- Keywords need to be in *lowercase* 
- Variables will always be exactly as you declare them, *including capitalization*

[Back to Top](#table-of-contents)

---

## Chapter 18 - Exploring Integer Ranges and Wrapper Classes
In this chapter, we will be looking at some additional data types besides *int*. It's important to remember that these basic types are also referred to as *primitive data types* to differentiate them from more complex, code-generated data types we could build. 

There are eight primitive data types in Java:

| Whole Numbers | Real Numbers (Floating Point or Decimal) |
| :-----------: | :---------------------------------------:|
| byte          | float                                    |
| short         | double                                   |
| int           |                                          |
| long          |                                          |
|---------------| -----------------------------------------|
| Single Character | Boolean Value                        |
| ------------------| -------------------------------------|
| char              | boolean                              |

### What Data Can We Store in an Integer?
- There is a specified range of values allowed for the *int* data type
- The allowable range of values is **not infinite**
- There is a defined minimum and maximum value for an integer 
- To determine what we can store in an integer, we can use the following code:
    ```java
    int myMinIntValue = Integer.MIN_VALUE;
    myMinIntValue ==> -2147483648
    ```
    - What this tells us is that the *lowest* value we can store in an integer is the value of *-2147483648* 
    - My using the *Integer.MIN_VALUE* we are revealing that Integer is a **wrappper class** which means that Java already has some specific and pre-determined attributes that it can use with this data type. 
- Another wrapper item we can determine about integer is the Max Value. This can be determined like this:
    ```java
    int myMaxIntValue = Integer.MAX_VALUE;
    myMaxIntValue ==> 2147483648
    ```
    - Much like the Min Value, another integer attribute is the max value so we cannot assign a value of any higher than this to an integer. 
- Now we want to print the full range of the Integer value but we're giong to use a compound statement. 
- We can achieve presenting multiple values to a single screen by concatenation of values. An example of this is as follows:
    ```java
    System.out.print("Integer Minimum Value = " + myMinIntValue);
    ```
    - The use of the plus sign (+) in the system.out.print command allows different types of data on the same line as a single line of text. 
    - In the example above, we created a label called "Integer Minimum Value" and set it to display the myMinIntValue data. 
- If we do not want to create a variable just to store this value, we can ask Java to print the wrapper text using this code:
    ```java
    System.out.print("Integer Minimum Value = " + Integer.MIN_VALUE);
    ```
    - This will produce the same exact value as we saw before but it won't require us to burn a variable just for this value. 
- To display the integer range in a single line, we scan use the following command:
    ```java
    System.out.print("Integer Value Range (" + Integer.MIN_VALUE + " to " + Integer.MAX_VALUE + ")");
    ```
    - We don't have to put this all on one line if we don't want to. We can use the multi-line code entry by doing this:
        ```java
        System.out.print(
            "Integer Value Range ("
            +
            Integer.MIN_VALUE
            +
            " to "
            +
            Integer.MAX_VALUE
            +
            ")"
        );
        ```
    - The resulting values are the same, but it allows us to more readily see each piece of the code. 
### Classes
A class is a building block for Object-Oriented programming, and allows us to build custom data types. By itself, a class is an object that is a collection of attributes. You can interact directly with the entire class object or you can interact with just a single or set of attributes of the class. 

### Wrapper Classes
Java establishes a *wrapper class* for all of its eight primitive data types. 
- Wrappers can provide simple operations and basic information about the primitive data type. But the information cannot be stored on the primitive itself.
- In the previous example, we interacted with the MIN_VALUE and MAX_VALUE of the Integer Wrapper. 
- Wrapper Types and their Classes:
    | Primitive | Wrapper Class |
    |-----|-----|
    | byte | Byte |
    | short | Short |
    | char | Character |
    | int | Integer |
    | long | Long |
    | float | Float |
    | double | Double |
    | boolean | Boolean |

### Maxing Out the Integer
If we attempted to make the MAX Value of the Integer go higher than the maximum value it can accept, you will cause the integer value to reset. 
- An example of what this looks like is here:
    ```java
    System.out.print("Busted Max Value = " + (myMaxIntValue + 1));
    ```
    - We attempted to add one more number to the maximum value of an integer and the result is `-2147483648`
    - This is called an *overflow* because the integer cannot accept the value but tries to anyway and it hit its upper limit. 
- The same process will also work if we attempted to do the same thing with the minimum value:
    ```java
    System.out.print("Busted Min Value = " + (myMinIntValue -1));
    ```
    - We attempted to subtract one number from the minimum value of an integer and the result is `2147483647` because we hit an *underflow* this time. 

### Overflow and Underflow in Java
- If we force a value higher than the maximum value for an integer, we will trigger an *overflow*
- If we force a value lower that the minimum value for an integer, we will trigger an *underflow* 
- This concept is also called an *integer wraparound* and is dangerous because Java will simply flip around to the polar end of the value and keep processing without an error.
- This could cause serious issues when counting large numbers or dealing with exteremely small numbers. 

### Assigning Numeric Literals to an Integer 
- Another problem we may encounter is if we try to force an integer to take a number bigger than it can accept when we declare the variable. The code may look like this:
    ```java
    System.out.print("Integer Maximum Value = " + Integer.MAX_VALUE);
    Integer Maximum Value = 2147483647
    int myMaxIntTest = 2147483648;
    ```
    - This will produce the following error because we have attempted to force a value that is beyond Int's capacity:
        ```java
        Error:
        integer number too large
        int myMaxInTest = 2147483648;
        ```
- An integer wraparound (overflow or underflow) can occur in Java when you are using expressions that are not a simple literal value.
- The Java compiler does not attempt to evaluate the expression to determine its value, so it DOES NOT give you an error. 
- Here are some other examples that will create an overflow without checking for the condition:
    ```java
    int willThisCompile = (Integer.MAX_VALUE + 1);
    int willThisCompile = (2147483647 + 1);
    ```
- However, if you were to try `int willThisCompile = 2147483648;` it will throw an error. 

### Underscores and Numeric Literals
- In Java you cannot put commas in a numeric literal. So something like this will not work: `int myMaxIntTest = 2,147,483,647;`. 
- However, if you would like to break this down you can use the underscore like this: `int myMaxIntTest = 2_147_483_647;`
- We can use the underscore any time we might have previously used a comma, but it **cannot** be used at the begining of a number. 

[Back to Top](#table-of-contents)

---

## Chapter 19 - Understanding Byte, Short, and Long Data Types
Each of these data types in Java have a different width. If we are to properly use them, we need to understand more about their role and width. 

### Primitive Data Types in Java
| Whole Number Data Type | Wrapper Class | What's noteworthy |
|--------                |--------       | --------          |
| byte | Byte | Has the smallest range |
| short | Short |   |
| int | Integer | Java's Default Data Type for whole numbers |
| long | Long | Has the largest range |

- Because Byte is a wrapper class like Integer, we can use the same basic code to print its max and minimum values. 
- The code looks like this:
    ```java
    System.out.print("Byte Value Range (" + Byte.MIN_VALUE + " to " + Byte.MAX_VALUE + ")");
    ```
    - This should output the values `Byte Value Range (-128 to 127)`

- Given the small size of the byte, it is rare to use it for most practical programs but it may have uses for handling small data sets and save on memory. 
- It may also be a good way to ensure that your program will not accept anything larger than the range so users do not attempt to put anything larger in the value. 

- Short is another data type that is only used for a few unique situations. 
- We can review it's size with the following code:
    ```java
    System.out.print("Short Value Range (" + Short.MIN_VALUE + " to " + Short.MAX_VALUE + ")");
    ```
    - The resulting code should look like this: `Short Value Range (-32768 to 32767)`

- **NOTE** The *byte* and *short* data types have the same overflow problem found in the *int* data type so if the values inserted into them are outside of their range, they will cause overflow or underflow. 

### Size and Width of Primitive Data Types

| Data Type | Width (in bits) | Min Value | Max Value |
|------     | ------          | ------    | ------    |
| byte | 8 | -128 | 127 |
| short | 16 | -32768 | 37267 |
| int | 32 | -2147483648 | 2147483648 |

- The *Long* data type is the largest of the primitive data types in Java
- Long is used when you must deal with extremely large datasets that require extra space. 
- We can create an example of a long data type by using the following code: 
    ```java
    long myLongValue = 100L;
    ```
    - It is typically a Java best practice to include the letter *L* at the end of a Long Number. This tells Java (and the programmer) that this is a Long, even if it doesn't use all that space initially. 
    - We can check how long the Long value can be by using the *SIZE* operator with the *Long* wrapper. 
    - The code looks like this: `("A Long has a width of " + Long.Size);`
    - This should output: `A Long has a width of 64.`
- This is **TWICE** the size of an Int data type and equates to something like 2^63.
- We can use the same code we used for the others to determine the range on this data type:
    ```java
    System.out.print("Long Value Range (" + Long.MIN_VALUE + " to " + Long.MAX_VALUE + ")");
    ```
    - This will output the following range: `Long Value Range (-9223372036854775808 to 9223372036854775807)`
- Without including the *L* on the number, even if we designate it as a *long*, the variable will default to an *integer*. 
- An example of this code:
    ```java
    long bigLongLiteralValue = 2_147_483_647;
    bigLongLiteralValue ==> 2147483647
    ```
    - This instance will work properly. But if we try to change the value without using the *L* then Java will default to *int* as seen here:
    ```java
    long bigLongLiteralValue = 2_147_483_647_234;
    Error:
    integer number too large
    ``` 
    - However, if you add the expected *L* on the end `long bigLongLiteralValue = 2_147_483_647_234L;` then you will not get an error. 

[Back to Top](#table-of-contents)

---

## Chapter 20 - Understanding Casting with Numeric Primitives Types in Java
We will use the option for casting specific types of numbers as other values in Java in this section. 

- One thing we have not done yet is to declare and initialize a variable on the same line in Java. This is perfeclty acceptable and used commonly. 
`short myMinShortValue = Short.MIN_VALUE; int myMinIntValue = Integer.MIN_VALUE;`
    - In this example, we are using a single line to create multiple variables and also establishing the default values. 
- It is also possible to declare multiple variables of the same kind in a single line of code:
    `byte myMinByteValue = Byte.MIN_VALUE, myMaxByteValue = Byte.MAX_VALUE;`
    - This will create two of the *byte* variable types with their values already set. 

### Rules for Declaring Multiple Variables in one statement
- You cannot declare variables with different data types in a single statement (i.e. byte and int)
    - This code shows you an example of how Java will react to this:
    ```java
    short firstShort = 1, int firstInteger = 2;

    Error:
    <identifer> expected
    ```
    - If you were to replace the , with a semicolon, the code would actually work as expected: `short firstShort = 1; int firstInteger =2;`

- If you declare multiple data variables of the same data type, you must specify the data type *only once* before any variable names. 
    - This code shows you an example of Java will react to this: 
    ```java
    byte firstByte = 1, byte secondByte = 2;

    Error:
    <identifier> expected
    ```
    - You can fix this in one of two ways:
    `byte firstByte = 1; byte secondByte = 2` (using a semicolon)
    OR
    `byte firstByte = 1, secondByte = 2;` (using a comma and removing the second *byte*) 

### Simple Math with Java
- Here is an example of a simple division problem in Java: `int myTotal = (myMinIntValue /2);`
    - This creates a variable called *myTotal*
    - Takes the value of *myMinIntValue* (remember that is -2147483648) and divides it by two
    - Assigns the new value (-1073741824) to the *myTotal* varaiable. 
    - if we attempted to do this with a *byte* data type, however, it would present an error:
    ```java
    byte myNewByteValue = (myMinByteValue /2);

    Error:
    incompatible data types: possible lossy conversation from int to byte.
    ```
- In a situation where we feed Java a literal value for a variable, it is smart enough to know whether or not the result will fit in the prescribed variable. 
- On the other hand, if we attempt to send a value using a variable (like myMinByteValue) Java has not seen what is inside the variable to realize that it won't work, hence it will throw an error. 

### Casting in Java
No, not like what a wizard does...

**Casting** means to treat or convert a number, from one type to another. We put the type we want the number to be in parenthesis like this:
    `byte myNewByteValue = (byte) (myMinByteValue / 2);`

- This will establish the value to be *-64* which will easily fit in a byte data type. 

- This will work with other data types as well including short:
    `short myNewShortValue = (short) (myMinShortValue /2);`

[Back to Top](#table-of-contents)

---

## Chapter 21 - Primitive Types Challenge: Applying Your Knowledge
This chapter is focused on doing some challenges with various data types to test our skills. 

### Challenge Items:
- Create a *byte* variable and set it to a valid byte value.
    - I created *myChallengeByte* and set it to 61
- Create a *short* variable and set it to a valid short value.
    - I created *myShortByte* and set it to 10201
- Create an *int* variable and set it to a valid int value. 
    - I created *myChallengeInt* and set it to 867005309.
- Create a *long* variable and:
    - Make it equal to 50,000 *plus* **10 times** the sum of your byte, short, and int values.
    - Use the variable names to calculate the same. 

### Challenge Code
I tried a lot of different ways to make this work but the code I ultimately chose was as follows:
   ```java
    byte myByteChallenge = 61;
    short myShortChallengeShort = 10201;
    int myIntChallenge = 867005309;

  long myChallengeP1 = (myByteChallenge + myShortChallengeShort + myIntChallenge);
  ==> 867015571

  long myChallengeP2 = (10L * myChallengeP1);
  ==> 8670155710

  long myChallengeAnswer = (50_000L * myChallengeP2);
  ==> 433507785500000
   ```
Although this may not be the most effective way to solve this problem, it seemed to provide the desired results. 

### Instructor's Code Answer
The instructor suggested we do it like this:
    
 ```java
    byte byteValue = 10;
    short shortValue = 20;
    int intValue = 50;

    long longTotal = 50000L + 10L * (byteValue + shortValue + intValue);
 ```    
    
Another completely valid example is more similar to the one that I did:

```java
    byte byteValue = 10;
    short shortValue = 20;
    int intValue = 50;

    int sumOfThree = byteValue + shortValue + intValue;
    long LongTotal = 50000L + (10 * sumOfThree);
 ```
### Using Parenthesis

- Parentheses are another way to make your code more readable. 
    `longTotal = 50000L + (10 * sumOfThree);`

- They also make it clear which calculations should be done first. 

### Using a Short (and breaking it)

Another example suggested by the instructor shows a shortcoming of the short value as indidcated by this code:

```java
short shortTotal = (1000 + 10 * (byteValue + shortValue + intValue));
```
This will produce an error of:

```java
Error:
incompatible types: possible lossy conversion from int to short
short shortTotal = (10000 + 10 * (byteValue + shortValue + intValue));
```
We can solve this by forcing a *cast* to the byte value:

```java
    short shortTotal = (short) (1000 + 10 * (byteValue + shortValue + intValue));
    shortTotal ==> 1800
```
### Recap

- We have now worked a lot with bytes, shorts, integers, and longs. 
- Now we need to work on four other data types. 
- In the next section we will focus on dealing with decimals instead of whole numbers. 

[Back to Top](#table-of-contents)

---

## Chapter 22 - Working with Float and Double: Precision in Floating Point Numbers

In this next section, we will work with decimals for some real world use cases. 

Unlike whole numbers, *floating-point* nubmers have *fractional* parts requiring a decimal point. 

### Comparing Whole Nubmers and Floating Point Numbers

| Whole Numbers | Floating Point Numbers |
| ------ | ------- |
| 3 | 3.14159 |
| 10000 | 10.0 |
| -2147483649L | -0.666666666666667|

The purpose of a floating point number in Java is to allow for more precision in calculating complex numbers. 

### Java's Floating Point Number Options

| Java's Data Types for Floating Point Numbers |
| -------- |
| float |
| **double** |
| The double is Java's default number for decimals and real numbers. |

### Single and Double Precision

Precision refers to the format and amount of space occupied by the relevant type. 

| Data Type | Width (in bits) | Min Value | Max Value |
| ------ | ------- | ------- | ------ |
| float | 32 | 1.4E-45 | 3.4028235E38 |
| double | 64 | 4.9E-324 | 1.7976931348623157E308 |

**Note** The *E* numbers are using Java Scientific Notation

### Java Scientific Notation

Scientific notation can be translated into more familiar terms, by replacing *E* in the nubmer with the words *10 times the power of...* 

- 1.4E-45 is the same as 1.4 X 10<sup>-45</sup> and 3.4E38 is the same as 3.4 X 10<sup>38</sup>
- For more clarity, remember that 10-1 = *0.1* and 10-5 = *0.00001*
- The moral of this story is that *double* when compared to *float* can handle both a much smaller and much larger decimal value.

If you wanted to check this function in Java, you could use the following code:
```java
System.out.print("Float Value Range(" + Float.MIN_VALUE + " to " + Float.MAX_VALUE + ")");

Float Value Range(1.4E-45 to 3.4028235E38) 
```
You could also do the same thing with  the *double* value using this code:
```java
System.out.print("Double Value Range(" + Double.MIN_VALUE + " to " + Double.MAX_VALUE +")");

Double Value Range(4.9E-324 to 1.7976931348623157E308)
```
### Workiing with Float and Double
Now let's do some practical application of the float and double values. 

```java
int myIntValue = 5; float myFloatValue = 5; double myDoubleValue = 5;
```
**Note** Much like the *Long* value, you want to suffix *float* and *double* values. 
    - Since *double* is default, you don't have to include the *d* or *D* 
    - For *float*, however, we need to add *f* or *F* to establish a *Float*
    - When interacting with literal constants, it is good practice to assign the *F* and *D* suffixes

A better example of the code from earlier is as follows:

```java
myFloatValue = 5f;
myDoubleValue = 5d;
```
It is possible to create an issue if you do not specify the *f* and *d* when working with decimals:

```java
float myOtherFloatValue = 5.25;

Error:
incompatible types: possible lossy conversion from double to float
float myOtherFloatValue = 5.25;
```
### Challenge - Fix the Float with casting

We know we can use the *f* to force a float and remove the error above. But what about using casting? 

Create a solution that removes the error above **without** using the *f* function. 

This was my solution:

```java
float myOtherFloatValue = (float) (5.25);

myOtherFloatValue ==> 5.25
```

This solution appears to work!

### Good Coding Practice Note
It is generally a good coding practice to **NOT** use the *float* vaue unless it is absolutely necessary. 

There are a few reasons for this:
- *double* is a more precise type than *float*
- Code readability is much easier when using `float myOtherFloatValue = 5.25f;` because it's less code to review.

In Oracle Certification exams, they like to use the `float myOtherFloatValue = 5.25;` on questions requiring code review. So if you know to look for the requisite *f* it 
will basically be a free question. 

[Back to Top](#table-of-contents)

--- 

## Chapter 23 - Understanding Floating-Point Precision: A Practical Challenge in Java
There are a few different ways to present literal decimal values when typing them directly into Java such as:

| Literal Value | Default Output |
| ------ | ------|
| 5 | 5.0 |
| 5.000000 | 5.0 |
| 5f | 5.0 |
| 5d | 5.0 |
| 5e1 | 50.0 |
| 5_000_000.0 | 5000000.0 |
| 50_000_000.0 | 5.0E7 |

### Simple Division

Let's try some simple division to illustrate the use of Float. If we try the basic code to divide 5 by 2 but don't include the f, we will get an integer value:

```java
myIntValue = 5/2;
myIntValue ==> 2
```

However, we know that this is not precise. This is because Java saw two integers and assumed we wanted to get an integer value. If we force the *float*, we can get a more precise answer:

```java
myFloatValue = 5f / 2f;
myFloatValue ==> 2.5
```
We can do something similar with *double*

```java
myDoubleValue = 5d / 2d;
myDoubleValue ==> 2.5
```
Now, let's try a bit more complex division operation. 

```java
myIntValue = 5 / 3;
myIntValue ==> 1
```

Notice that this is a whole value which does not accurately represent the value. So, let's go with the more precise *float* value. 

```java
myFloatValue = 5f / 3f;
myFloatValue ==> 1.6666666
```

This data represents a number with a default limit of 7 decimal places. However, if we do the exact same code but with *double* we get a more precise number:

```java
myDoubleValue = 5d / 3d;
myDoubleValue ==> 1.6666666666666667
```

This number is clearly more precise than the *float* variant.

We can type decimals correctly into the values to negate the need to include the *d*. 

```java
myDoubleValue = 5.00 / 3.00;
myDoubleValue = 1.6666666666666667.
```

Because we incuded the trailing decimals, Java automatically assigned the correct double value type. 

### Mixing operands

The *operand* is a term used to describe the number on either side of a mathematical statement. In the example above, `myDoubleValue = 5.00 / 3.00` the values of *5.00* and *3.00* are **operands**. 

What if wenated to mix values to include a double and an integer? 

```java
myDoubleValue = 5.00 / 3;
myDoubleValue ==> 1.6666666666666667
```
The result is the same because *ONE* of the *operands* includes a decimal (5.00). Java sees that at least one operand uses decimals and automatically displays the *double* value. 

However, this will *NOT* work when using floats:

```java
myFloatValue = 5.00 / 3f;

Error:
incompatible types: possible lossy conversion from double to float
myFloatValue = 5.00 / 3f;
```
This failed because Java has already established a *double* variable and you cannot force a *float* value into a *double* data store. 

### Why Choose Double?
- It is actually faster processing on modern computers
- Many Java Libraries that will be used later in the course, especially math operations are often written to process doubles by default. 
- Java creators selected *Double* because it is more precise than *Float* and can handle larger numbers. 
- Decades ago, lack of memory in computers was a problem but with most modern computers, this is no longer the case. 

### Coding Challenge - Convert Pounds to Kilograms

Steps:
1. Create a variable with the appropriate type to store the number of Pounds we want to convert to Kilograms 
2. Calculate Kilograms, using the variable above, and store the result in a second appropriately typed variable. 
3. Use the following conversion: `1 pound is equal to 0.45359327 kilograms`

My code:
```java
double poundValue = 210;
double kiloValue = 0.45359327;
double convertedAmount;

convertedAmount = poundValue * kiloValue

System.out.print(convertedAmount);
```
This solution appears to have worked!

The instructor's solution is as follows:
```java
double numberOfPounds = 200d;
double convertedKilograms = numberOfPounds * 0.45359327d;
System.out.print("Converted kilograms = " + convertedKilograms);

convertedKilograms ==> 90.718474
```
### Underscores in Doubles and Floats
You can also include underscores in code with decimals to make the numbers clearer. 

For example:
```java
double pi = 3.1415927d;
pi ==> 3.1415927

double anotherNumber = 3_000_000.4_567_890d;
anotherNumber ==> 3000000.456789
```
In this example, the numbers input with underscores formatted exactly as they should without the underscores. Additionally, the *0* at the end did not populate because it was not necessarry. 

### Floating Point Number Precision Tips
- Float and double are great for general floating point operations. 
- **Neither** should be used when precise calculations are required because of how floating point nubmers are stored, this is not native to Java. 
- To deal with this absurdly large numbers, Java has a class called *BigDecimal* that is more precise. 

[Back to Top](#table-of-contents)

---

## Chapter 24 - Exploring Character (Char) and Boolean Primitive Data Types
