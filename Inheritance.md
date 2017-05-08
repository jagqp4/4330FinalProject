# Java
#### Java allows subclasses to inherit from a single base class by using the "extends" keyword. Inheritance is a way to give new classes all the non private methods and fields of another class without having to redefine them.
```java
class Dog extends Pet {

}
```
#### Interfaces can alse use inheritance but Java lets you use extend multiple base interfaces.
```java
interface OwnedPet extends BoughtPet, LicensedPet, MouseListener {

}
```
# C#
#### C# does away with the long winded 'extends' keyword in favor of a colon to express inheritance. Just like Java, C# doesn't allow multiple inheritance on classes but does allow it on interfaces.
```c#
class Car : Vehicle
```
#### When you want a class to extend a superclass and implement multilpe interfaces the class must come first followed by the interfaces. To avoid the appearance that we are inheriting from multiple classes we put an I before interfaces by convention.
```c#
class Car : Vehicle, IDriveable, ICrashable
```
