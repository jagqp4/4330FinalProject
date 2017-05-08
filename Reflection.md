# Java
#### What reflection abilities are supported?
* Finding out a classes' methods
* Invoking a method by name
* Finding information about constructors
* Finding information about class fields
* Changing a fields' values
* Array manipulation

Code example:
036
            // get all methods of the class including declared methods of
037
            // superclasses
038
            // in that case, superclass of RentCar is the class java.lang.Object
039
            Method[] allmethods = rental.getMethods();
040
            System.out.println("Methods are: " + Arrays.toString(allmethods));
041
            for (Method method : allmethods) {
042
                System.out.println("method = " + method.getName());
043
            }
#### How is reflection used?
Reflection is used in Java to examine an executing program and manipulate the internal properties of the program.

# C#
#### What reflection abilities are supported?
* Dynamically Create an instance of a type
* Bind the type to an existing object
* Get the type from an existing object and...
* ... invoke its methods.
* ... or access its fields and properties 
* Also, if you are using attributes in your code, reflection enables you to access them

Code example:
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
#### How is reflection used?
Reflection is useful in the following ways in C#:
* When you have to access attributes in your program's metadata.
* For examining and instantiating types in an assembly.
* For building new types at runtime.
* For performing late-binding, accessing methods on types created at runtime.
