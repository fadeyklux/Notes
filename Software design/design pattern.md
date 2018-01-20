Design Patterns
==================
## SINGLETON PATTERN
static variable to hold our instance
private constructor
getInstance() method to instantiate the class
```java
    private static Singleton uniqueInstance;
    private Singleton(){} 
    public static Singleton getInstance() {
       if(uniqueInstance == null){
           uniqueInstance = new Singleton();
       }
       return uniqueInstance;
    }
```
the code above is not **thread safe**
```java
    public static synchronized Singleton getInstance()
```
force every thread to wait its turn befor it can enter the method.
no two threads may be in the method at the same time
**but synchronization is expensive**
- use **eager instantiation** instead of **lazy instantiation**
在定义类的一开始就实例化变量
```java
    private static Singleton uniqueInstance = new Singleton();
    private Singleton(){}
    public static Singleton getInstance() {
        return uniqueInstance;
    }
```
- use **volatile** keyword
if there isn't a instance, enter the synchronized block
only synchronize the first time through
------------------
## THE COMMAND PATTERN
encapsulate a request as an object**command object**