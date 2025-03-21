# Homework #1

## 1. Why we need to use OOP? Some major OOP languages?
OOP (Object-Oriented Programming), kodun modüler, yeniden kullanılabilir ve bakımı kolay olması için kullanılır. OOP ile yazılan kodlar daha anlaşılır ve esnektir.

**Başlıca OOP dilleri:** Java, C++, Python, C#.

**Örnek:**
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
Bu örnekte bir **Car** sınıfı oluşturduk ve nesne yönelimli programlama ile bir nesne temsil ettik.

## 2. Interface vs Abstract class?
- **Interface:** Yalnızca metot imzalarını içerir, çoklu kalıtıma olanak tanır.
- **Abstract Class:** Hem metot imzaları hem de gövdeleri içerebilir, tek bir sınıftan türetilebilir.

**Örnek:**
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
Burada **Dog**, **Animal** arayüzünü uygular.

## 3. Why we need equals and hashcode? When to override?
- **equals()**: Nesnelerin içerik bazında eşit olup olmadığını kontrol eder.
- **hashCode()**: Nesnelerin bellek adresine bağlı bir tamsayı döndürür.
- **Ne zaman override edilir?** HashMap, HashSet gibi koleksiyonlarda doğru çalışmasını sağlamak için.

**Örnek:**
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
Burada **equals() ve hashCode()** metotlarını override ettik, böylece `HashSet` veya `HashMap` gibi veri yapıları içinde **eşitlik** düzgün çalışır.

## 4. Diamond problem in Java? How to fix it?
Çoklu kalıtımda aynı metodu farklı yollarla miras alırken oluşur. **Çözüm:** Interface’ler kullanılır, Java’da class'lar birden fazla sınıftan türetilemez.

## 5. Why we need Garbage Collector? How does it run?
Bellek yönetimini otomatikleştirmek için kullanılır. JVM, kullanılmayan nesneleri tespit edip temizler.

## 6. Java `static` keyword usage?
- **Static Variables:** Sınıfa aittir, nesneye bağlı değildir.
- **Static Methods:** Nesne oluşturmadan çağrılabilir.
- **Static Blocks:** Sınıf yüklendiğinde çalışır.

## 7. Immutability means? Where, How and Why to use it?
**Immutable** nesneler değiştirilemez (örneğin `String`). **Kullanım alanları:** Thread-safe programlama, güvenilir veri yapıları.

## 8. Composition and Aggregation means and differences?
- **Composition:** Bir nesne başka bir nesneye **bağımlıdır** (strong association). İç içe nesneler vardır ve bağımlılık yüksektir.
- **Aggregation:** Nesneler birbirinden bağımsızdır, **zayıf bağlıdır** (weak association).

**Örnek:**
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
Burada **Composition**'da nesne tamamen iç içe geçmiş, **Aggregation**'da dışarıdan bağlanmıştır.

## 9. Cohesion and Coupling means and differences?
- **Cohesion:** Bir sınıftaki metotların birbirine ne kadar bağlı olduğu.
- **Coupling:** Sınıfların birbirine ne kadar bağımlı olduğu. **Düşük coupling daha iyidir.**

## 10. Heap and Stack means and differences?
- **Heap:** Nesnelerin tutulduğu alan (Garbage Collector burada çalışır).
- **Stack:** Metot çağrıları ve yerel değişkenler tutulur.

## 11. Exception means? Type of Exceptions?
- **Checked Exception:** Compile-time hataları (IOException, SQLException).
- **Unchecked Exception:** Runtime hataları (NullPointerException, ArithmeticException).

## 12. How to summarize ‘clean code’ as short as possible?
- **Okunabilir, modüler, tekrar kullanılabilir ve gereksiz kod içermeyen kod yazmak.**

## 13. What is the method of hiding in Java?
Method Hiding, **static metotların alt sınıflarda yeniden tanımlanmasıdır.** Overriding’den farklı olarak, hangi metot çağrılacağı nesneye değil, referansa bağlıdır.

## 14. What is the difference between abstraction and polymorphism in Java?
- **Abstraction:** Gereksiz detayları gizleyerek yalnızca önemli kısımları gösterme (Abstract class, Interface).
- **Polymorphism:** Aynı metodu farklı şekillerde kullanabilme (Method Overloading & Overriding).

