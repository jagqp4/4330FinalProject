# Java
#### Java lacks the ability to create properties and leaves it up to the programmer to write their own getter and setter methods. 
```java
public class Person {
    private String name;
    
    public String getName(){
        return this.name;
    }
    
    public void setName(String name){
        this.name = name;
    }
}
```
# C#
#### In C# you can assign getter and setter abilities to the variable itself. By using the 'get' and 'set' keywords you can make your variables read only, write only, or read-write. Notice that the property name is capitalized at the top where you define it. Also 'value' is used as a placeholder to refer to the variable passed to the accessor.
```C#
public class Person {
    //constructor
    
    public String Name{
        get {return name;}
        set {name = value;}
    }
}
```
#### Starting with C# 7 getters and setters can be implemented as expressions instead of code blocks by using the '=>' operator as follows. The end result is the same.
```C#
public class Person{
    //constructor
    
    public String Name{
        get => name;
        set => name = value;
    }
}
```
#### Property accessors can also be implemented as single line statements which either assign or return something. In this example we create a read only name property.
```C#
public class Person {
    String firstname;
    String lastname;
    
    Person(String first, String last) {
        this.firstname = first;
        this.lastname = last;
    }
    
    public String Name => $"{firstName} {lastName}";
}
```
