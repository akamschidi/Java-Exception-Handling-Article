# Introduction

When you run a Java code or program, it will either compile and execute or throw an error. When a code throws an, it’s a result of either an error or an exception.

An error is more critical. It occurs outside the scope of the code but within the environment in which the application is running. The program is not expected to catch and handle an error.

Some examples of errors are

* OutOfMemoryError
* VirtualMachineError
* StackOverFlowError

Exceptions occur within the scope of the code. It is also known as execution error which means that it occurs during the execution of the code. The programmer is expected to catch and handle exceptions in a program.

This post will focus more on exceptions and runtime errors specifically. You will learn all about exceptions and how to handle exception errors in your Java program.

## Types of Execution Errors In Java
There are three types of execution errors in Java. Here is a breakdown of each of them

### . Compile-Time Error
This type of error is known as compilation error or checked error. A Java program throws this code during the compilation stage. 

In other words, this error occurs when the Javac code is being compiled to bytecode. The compile-time error is usually caused by an error in the code syntax.

For instance, when the programmer fails to add a semicolon at the end of a statement or fails to initialize a variable before printing. 

```

public class JavaExceptionCodes {
    public static void main (String []args){
        int y = 10      //no semicolon
        System.out.println(y);
    }

}
```
### . Run-Time Error
The run-time error is also known as the exception error or unchecked error. It occurs as the program is being executed. The code will compile but will throw an error during runtime.

The runtime error can be further classified into built-in exceptions or user-defined exceptions. Examples of built-in exceptions include:

* ArrayIndexOutOfBoundsException
* ArithmeticException
* FileNotFoundException
* NullPointerException

For instance if a user inputs an int instead of a string or inserts values bigger than the size of an array.

```
public class JavaExceptionCodes {
    public static void main (String []args) {
        int nombas[] = {1, 2, 3, 4, 5};
        System.out.println(nombas[6]); 
        
    }
}
//ArrayIndexOutOfBoundsException
```

### . Logical Error
Also known as semantic error, it occurs if there is an error in a program’s logical output. For instance, 3 + 3 shows an output of 7, or when you log into your account and land on another profile.

The compile-time error is the easiest to catch because your IDE will always point out this error to the programmer. Logical error most times is the hardest error to see because the code will throw no compile time or runtime error.

## Concept of Exception Handling
Exception handling is used to catch errors in a program and maintain the normal flow of the execution of a program. Usually, once a program throws an error, the code will stop executing.

Catching and handling errors beforehand will enable the program to skip the block of code with errors and continue executing the rest of the program.

## Exception Handling Methods:
**Try – Catch – Finally – Throw – Throws** are the list of methods for exception handling in Java. Let’s break each of them in detail with examples:

### . Try
Try is used to enclose a line or blocks of code that may throw an exception. There is also a nested try which is a try with an inner try block (s). They serve the same purpose.

**Syntax**
```
try{

}
```

### . Catch
The catch is a block of code used to catch errors thrown in the try block.

**Syntax**
```
try{

}
catch (Exception e){

}
```
**multiple catch blocks**
```
public class JavaExceptionCodes {
    public static void main (String []args) {
        int x = 10;
        int y = 0;
        int z ;
        int nombas [] = {5, 6, 7, 8, 9};
        try {
            System.out.println(z = x / y);
            System.out.println(nombas[6]);
        }
        catch (ArithmeticException e){
            System.out.println("Can't divide by 0. Choose another number" + e);
        }
        catch(ArrayIndexOutOfBoundsException e){
            System.out.println("Array Out Of Bound" + e);
        }
        System.out.println("End");
    }
}
```
### . Finally
Finally, is an optional block of code, that is usually placed after the try and catch code blocks. It is used to execute important codes. The finally block is always executed whether the program throws an error or not.

**Syntax**
```
try{

}
catch (Exception e){

}
finally{

}
```
### . Throw
Throw is a keyword used to throw an exception inside a method or block of code.

**Syntax**

```

public class JavaExceptionCodes {
    public static void main (String []args) {

           try { throw new ArithmeticException("Try Run");
           }
           catch (ArithmeticException e){
               System.out.println("Catch Exception Error");
           }

    }
}
```
### . Throws
Unlike the throw keyword, the throws keyword is not used to throw an exception. However, it specifies that there may be an exception in the method. The Throws is used in the method signature and not inside the method.

## Best Practices For Handling Exceptions

1. A try block can have several statements (lines of code). It is best to create multiple catch blocks to catch the error in each statement.

2. Always specify the type of exception if you are working with multiple catch blocks.

3.  If there are multiple statements in a try block and you don’t know the statement with the error, create a final general exception at the end of other exceptions to catch unknown errors.

4. Always place the general exception catch block at the end of the other custom exception catch blocks. 

