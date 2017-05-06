# Java
#### In Java namespaces are refereed to as packages and they are used to group similar classes, interfaces, and sub-packages. Packages can be mapped to a file system. These packages can be stored in compressed JAR files which allows them to be downloaded much faster. Packages also serve to help the programmer organize classes into similar categories based on some functionality. 
#### At the top of every java file you must define the package it belongs to as shown below
```java
package petstore;

class Dog {}
```
#### Here are two examples of commonly used Java packages.
##### 1. java.lang
  * The most widely used package which contains the most essential and fundamental classes and interfaces.
  * Just a few of the classes contained in this package are Object, Number, Thread, Throwable, and System.
  * This packgae even contains the "Package" class which basically represents a specific package implementation as an object.
##### 2. java.io
  * As the name suggests, this package contains things relating to input and output functionality
  * Some of the classes it contains are File, Console, Reader, Writer, and InputStream.
#### When you want to use a specific class from another package you do the following
```java
import java.io.BufferedInputStream;
```
# C#
#### The equivalent of a package in C# is a namespace and it operates in a similar way but there are some differences. At the top of your file you declare what namespace to use.
```C#
namespace petstore {
    class a {}
}
```
#### The .NET framework provides C# users with pre defined namespaces just like Java's API Platform. When you want to access stuff from other namespaces you do the following. 
```C#
using System
```
#### Unlike Java, you can use aliases when delaing with namespaces to help avoid confusion. In this example we create two variable names for different classes that happen to both be called "Timer". This variable name can be used later in the program to specify which Timer class we are using. 
```C#
using WinformTimer = System.Windows.Forms.Timer;
using ThreadingTimer = System.Threading.Timer;
```
#### C# even allows you to nest namespaces to help control scope.
```C#
using top_namespace
using top_namespace.inner_namespace

namespace top_namespace {
    class a {}
    
    namespace inner_namespace{
        class b {}
    }
}
```
