# Java: At the most general level java has two kinds of data types.
## 1. Primitive Data Types
#### These are also referred to as value types because the variables themselves hold actual values. In java there are 8 value types and it is not possible to create new ones.
  1. byte
  2. short
  3. int
  4. long
  5. float
  6. double
  7. boolean
  8. char
#### Here's how you define a primitve type and use it in a comparison
```java
int data = 7;
if(data == 8){
    System.out.println("My variable equals 8");
}
```
## 2. Objects 
#### These are called reference types becaue the variables hold references or addresses to the object. Everything not listed above is a reference type. Objects from the java.lang.number which sort of parallel the primitive data types are listed below. Notice these begin with a capital letter because they are objects and not value types.
  * Byte 
  * Short
  * Integer
  * Long
  * Float
  * Double
 #### Another thing that differentiates Objects from primitive types is the ability to call methods on them. Here's an example of defining an object and calling a method on it.
 ```java
 Integer dataObject = 7;
 if(dataObject.equals(8)){
     System.out.println("My variable equals 8");
 }
 ```
#C#: Similarly C# has reference types and value types but in addtion there are pointer types
## 1. Value Types
#### Like java, value types can be assigned a value directly. Instead of being hidden behind the scenes, C# value types are derived from the System.ValueType class.
  1. bool
  2. byte
  3. char
  4. decimal
  5. double
  6. float
  7. int
  8. long
  9. sbyte
  10. short
  11. uint
  12. ulong
  13. ushort
#### In C# structs also act as value types and you can create your own struct as shown below
```c#
struct example{
  private int data;
  
  string[] array;
}
```
 ## 2. Reference Type
 #### These behave just like their java counterparts. Listed below are the kewords which are used to declare referencce types.
   1. class
   2. interface
   3. delegate
#### C# also provides these built in reference types
   1. dynamic
   2. object
   3. string
#### Below is an example of a declaring a test class
```C#
class ExampleClass{
    int data;
    
    string[] array;
}
```
## Pointer Types
#### These are very similar to reference types since they hold memory addresses but there is a slight difference. A pointer cannot point to a reference or struct because it is possible for that object reference to be garbage collected. In C# the garbage collector does not notice if an object is being pointed to. You must use keywords like 'unsafe' and 'fixed' when working with pointers to get around this. Here's a simple example of declaring 3 int pointers.
```C#
int* p1, p2, p3;
```
