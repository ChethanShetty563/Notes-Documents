### 1.) Explain OOPS concepts in Java?

In Java, the term "OOPs" (Object-Oriented Programming System) refers to the concept of using objects to model real-world entities and their interactions. OOPs includes several key concepts such as inheritance, polymorphism, encapsulation, and abstraction.

1.  **Inheritance**: It is the mechanism of acquiring the properties and methods of one class by another class. It allows you to create a new class that inherits the properties and methods of an existing class. This allows for code reuse and a more organized and efficient way of managing code.
    
2.  **Polymorphism**: It allows an object to take on many forms. In Java, polymorphism is implemented through method overriding and method overloading. Method overriding allows a subclass to provide a specific implementation of a method that is already provided by its superclass. Method overloading allows multiple methods in the same class to have the same name but different parameters.
    
3.  **Encapsulation**: It is the practice of keeping the internal state and behavior of an object hidden from the outside world. This is achieved by making the class's properties and methods private and providing public getter and setter methods to access and modify the properties.
    
4.  **Abstraction**: It is the process of hiding the implementation details of an object and exposing only the necessary information to the user. In Java, abstraction is achieved through interfaces and abstract classes. Interfaces allow you to define a set of methods that a class must implement, while abstract classes allow you to define a partial implementation of a class that can be extended by other classes.

### 2.) Difference b/w interface and abstract classes?
In Java, abstract classes and interfaces are both used for abstraction, but they have some key differences:

1.  **Abstract Classes**: An abstract class is a class that cannot be instantiated. It is a blueprint for other classes, and it can contain both abstract and non-abstract methods. Abstract methods are methods that have a method signature but no implementation. Subclasses that extend an abstract class must provide an implementation for all of its abstract methods. An abstract class can have constructors, and it can also have non-abstract methods with an implementation.
    
2.  **Interfaces**: An interface defines a set of methods that a class must implement. It can only contain abstract methods and constants. All methods in an interface are implicitly abstract and public, and interfaces cannot have any constructors. A class can implement one or more interfaces, and it must provide an implementation for all of the methods defined in the interfaces it implements.
    
3.  **Multiple Inheritance** : Java does not support multiple inheritance of classes, meaning a class can't extend multiple classes. However, a class can implement multiple interfaces.
    
4.  **Inheritance**: An abstract class can inherit from another class (Single Inheritance) and can also implement multiple interfaces. An interface can only inherit from other interfaces (Multiple Inheritance).
    
5.  **Access Modifiers**: In an abstract class, methods and variables can have various access modifiers (public, private, protected etc) but in interfaces all the methods and variables are implicitly public.
    

In general, if you want to provide a common interface for multiple classes and you don't want to provide any implementation, you should use an interface. If you want to provide a common implementation for multiple classes and you also want to provide some specific implementations, you should use an abstract class.

### 3.) What is immutable classes?

 Java, an immutable class is a class whose state cannot be modified after it is created. Once an object of an immutable class is created, its state cannot be changed, and it cannot be modified in any way. Instead, any changes to the state of the object must be done by creating a new object with the desired state.

Here are some of the characteristics of immutable classes:

1.  **All fields are final**: The fields of an immutable class are declared as final, which means they cannot be reassigned once they are set.
    
2.  **No setters**: Immutable classes do not have any setter methods, which means that the state of the object cannot be modified after it is created.
    
3.  **No mutable fields**: Immutable classes should not have any mutable fields, such as lists or maps, which can be modified after the object is created. Instead, they should use immutable data structures such as the `Collections.unmodifiableXXX` methods.
    
4.  **No methods that modify state**: Immutable classes should not have any methods that modify the state of the object. Instead, they should return new objects with the modified state.
    
5.  **Proper constructor** : Immutable classes should have a proper constructor that initializes all the fields of the class.
    

An example of an immutable class is String in Java. Once a String object is created, its value cannot be changed. If you want to change the value of a String, you need to

### 4) can we declare class as private?
In Java, a class can be declared as private, but it is not a commonly used practice. Private classes are only accessible within the same package as the class in which they are defined. They are not visible to other classes in the same package, and they cannot be accessed by classes in other packages.

Declaring a class as private can be useful in certain situations, such as when you want to create a helper class that is only used within a specific class or module. However, in general, it is better to use other access modifiers, such as `default`, `protected`, or `public` that allows more flexibility and encapsulation.

Here is an example of how you can declare a private class in Java:

```Java
class MyClass {     
private static class MyPrivateClass {   
//...     }
}
```

In this example, the `MyPrivateClass` is a private class that is only accessible within the `MyClass` class.

It's worth noting that, in most cases, instead of declaring a class private, it's better to use package-private(default) and use package level access control for encapsulation and hiding the implementation details.

In summary, private classes are not commonly used in Java and in most cases, it's better to use other access modifiers and encapsulation mechanisms.

### 5.) What is singleton class in java?
A singleton class in Java is a class that can only have one instance at any given time. This means that only one object of the class can be created, and any attempts to create additional objects will return the same instance. Singleton classes are useful in situations where you need to ensure that only one instance of a class exists, such as when you want to share a common resource across multiple parts of your application.

Here are some common ways to implement a singleton class in Java:

1.  **Eager Initialization**: You can create the singleton instance during class loading. This is the simplest and easiest way to create a singleton class.


```Java
public class Singleton { 
private static final Singleton instance = new Singleton(); 
private Singleton() {} 
public static Singleton getInstance() {   
return instance;    } 
}
```


2.  **Lazy Initialization**: You can create the singleton instance when it is first accessed. This approach is useful when the singleton class has a heavy initialization process.

```Java
public class Singleton { 
private static Singleton instance; 
private Singleton() {} 
public static Singleton getInstance() {
if (instance == null) {  
instance = new Singleton(); 
}        
return instance;
}

```










1) What are static blocks and static initializers?
		Static blocks or static initializers are used to initalize static fields in java.
		
2)  If you have given file system and DB system implementations with common inter face. How can we configure these classes in Java?
3) Difference between Abstract class and Interface?
4) Can we instantiate abstract class?
5) How can we get implemented methods in abstarct class?
6) can we write method implementation in Interface?
7) What is immutable objects in Java?
8) String s = "abc", String s1 = new String("abc") How many objects got created? String s = "abc"; s="abc"
9) What are collection interface?
10) Difference between ArrayList and LinkedList?
11) When to use ArrayList and LinkedList?
12) Difference between HashTable and HashMap?
13) Have you used ConcurrentHAshMap when to use it?
14) can we store null key in map?
 1.  Can you explain what a lambda expression is and how it is used in Java 8?
2.  How does the Stream API in Java 8 differ from traditional collections?
3.  Can you give an example of how the Date/Time API in Java 8 can be used to solve a specific problem?
4.  How does the Optional class in Java 8 help prevent null pointer exceptions?
5.  How does the Nashorn JavaScript Engine in Java 8 work and what are some use cases for it?
6.  Can you explain the difference between default and static methods in interfaces in Java 8?
7.  How the Base64 Encoding/Decoding feature can be used in a Java 8 application?
8.  Can you explain what is a functional interface and how it is used in Java 8?
9.  How does the forEach method work in Java 8 and how is it different from other iteration methods?
10.  How does the parallel stream feature work in Java 8 and what are some use cases for it?

1.  **What is an exception in Java?**
2.  **What are the different types of exceptions in Java?**
3.  **How do you handle exceptions in Java?**
4.  **What is the difference between a checked and an unchecked exception in Java?**
5.  **What is the difference between a try-catch block and a try-catch-finally block?**
6.  **What is the difference between a throw and a throws in Java?**
7.  **What is a custom exception in Java? How do you create one?**
8.  **What is a catch-all exception handler? When is it useful?**
9.  **What is the difference between exception chaining and exception wrapping?**
10.  **What is the best practice for exception handling in Java?**

### 6.)  Wha