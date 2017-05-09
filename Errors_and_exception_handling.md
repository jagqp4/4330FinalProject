# Java Errors and Exception Handling
#### Reasons for Needing Exceptions:
* A user has entered invalid data.
* A file has been requested but can not be found.
* Network connection has been lost in the middle of processing.
* JVM has run out of memory.

#### Throwing Exceptions:
* The 'throws' statement is used in java to throw an exception wherever it is needed and then caught appropriately thereafter.

#### Example Code:
package com.myjava.exceptions;

public class MyExplicitThrow {
    public static void main(String a[]){
        try{
            MyExplicitThrow met = new MyExplicitThrow();
            System.out.println("length of JUNK is "+met.getStringSize("JUNK"));
            System.out.println("length of WRONG is "+met.getStringSize("WRONG"));
            System.out.println("length of null string is "+met.getStringSize(null));
        } catch (Exception ex){
            System.out.println("Exception message: "+ex.getMessage());
        }
    }

    public int getStringSize(String str) throws Exception{
        if(str == null){
            throw new Exception("String input is null");
        }
        return str.length();
    }
}
- See more at: http://www.java2novice.com/java_exception_handling_examples/throw_clause/#sthash.3X2oLH6M.dpuf

#### Errors:
* Recovering from Error is not possible. The only solution to errors is to terminate the execution. Where as you can recover from Exception by using either try-catch blocks or throwing exception back to caller.
* All errors are unchecked types of exceptions.
* All errors in java are of type java.lang.Error
* Errors are caused by the environment in which the application is running.
* They are not known to the compiler. They mostly happen at run-time.


# C#  Errors and Exception Handling
#### Reasons for Needing Exceptions:
* An exception is a problem that arises during the execution of a program. A C# exception is a response to an exceptional circumstance that arises while a program is running, such as an attempt to divide by zero.

#### C# Exception handling is built upon four keywords:
* Try: A try block identifies a block of code for which particular exceptions is activated. It is followed by one or more catch blocks.
* Catch: A program catches an exception with an exception handler at the place in a program where you want to handle the problem. The catch keyword indicates the catching of an exception.
* Finally: The finally block is used to execute a given set of statements, whether an exception is thrown or not thrown. For example, if you open a file, it must be closed whether an exception is raised or not.
* Throw: A program throws an exception when a problem shows up. This is done using a throw keyword.

#### Code Example:
using System;
namespace ErrorHandlingApplication
{
   class DivNumbers
   {
      int result;
      DivNumbers()
      {
         result = 0;
      }
      public void division(int num1, int num2)
      {
         try
         {
            result = num1 / num2;
         }
         catch (DivideByZeroException e)
         {
            Console.WriteLine("Exception caught: {0}", e);
         }
         finally
         {
            Console.WriteLine("Result: {0}", result);
         }
      }
      static void Main(string[] args)
      {
         DivNumbers d = new DivNumbers();
         d.division(25, 0);
         Console.ReadKey();
      }
   }
}

#### Errors:
* C# uses several different exception class types to deal with different error types:
* System.IO.IOException Handles I/O errors.
* System.IndexOutOfRangeException	Handles errors generated when a method refers to an array index out of range.
* System.ArrayTypeMismatchException	Handles errors generated when type is mismatched with the array type.
* System.NullReferenceException	Handles errors generated from referencing a null object.
* System.DivideByZeroException	Handles errors generated from dividing a dividend with zero.
* System.InvalidCastException	Handles errors generated during typecasting.
* System.OutOfMemoryException	Handles errors generated from insufficient free memory.
* System.StackOverflowException	Handles errors generated from stack overflow.
