# Homework #1 - Java OOP Concepts

## 1. Why do we need to use OOP? Some major OOP languages?

OOP (Object-Oriented Programming) is used to make code modular, reusable, and easier to maintain. OOP-written code is more readable and flexible.

**Major OOP languages:** Java, C++, Python, C#.

**Example:**

```java
class Car {
    String brand;
    int speed;
    
    void accelerate() {
        speed += 10;
        System.out.println("Speed: " + speed);
    }
}
```

In this example, we created a **Car** class and represented an object using OOP principles.

## 2. Interface vs Abstract class?

- **Interface:** Contains only method signatures, allows multiple inheritance.
- **Abstract Class:** Can contain both method signatures and implementations, can only be extended by one class.

**Example:**

```java
interface Animal {
    void makeSound();
}
class Dog implements Animal {
    public void makeSound() {
        System.out.println("Woof Woof");
    }
}
```

Here, **Dog** implements the **Animal** interface.

## 3. Why do we need equals and hashcode? When to override?

- **equals()**: Checks if two objects are equal based on content.
- **hashCode()**: Returns an integer based on the object's memory address.
- **When to override?** To ensure proper behavior in collections like HashMap, HashSet.

**Example:**

```java
class Person {
    String name;
    
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        Person person = (Person) obj;
        return name.equals(person.name);
    }
    
    @Override
    public int hashCode() {
        return name.hashCode();
    }
}
```

Here, **equals() and hashCode()** methods are overridden to ensure correct equality checking in `HashSet` or `HashMap`.

## 4. Diamond problem in Java? How to fix it?

Occurs when multiple inheritance leads to ambiguity in method resolution. **Solution:** Use interfaces, as Java does not allow multiple inheritance in classes.

## 5. Why do we need Garbage Collector? How does it run?

It automates memory management. The JVM identifies and removes unused objects.

## 6. Java `static` keyword usage?

- **Static Variables:** Belong to the class, not instances.
- **Static Methods:** Can be called without creating an instance.
- **Static Blocks:** Execute when the class is loaded.

## 7. What does Immutability mean? Where, How, and Why to use it?

**Immutable** objects cannot be changed (e.g., `String`). **Use cases:** Thread-safe programming, reliable data structures.

## 8. What do Composition and Aggregation mean, and what are the differences?

- **Composition:** One object is strongly dependent on another (strong association).
- **Aggregation:** Objects are related but can exist independently (weak association).

**Example:**

```java
class Engine {}
class Car {
    private Engine engine; // Composition
    Car() { engine = new Engine(); }
}
class University {}
class Student {
    private University university; // Aggregation
    Student(University university) { this.university = university; }
}
```

In **Composition**, objects are tightly bound; in **Aggregation**, they are loosely coupled.

## 9. What do Cohesion and Coupling mean, and what are the differences?

- **Cohesion:** Measures how closely related methods in a class are.
- **Coupling:** Measures dependency between classes. **Low coupling is preferred.**

## 10. What are Heap and Stack, and what are the differences?

- **Heap:** Stores objects (Garbage Collector operates here).
- **Stack:** Stores method calls and local variables.

## 11. What does Exception mean? Types of Exceptions?

- **Checked Exception:** Occurs at compile-time (IOException, SQLException).
- **Unchecked Exception:** Occurs at runtime (NullPointerException, ArithmeticException).

## 12. How to summarize ‘clean code’ as short as possible?

- **Readable, modular, reusable, and free of unnecessary code.**

## 13. What is the method of hiding in Java?

Method Hiding occurs when **static methods are redefined in subclasses.** Unlike Overriding, the method that gets called depends on the reference type, not the object.

## 14. What is the difference between abstraction and polymorphism in Java?

- **Abstraction:** Hides unnecessary details, showing only important parts (Abstract classes, Interfaces).
- **Polymorphism:** Allows the same method to be used in different ways (Method Overloading & Overriding).

