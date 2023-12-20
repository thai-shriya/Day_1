# Builder Design Pattern

The Builder Design Pattern is a creational pattern that provides a way to construct a complex object step by step. It allows the construction of different types and representations of an object using the same construction code.

Suppose you want to create a Person class with various attributes like name, age, address, etc., and you want to provide a flexible way to construct instances of this class.

// Product class
class Person {
private String name;
private int age;
private String address;
// other attributes...

    // private constructor to enforce the use of the builder
    private Person() {
    }

    // Getters...

    // Builder class
    static class Builder {
        private Person person;

        // Constructor
        Builder() {
            this.person = new Person();
        }

        // Setters for building attributes
        Builder name(String name) {
            person.name = name;
            return this;
        }

        Builder age(int age) {
            person.age = age;
            return this;
        }

        Builder address(String address) {
            person.address = address;
            return this;
        }

        // Additional setters for other attributes...

        // Build method to create the final instance
        Person build() {
            return person;
        }
    }

}

// Usage example
public class BuilderPatternExample {
public static void main(String[] args) {
// Using the builder to create a Person object
Person person = new Person.Builder()
.name("John")
.age(30)
.address("123 Main St")
.build();

        // Accessing the created Person object
        System.out.println("Name: " + person.getName());
        System.out.println("Age: " + person.getAge());
        System.out.println("Address: " + person.getAddress());
        // Access other attributes...
    }

}
