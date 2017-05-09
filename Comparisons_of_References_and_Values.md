# Java
#### Comparisons of references and values:
#### How are values compared? (i.e. comparing two strings)
* Comparison: a == b, a != b | Reference Type
* Comparison: a.equals(b) | Value Type
* Comparison: a.compareTo(b) | Value Type
* Comparison: compare(a,b) | Value Type

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
