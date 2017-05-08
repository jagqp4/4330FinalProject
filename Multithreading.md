# Java
#### In Java there are two ways to create theads. First, you create an object which implements the Runnable interface and pass this object to the Thread constructor. The Runnable interface contains a single method called run which holds the code to be executed by the thread.
```java
public class MyTask implements Runnable {

    public void run() {
        System.out.println("Hello from a thread!");
        //this code is executed while the thread is active
    }

    public static void main(String args[]) {
        (new Thread(new MyTask())).start();
    }

}
```
#### The other way to create threads in java is to define a class which extends Thread and then directly call start() on an instance of your class. The Thread class contains an empty run method so you still need to provide your own implementation of the run method. The other technique is considered better than this one because you are able to implement Runnable and extend from another class also.
```java
public class MyTask extends Thread {

    public void run() {
        System.out.println("Hello from a thread!");
    }

    public static void main(String args[]) {
        (new MyTask()).start();
    }

}
```
# C#
#### To create a thread in C# you create a variable of type Thread and later call the start() method on it. When you create the Thread variable you must pass it a ThreadStart delegate which points to the method that gets executed in the thread. This is basically C#'s version of the run method.
```c#
using System.Threading;

Thread myThread = new Thread(new ThreadStart(DoThisMethod));
myThread.Start();

// somewhere else

public void DoThisMethod(){
    
    //This code is executed by the myThread objcect

}
```
