# Section 2 Material
This is the notes from Section 2 in the course. 

## Chapter 14
- Installed JDK 17 LTS
- Confirmed our Java Version via command prompt
    - `java -version`
- Experimented with our first program (HelloWorld.java) 
- Talked about JShell

### JShell
The instructor explanes the values of the Java Shell (JShell) tool for executing java code. 

- JShell became standard in JDK 9
- It is a *Read-Eval-Print-Loop* (REPL) tool which completes the following steps:
    - it **reads** the command or code we type in.
    - it **evaluates** and executes the code and often allows shortcuts to be used. 
    - it **prints** out the results of the evaluation or execution without making us write out the code. 
    - Lastly, it loops back out to serve as a sandbox. 
- JShell is **not** a replacement for an IDE. 
- [JShell-Docs](https://docs,oracle.com/en/java/javase/17/jshell/introduction-jshell.html)

### Navigating in JShell
- We use the `jshell` command to launch the JavaShell
- We used the `/help intro` command to review the introduction
- We used the `/list -all` to see a list of modules that were currently active. 
- We used the `/list -start` to see what modules are automatically started when JShell opens but this list is the same at the moment. 
- We discussed the use of the curly brace **{** to allow us to include multiple lines of code. JShell will not execute anything until we close the curly brace with what we typed. 
- We can also use the break command `ctrl +c` to force the curly brace to end if we want. 
- We exit JShell by typing `exit`

This concludes Section 02. We are now moving to Section 03, starting with Chapter 15. 