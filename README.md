# assign-7
1. Program to Access Method and Variable Without Creating an Object

In Java, you can access a method or variable without creating an object by using the static keyword.

Steps

Declare the variable as static.

Declare the method as static.

Access them directly using the class name (e.g., ClassName.methodName()).

Program Example
class Demo {
    static int number = 10;   // static variable

    static void display() {   // static method
        System.out.println("Static method accessed!");
        System.out.println("Number = " + number);
    }
}

public class Main {
    public static void main(String[] args) {
        // Accessing without creating an object
        Demo.display();
    }
}

2. Program to Implement Abstract Class and Method

An abstract class has:

At least one abstract method (method without body)

Cannot be instantiated

Must be inherited (extended) by another class

Child class must override the abstract method

Program Example
abstract class Animal {              // abstract class
    abstract void sound();           // abstract method

    void sleep() {                   // normal method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    @Override
    void sound() {                   // implementing abstract method
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal obj = new Dog();
        obj.sound();
        obj.sleep();
    }
}

3. What is Multiple Inheritance? Explain With Examples
Definition

Multiple Inheritance means a class can inherit features from more than one parent class.

Java

Java does NOT support multiple inheritance using classes (to avoid ambiguity known as the Diamond Problem).

But Java does support multiple inheritance using interfaces.

Example (Java using Interfaces)
interface A {
    void showA();
}

interface B {
    void showB();
}

class C implements A, B {   // multiple inheritance
    public void showA() {
        System.out.println("From A");
    }

    public void showB() {
        System.out.println("From B");
    }
}

public class Main {
    public static void main(String[] args) {
        C obj = new C();
        obj.showA();
        obj.showB();
    }
}

Example (C++ — supports true multiple inheritance)

(Just for comparison)

class A {
public:
    void displayA() { cout << "Class A"; }
};

class B {
public:
    void displayB() { cout << "Class B"; }
};

class C : public A, public B { };

int main() {
    C obj;
    obj.displayA();
    obj.displayB();
}
