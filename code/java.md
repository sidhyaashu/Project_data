
**1. Object-Oriented Programming (OOP) Concepts**


1. **Which term describes the process of bundling data and related methods together to restrict unauthorized access?**

   **Answer:** d) Encapsulation

   **Explanation:** Encapsulation involves bundling data (variables) and methods (functions) that operate on the data into a single unit, typically a class, and restricting access to some of the object's components.

2. **Which of the following enables a method to have multiple implementations based on different sets of parameters, making it an example of compile-time polymorphism?**

   **Answer:** c) Method Overloading

   **Explanation:** Method overloading allows multiple methods in the same class to have the same name but different parameters (type, number, or both). This is resolved during compile time, exemplifying compile-time polymorphism.

3. **In Java, what mechanism allows one class to derive attributes and behaviors from another class, thereby improving reusability?**

   **Answer:** b) Inheritance

   **Explanation:** Inheritance enables a new class (subclass) to inherit attributes and methods from an existing class (superclass), promoting code reusability and hierarchical classifications.

4. **Which class acts as the foundational class from which all Java classes implicitly inherit?**

   **Answer:** b) Object

   **Explanation:** In Java, the `Object` class is the root class from which all other classes implicitly inherit.

5. **Which feature of OOP allows objects of different classes to respond to the same method call in a way that is specific to their type?**

   **Answer:** c) Polymorphism

   **Explanation:** Polymorphism allows methods to perform differently based on the object they are acting upon, enabling a single interface to represent different underlying forms (data types).

6. **What is the primary purpose of abstraction in Java?**

   **Answer:** c) To hide implementation details while exposing only necessary functionality

   **Explanation:** Abstraction focuses on exposing only the essential features of an object, hiding the complex implementation details, thus simplifying code management and enhancing security.

*Short Answer Questions:*

1. **Explain how encapsulation works in Java with a relevant example.**

   **Answer:** Encapsulation in Java is achieved by declaring class variables as private and providing public getter and setter methods to access and modify them. For example:

   ```java
   public class Person {
       private String name;

       public String getName() {
           return name;
       }

       public void setName(String name) {
           this.name = name;
       }
   }
   ```


   Here, the `name` variable is private, and access is controlled through public methods.

2. **What is polymorphism, and how does Java implement it? Provide an example.**

   **Answer:** Polymorphism allows methods to perform differently based on the object they are acting upon. Java implements polymorphism through method overriding and method overloading. For example:

   ```java
   class Animal {
       void sound() {
           System.out.println("Animal makes a sound");
       }
   }

   class Dog extends Animal {
       void sound() {
           System.out.println("Dog barks");
       }
   }
   ```


   Here, the `Dog` class overrides the `sound` method of the `Animal` class, providing a specific implementation.

3. **Describe how Java achieves static polymorphism, along with a short code snippet.**

   **Answer:** Java achieves static polymorphism through method overloading, where multiple methods have the same name but different parameters. For example:

   ```java
   class MathUtils {
       int add(int a, int b) {
           return a + b;
       }

       double add(double a, double b) {
           return a + b;
       }
   }
   ```


   Here, the `add` method is overloaded to handle both integer and double parameters.

4. **How does inheritance contribute to code reusability? Illustrate with an example.**

   **Answer:** Inheritance allows a new class to inherit properties and methods from an existing class, promoting code reusability. For example:

   ```java
   class Vehicle {
       void start() {
           System.out.println("Vehicle starts");
       }
   }

   class Car extends Vehicle {
       // Inherits start() method
   }
   ```


   Here, `Car` inherits the `start` method from `Vehicle`, reusing existing code.

5. **Compare object-oriented programming with procedural programming, mentioning key advantages.**

   **Answer:** Object-oriented programming (OOP) organizes code into objects representing real-world entities, promoting modularity, reusability, and scalability. Procedural programming focuses on functions and procedures, which can lead to code duplication and less modularity. OOP's key advantages include improved code maintainability and the ability to model complex systems more naturally.

6. **Discuss practical scenarios where inheritance is beneficial in software development.**

   **Answer:** Inheritance is beneficial when creating hierarchical classifications, such as in GUI frameworks where a base `Component` class is extended by `Button`, `Label`, etc., allowing shared functionality and polymorphic behavior.


---

**2. Java Memory Management & Object Lifecycle.**


1. **What is the correct return type of a Java constructor?**  
   **Answer:** **d) It does not return a value**  
   **Explanation:** Constructors in Java do not have a return type, not even `void`. They are special methods used for object initialization.

2. **Which special method in Java is automatically invoked by the garbage collector before an object is destroyed?**  
   **Answer:** **a) finalize()**  
   **Explanation:** The `finalize()` method is invoked by the garbage collector before reclaiming the memory of an object. However, it is deprecated in newer versions of Java.

3. **Which keyword is used in Java to allocate memory dynamically for an array?**  
   **Answer:** **b) new**  
   **Explanation:** The `new` keyword is used in Java to allocate memory dynamically for objects and arrays.

4. **Which mechanism in Java ensures that memory occupied by objects that are no longer in use is reclaimed?**  
   **Answer:** **a) Garbage Collection**  
   **Explanation:** Java's automatic garbage collection mechanism reclaims memory occupied by unused objects, preventing memory leaks.

5. **What happens when a Java object no longer has any active references?**  
   **Answer:** **b) It is automatically removed by the garbage collector**  
   **Explanation:** When an object has no active references, it becomes eligible for garbage collection and is automatically removed from memory.

---

### **Short Answer Questions:**

1. **Explain constructor overloading in Java with an example.**  
   **Answer:** Constructor overloading in Java allows multiple constructors with different parameter lists in the same class. It enables different ways of object initialization.  
   **Example:**
   ```java
   class Person {
       String name;
       int age;

       // Constructor with no parameters
       Person() {
           this.name = "Unknown";
           this.age = 0;
       }

       // Constructor with parameters
       Person(String name, int age) {
           this.name = name;
           this.age = age;
       }
   }

   public class Main {
       public static void main(String[] args) {
           Person p1 = new Person();
           Person p2 = new Person("Alice", 25);
           System.out.println(p1.name + " - " + p1.age); // Unknown - 0
           System.out.println(p2.name + " - " + p2.age); // Alice - 25
       }
   }
   ```

2. **Why is Java called a platform-independent language?**  
   **Answer:** Java is platform-independent because it follows the "Write Once, Run Anywhere" (WORA) principle. Java programs are compiled into bytecode (`.class` files), which can run on any system with a Java Virtual Machine (JVM), irrespective of the underlying hardware and OS.

3. **What is instance variable hiding, and how does it affect program behavior?**  
   **Answer:** Instance variable hiding occurs when a subclass declares a variable with the same name as a variable in the parent class, effectively "hiding" the superclass variable. It can lead to confusion because accessing the variable through an object reference determines which variable is used.  
   **Example:**
   ```java
   class Parent {
       int x = 10;
   }

   class Child extends Parent {
       int x = 20;  // Hides parent class variable x

       void show() {
           System.out.println(x);         // 20 (child variable)
           System.out.println(super.x);   // 10 (parent variable)
       }
   }

   public class Main {
       public static void main(String[] args) {
           Child c = new Child();
           c.show();
       }
   }
   ```

4. **Describe the importance of garbage collection in Java.**  
   **Answer:** Garbage collection is crucial in Java as it automatically manages memory by reclaiming unused objects, reducing memory leaks, and improving application efficiency. It eliminates the need for manual memory management, preventing issues like dangling pointers and memory fragmentation.

5. **How does Java handle memory allocation for primitive data types and objects?**  
   **Answer:**  
   - **Primitive Data Types:** Stored in the **stack** memory for efficient access.  
   - **Objects:** Stored in the **heap** memory, with references stored in the stack. Memory for objects is managed by the garbage collector.

6. **What role does the finalize() method play in memory management?**  
   **Answer:** The `finalize()` method is intended to allow an object to perform cleanup actions before being garbage collected. However, it is deprecated in newer Java versions due to its unpredictable execution timing and inefficiency. Instead, Java recommends using `try-with-resources` or explicit `close()` methods for resource management.

---

### **Multiple-Choice Questions:**

1. **Which of these is not a valid class type in Java?**  
   **Answer:** **b) static**  
   **Explanation:** The `static` keyword cannot be used to define a top-level class. However, an inner class can be declared `static`.

2. **Which type of class can be accessed by any other class within a Java application?**  
   **Answer:** **c) Public**  
   **Explanation:** A `public` class is accessible from any other class in the Java application.

3. **What is the recommended access modifier for class variables to promote data security?**  
   **Answer:** **b) Private**  
   **Explanation:** Declaring class variables as `private` ensures encapsulation and prevents direct modification from outside the class.

4. **What is the role of an abstract class in Java?**  
   **Answer:** **b) To provide a blueprint for subclasses**  
   **Explanation:** An `abstract` class cannot be instantiated and serves as a blueprint for derived classes, defining methods that must be implemented.

5. **How does the static keyword affect a method or variable in Java?**  
   **Answer:** **b) It allows it to be shared among all objects of the class**  
   **Explanation:** A `static` variable or method belongs to the class rather than any specific object, meaning all instances share it.

---

### **Short Answer Questions:**

1. **Explain the significance of the static keyword with a practical example.**  
   **Answer:** The `static` keyword allows a variable or method to belong to the class rather than instances. This means it can be accessed without creating an object.  
   **Example:**
   ```java
   class Counter {
       static int count = 0;

       Counter() {
           count++;
           System.out.println("Count: " + count);
       }
   }

   public class Main {
       public static void main(String[] args) {
           Counter c1 = new Counter();
           Counter c2 = new Counter();
           Counter c3 = new Counter();
           // Output: Count: 1, Count: 2, Count: 3
       }
   }
   ```
   Here, the `count` variable is shared across all instances.

2. **How do access modifiers impact data security and encapsulation in Java?**  
   **Answer:**  
   - `private`: Ensures data hiding by restricting access to within the class.  
   - `protected`: Allows access within the same package and subclasses.  
   - `public`: Allows access from any class.  
   - `default` (no modifier): Accessible within the same package.  
   Using `private` and providing getter/setter methods enhances security and maintains encapsulation.

3. **Discuss the difference between abstract classes and interfaces in Java.**  
   **Answer:**  
   - **Abstract Class:**
     - Can have both abstract (unimplemented) and concrete (implemented) methods.
     - Supports constructors.
     - Can have instance variables.
   - **Interface:**
     - Only contains abstract methods (until Java 8, which introduced default methods).
     - Cannot have instance variables (only constants).
     - A class can implement multiple interfaces but can extend only one abstract class.  

4. **Why should class variables ideally be declared private?**  
   **Answer:** Declaring class variables as `private` ensures **encapsulation** by preventing direct access or modification from outside the class. Instead, controlled access is provided through getter and setter methods, enforcing validation and maintaining data integrity.

5. **Explain the concept of method hiding in Java.**  
   **Answer:** Method hiding occurs when a `static` method in a superclass is redefined with the same signature in a subclass. Unlike method overriding, method hiding is resolved at compile-time based on the reference type, not runtime.  
   **Example:**
   ```java
   class Parent {
       static void show() {
           System.out.println("Parent show()");
       }
   }

   class Child extends Parent {
       static void show() { // Method hiding
           System.out.println("Child show()");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Parent p = new Child();
           p.show(); // Calls Parent's show() because it's static (method hiding)
       }
   }
   ```

6. **What happens when a method in a subclass has the same signature as a method in its superclass?**  
   **Answer:** This is called **method overriding**. The subclass method overrides the superclass method, and at runtime, the subclass method is executed instead of the superclass method when called using an instance of the subclass. This follows **runtime polymorphism**.  
   **Example:**
   ```java
   class Parent {
       void display() {
           System.out.println("Parent display()");
       }
   }

   class Child extends Parent {
       @Override
       void display() {
           System.out.println("Child display()");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Parent obj = new Child();
           obj.display(); // Output: Child display()
       }
   }
   ```

---

### **Multiple-Choice Questions:**

1. **What does JIT stand for in Java?**  
   **Answer:** **a) Just-In-Time**  
   **Explanation:** The **Just-In-Time (JIT) Compiler** optimizes Java bytecode execution by compiling it into native machine code at runtime for faster performance.

2. **What does JVM stand for?**  
   **Answer:** **a) Java Virtual Machine**  
   **Explanation:** The **Java Virtual Machine (JVM)** is responsible for running Java applications by interpreting or compiling bytecode into machine code.

3. **What is the main function of the JVM?**  
   **Answer:** **a) To execute Java code on multiple platforms**  
   **Explanation:** The JVM enables **platform independence** by interpreting Java bytecode and executing it on different operating systems.

4. **What is the role of bytecode in Java's execution model?**  
   **Answer:** **b) It enables Java programs to run on any platform with a JVM**  
   **Explanation:** Java source code is compiled into **bytecode**, which can run on any device with a compatible **JVM**.

5. **Why is Java considered a "Write Once, Run Anywhere" language?**  
   **Answer:** **a) Because it supports cross-platform execution via bytecode**  
   **Explanation:** Java programs are compiled into **bytecode**, which the JVM interprets, allowing them to run on any platform.

---

### **Short Answer Questions:**

1. **Explain how Java achieves platform independence.**  
   **Answer:**  
   Java achieves **platform independence** through its **bytecode execution model**. Java programs are compiled into **bytecode** by the **Javac compiler**. This bytecode is then interpreted or compiled by the **JVM** on any platform that has a compatible **JRE (Java Runtime Environment)**, ensuring the **Write Once, Run Anywhere (WORA)** principle.

2. **What is the role of the Java Virtual Machine in executing Java programs?**  
   **Answer:**  
   The **JVM (Java Virtual Machine)** acts as an **interpreter and runtime environment** for Java programs. It performs the following tasks:
   - Loads and verifies **bytecode**.
   - Converts bytecode into **machine code** using the **JIT compiler**.
   - Manages **memory allocation and garbage collection**.
   - Ensures **security** by enforcing runtime checks.

3. **Why is the concept of bytecode important in Java?**  
   **Answer:**  
   **Bytecode** is a crucial part of Java’s execution model because:
   - It allows Java programs to be **platform-independent**.
   - It is an **intermediate representation** that can be efficiently executed by the **JVM**.
   - It enables **security** by allowing the JVM to check and verify the code before execution.
   - It makes Java **more efficient** than purely interpreted languages.

4. **How does JIT compilation improve Java program performance?**  
   **Answer:**  
   **Just-In-Time (JIT) Compilation** improves Java performance by:
   - **Compiling bytecode into native machine code** at runtime.
   - **Reducing interpretation overhead**, as compiled code executes faster.
   - **Caching frequently used methods**, so they don’t need to be recompiled.
   - **Optimizing code execution** by removing redundant operations.

5. **Discuss the difference between interpreted and compiled languages in relation to Java.**  
   **Answer:**  
   - **Interpreted Languages (e.g., Python, JavaScript):**
     - Code is executed **line-by-line** by an interpreter.
     - Slower execution due to real-time interpretation.
   - **Compiled Languages (e.g., C, C++):**
     - Code is **fully compiled** into machine code before execution.
     - Faster execution but platform-dependent.
   - **Java's Hybrid Model:**
     - Java is **first compiled** into bytecode (like compiled languages).
     - The JVM **interprets or compiles** bytecode at runtime (like interpreted languages).
     - This combines **portability** with **performance optimization**.

6. **Explain how the Java ClassLoader manages the loading of classes during execution.**  
   **Answer:**  
   The **Java ClassLoader** is responsible for **dynamically loading classes** into memory during runtime. It performs the following tasks:
   - **Bootstrap ClassLoader**: Loads core Java classes (`java.lang` package).
   - **Extension ClassLoader**: Loads classes from the `ext` directory.
   - **Application ClassLoader**: Loads classes from the application's classpath.
   - **Custom ClassLoaders**: Developers can create custom loaders for special use cases.
   The **ClassLoader** ensures that only trusted classes are loaded, improving **security and efficiency**.

---
