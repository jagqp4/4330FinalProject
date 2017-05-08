# Java
#### Comparisons of references and values:
#### How are values compared? (i.e. comparing two strings)
Equality comparison: One way for primitives, Four ways for objects
Comparison	Primitives	Objects
a == b, a != b	Equal values	Compares references, not values. The use of == with object references is generally limited to the following:
Comparing to see if a reference is null.
Comparing two enum values. This works because there is only one object for each enum constant.
You want to know if two references are to the same object
a.equals(b)	N/A	Compares values for equality. Because this method is defined in the Object class, from which all other classes are derived, it's automatically defined for every class. However, it doesn't perform an intelligent comparison for most classes unless the class overrides it. It has been defined in a meaningful way for most Java core classes. If it's not defined for a (user) class, it behaves the same as ==.
It turns out that defining equals() isn't trivial; in fact it's moderately hard to get it right, especially in the case of subclasses. The best treatment of the issues is in Horstmann's Core Java Vol 1. [TODO: Add explanation and example]
a.compareTo(b)	N/A	Comparable interface. Compares values and returns an int which tells if the values compare less than, equal, or greater than. If your class objects have a natural order, implement the Comparable<T> interface and define this method. All Java classes that have a natural ordering implement this (String, Double, BigInteger, ...).
compare(a, b)	N/A	Comparator interface. Compares values of two objects. This is implemented as part of the Comparator<T> interface, and the typical use is to define one or more small utility classes that implement this, to pass to methods such as sort() or for use by sorting data structures such as TreeMap and TreeSet. You might want to create a Comparator object for the following.
Multiple comparisons. To provide several different ways to sort something. For example, you might want to sort a Person class by name, ID, age, height, ... You would define a Comparator for each of these to pass to the sort() method.
System class. To provide comparison methods for classes that you have no control over. For example, you could define a Comparator for Strings that compared them by length.
Strategy pattern. To implement a strategy pattern, which is a situation where you want to represent an algorithm as an object that you can pass as a parameter, save in a data structure, etc.
If your class objects have one natural sorting order, you may not need this.


# C#
#### Comparisons of references and values:
#### How are values compared? (i.e. comparing two strings)
* When comparing strings in C# the two operators which come to mind are string.Equals() and the '=='operator. So the question is, are they interchangeable?
* There are two differences:
Equals is polymorphic (i.e. it can be overridden, and the implementation used will depend on the execution-time type of the target object), whereas the implementation of == used is determined based on the compile-time types of the objects:

#### Example Code:
// Avoid getting confused by interning
object x = new StringBuilder("hello").ToString();
object y = new StringBuilder("hello").ToString();
if (x.Equals(y)) // Yes

// The compiler doesn't know to call ==(string, string) so it generates
// a reference comparision instead
if (x == y) // No

string xs = (string) x;
string ys = (string) y;

// Now *this* will call ==(string, string), comparing values appropriately
if (xs == ys) // Yes

* Now, to highlight the difference between the two--you can not call Equals on null--this code exemplifies it:
#### Example Code:
string x = null;
string y = null;

if (x.Equals(y)) // Bang

if (x == y) // Yes
