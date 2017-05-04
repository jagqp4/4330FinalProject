# Java
#### When defining a class you have a choice of using some or all of these 5 things in order from left to right and top to bottom.
1. Modifiers such as public, private, protected, defalut (empty), abstract, final ... etc
2. The class name, with the initial letter capitalized by convention.
3. The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
4. A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
5. The class body, surrounded by braces, {}.
#### Code example
```java
public final class JavaClass extends SuperClassName implements InterfaceName {
    //fields go here
    String name;
    
    //constructors and other methods go below
}
```
#### Constructors are used when you want to initialize an instance of a class. A class can contain multiple constructors wihch are differentiate by the parameters they take in. This example class has a no argument constructor which uses a default value to set it's name. It also has a constructor where the name is set to the specific string passed to it.  
```java
    //fields go here
    JavaClass(){
       this.name = "Empty";
    }
    JavaClass(String word){
       this.name = word;
    }
    //other methods go below
```
#### When you want to create an instance of a class you must use the new keyword and then proceed to call the constructor with the correct parameters.
```java
JavaClass myInstance = new JavaClass("Jordan");
```
# C#
#### Declaring classes in C# is very similar to Java so I will only focus on their differences. For starters C# drops the verbose "extends" and "implements" syntax in favor of a single colon. Like Java you can only inherit from one base class so that must go first in the list, followed by any number of interfaces. In this example we create a hypothetical Cat class which extends from the more general Pet class and implements the OwnedPet interface.
```C#
class Cat : Pet, OwnedPet {
    
}
```
#### Destructos get called whenever an object is no longer used and it gets garbage collected. Java doesn't have the ability to write destructors on classes.
```C#
~Cat() 
{
    Console.WriteLine("Cat object has been destroyed");
}
```
