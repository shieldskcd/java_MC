# Section 3
This section is our first look at actually doing code in Java. We will be working with JShell first and then move into an IDE. 

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

## Chapter 17 - Comprehensive Introduction Guide to Using Variables in Java Expressions
In this chapter, we will take the basics we learned in Java Expressions and do a lot more with them. 