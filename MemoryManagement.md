# Java Memory Management
#### How is it handled?
* Java stores objects in the a heap structure. The heap structure is divided into two areas: the 'nursery' and the 'old space'. The nursery is used for new objects, but when it becomes too full some of the objects are moved to the old space. The old space simply takes the past parts and parcels from the Nursery and then once the old space is filled up, garbage collection will begin happening there.
#### How does it work?
* Memory is preallocated for future objects, and then garbage collection in the old space frees the memory up.
#### Garbage Collection?
* Yes, java has garbage collection. It is used when areas become full and the nursery uses young collection to collect its garbage.
#### Automatic reference counting?
* No, java does not support this.

# C# Memory Management
#### How is it handled?
Answered below.
#### How does it work?
The memory management life cycle of an object is as follows:
* When the object is created, memory is allocated for it, the constructor is run, and the object is considered live.
* If the object, or any part of it, cannot be accessed by any possible continuation of execution, other than the running of destructors, the object is considered no longer in use, and it becomes eligible for destruction. The C# compiler and the garbage collector may choose to analyze code to determine which references to an object may be used in the future. For instance, if a local variable that is in scope is the only existing reference to an object, but that local variable is never referred to in any possible continuation of execution from the current execution point in the procedure, the garbage collector may (but is not required to) treat the object as no longer in use.
* Once the object is eligible for destruction, at some unspecified later time the destructor (if any) for the object is run. Unless overridden by explicit calls, the destructor for the object is run once only.
* Once the destructor for an object is run, if that object, or any part of it, cannot be accessed by any possible continuation of execution, including the running of destructors, the object is considered inaccessible and the object becomes eligible for collection.
* Finally, at some time after the object becomes eligible for collection, the garbage collector frees the memory associated with that object.
#### Garbage Collection?
* The process of selecting which objects are in use or not is detailed in the memory management life cycle of an object above.
#### Automatic reference counting?
* No, C# does not support ARC.
