# Java
#### In Java we use the 'this' keyword to refer to instances of the class we're in. You can use 'this' by itself to access the entire class as a single object. You can also reference any instance variable by appending a its name at the end of the 'this' keyword.
```java
public class Example {
    private int data;
    private String name;
    
    Example(int data, String name){
        this.data = data
        this.name = name;
    }
}
```
#### When you call the constructor for the Example class it sets the data and name variables to whatever you pass it. Note that both fields in the Example class are private so they can only be referenced from within the class, that's where 'this' comes into play.
# C#
#### Once again we use the 'this' keyword to refer to the current instance of a class. When passed parameters have the same names as fields we use 'this' to refer to the class variables exactly like we did above. 
#### Both languages also allow you to pass an instance of the class as a parameter by using 'this'.
```C#
public class Example {
    int data;
    
    Example(int data){
        this.data = data;
        //pass the freshly created Example object to a function
        doSomething(this);
    }
}
```
