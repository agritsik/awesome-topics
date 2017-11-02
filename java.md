## OOP
### Encapsulation & Methods
- Java offers four choices of access modifer: Public, Protected, Default (Package Private), Private
- Static member doesn’t require any instances of the class to be around e.g. `User u = new User(); u=null; sout(u.STATIC_VARIABLE);`
- Java is a “pass-by-value” language
- Every class has at least one constructor. In the case that no constructor is declared, the compiler will automatically insert a default no-argument constructor. The first statement of every constructor is either a call to another constructor within the class, using `this()`, or a call to a constructor in the direct parent class, using `super()`.
- In Java, the parent constructor is always executed before the child constructor. Think like the compiler.
- The constructor is part of the initialization process, so it is allowed to assign final instance variables in it. By the time the constructor completes, all final instance variables must have been set.
- Order of Initialization - superclass, Static variable declarations and static initializers, Instance variable declarations and instance initializers, The constructor


### Inheritance & Polymorphism
- a Java  file can have many classes but at most one public class. In fact, it may have no public class at all.
- The key is that when Java sees you define a class that doesn’t extend another class, it immediately adds the syntax `extends java.lang.Object` to the class definition.
- `this` and `super` may both be used for methods or variables defined in the parent class, but only `this` may be used for members defined in the current class.
- 5 rules for everriding method __TODO p253__
- it is not possible to override a private method in a parent class since the parent method is not accessible from the child class. Just because a child class doesn’t have access to the parent method, doesn’t mean the child class can’t de ne its own version of the method.
- Unlike overriding a method, in which a child method replaces the parent method in calls defined in both the parent and child, hidden methods only replace parent methods in the calls defined in the child class.
- final methods cannot be overridden or hidden
- Java doesn’t allow variables to be overridden but instead hidden. When you hide a variable, you define a variable with the same name as a variable in a parent class. This creates two copies of the variable within an instance of the child class: one instance defined for the parent reference and another defined for the child reference.
- Casting object rules __TODO p282__

### Interface & Abstract Class
- Astract methods can't be declared as `private` or `final`.
- Interface methods (inc. default) can be declared as `public` only.

### Enum
- If no access modifier is specified for the constructor of an enum type, the constructor is `private`.
- It is a compile-time error if the constructor of an enum type (§8.9) is declared `public` or `protected`.

### Nested Class
- member inner class - any accessor type, any inheritance, can be abstract of final, can access any to members of outer class. BUT cannot declare static fields/members
- local inner class - do not have accessor type, can access to any members of outer class. BUT can access only must be final or effectively final local variables (https://stackoverflow.com/a/20938132)
- anonymous inner class = local inner class wihout name
- static nested
__TODO p33__

## Collections
### Equals & Hashcode
### Comparator & Comparable
### Collections

## Extra
### JVM
### Exceptions
### Concurrency
