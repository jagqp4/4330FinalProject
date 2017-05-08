# Java
#### There are many different ways to create a singleton in Java but some offer more abilities than others. The example I chose is considered 'thread safe' which means all threads operating on the instance will be using the same version and will not be able to desynchronize. This technique comes from computer sccience researcher Bill Pugh and is considered the best way to implement singletons in Java. He takes advantage of internal java mechanisms which guarantee that the inner class is referenced only when the getInstance() method is called and not before. This is referred to as lazy instantiation because the inner class ins't created until the first time it's needed.
```java
public class Singleton {
    private Singleton() {}

    private static class SingletonHolder {
        private static final Singleton INSTANCE = new Singleton();
    }

    public static Singleton getInstance() {
        return SingletonHolder.INSTANCE;
    }
}
```
# C#
#### Like java, there are multiple ways to create singletons in C# and some have more bells and whistles than others. In my example I chose a design pattern which is thread safe and lazy. The singleton instance is not created until the first reference to the static field of the 'Nested' class. Note the constructor of the inner class is static which guarantees the lazy instantiation. An internal flag called 'beforefieldinit' is not set and this tells the C# compiler to wait to initialize the object.
```c#
public sealed class Singleton
{
    private Singleton()
    {
    }

    public static Singleton Instance { get { return Nested.instance; } }
        
    private class Nested
    {
        // Explicit static constructor to tell C# compiler
        // not to mark type as beforefieldinit
        static Nested()
        {
        }

        internal static readonly Singleton instance = new Singleton();
    }
}
```
