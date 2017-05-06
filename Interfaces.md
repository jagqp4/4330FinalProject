# Java
#### Interfaces are a list of methods definitions which a class must implement. The interfaces only contain the function prototype, it is up to the classes to write the body of the code. If a class implements an interface it must contain all those methods listen in the interface or else it will fail to compile. Also keep in mind that all interface methods must be declared public since the classes which implement them may be located in different packages.
```java
public interface OwnedPet 
    public void feed();
    public int getAge();
    
    //Note that this last method doesn't use public since all interfaces methods must be public regardless
    void setName(String name);
}

// somewhere else in your application

public class Pet Implements OwnedPet{
    public void feed(){
        //...function body
    }
    public int getAge(){
        //...function body
    }
    public void setName(String name){
        //..function body
    }
    
}
```
#### Unlike C#, Java allows you to declare variables in interfaces. For this to make sense they are essentially constants and must be declared as follows.
```java
public interface myInterface{
    public static final CONSTANT = 20;
}
```
# C#
#### Interfaces in C# are very similar to Java because they cannot be instantiated and they don't contain the implementation of any methods. Interfaces in C# contain events, indexers, methods, and properties.
```C#
public interface Transactions{
    void deposit(int amount);
    int withdraw(int amount);
}

// somewhere else in your application

public class Bank : Transactions{
    public void deposit(int amount){
        //..function body
    }
    public void withdraw(int amount){
        //..function body
    }
}
```
#### C# interfaces cannot contain constant fields like Java but they can contain properties. Here is an example of a Name property which has a getter and setter.
```C#
public interface OwnedPet{
    string Name
        {
            get;
            set;
        }
}

// somewhere else in program

public class Dog : OwnedPet{
    public string Name{
        get
        {
            return name;
        }
        set
        {
            name = value;
        }
    }
}
```
