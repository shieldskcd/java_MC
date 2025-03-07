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