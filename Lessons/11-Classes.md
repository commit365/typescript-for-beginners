## 11. Classes

Classes in TypeScript provide a blueprint for creating objects with specific properties and methods. They support object-oriented programming concepts such as encapsulation, inheritance, and access control.

### Class Properties and Methods

Classes can have properties (variables) and methods (functions) that define the behavior of the objects created from them.

```typescript
class Animal {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    speak(): void {
        console.log(`${this.name} makes a sound.`);
    }
}

const animal = new Animal("Dog");
animal.speak(); // Output: Dog makes a sound.
```

In this example, the `Animal` class has a property `name` and a method `speak`. The `speak` method uses the `name` property to output a message.

### Constructors and Inheritance

1. **Constructors**: A constructor is a special method used to initialize objects. It's called when a new instance of the class is created.

   ```typescript
   class Car {
       make: string;
       model: string;

       constructor(make: string, model: string) {
           this.make = make;
           this.model = model;
       }

       displayInfo(): void {
           console.log(`Car: ${this.make} ${this.model}`);
       }
   }

   const myCar = new Car("Toyota", "Corolla");
   myCar.displayInfo(); // Output: Car: Toyota Corolla
   ```

   Here, the `Car` class has a constructor that initializes the `make` and `model` properties.

2. **Inheritance**: Inheritance allows a class to inherit properties and methods from another class, promoting code reuse.

   ```typescript
   class Dog extends Animal {
       breed: string;

       constructor(name: string, breed: string) {
           super(name);
           this.breed = breed;
       }

       speak(): void {
           console.log(`${this.name} barks.`);
       }
   }

   const myDog = new Dog("Buddy", "Golden Retriever");
   myDog.speak(); // Output: Buddy barks.
   ```

   In this example, the `Dog` class extends the `Animal` class, inheriting its properties and methods. The `super` keyword is used to call the constructor of the parent class.

### Public, Private, and Protected Modifiers

Access modifiers control the visibility of class members.

1. **Public**: Members are accessible from anywhere. This is the default visibility.

   ```typescript
   class Person {
       public name: string;

       constructor(name: string) {
           this.name = name;
       }
   }

   const person = new Person("Alice");
   console.log(person.name); // Output: Alice
   ```

2. **Private**: Members are accessible only within the class they are defined in.

   ```typescript
   class BankAccount {
       private balance: number;

       constructor(initialBalance: number) {
           this.balance = initialBalance;
       }

       getBalance(): number {
           return this.balance;
       }
   }

   const account = new BankAccount(1000);
   console.log(account.getBalance()); // Output: 1000
   // console.log(account.balance); // Error: Property 'balance' is private and only accessible within class 'BankAccount'.
   ```

3. **Protected**: Members are accessible within the class they are defined in and in derived classes.

   ```typescript
   class Employee {
       protected employeeId: number;

       constructor(employeeId: number) {
           this.employeeId = employeeId;
       }
   }

   class Manager extends Employee {
       getEmployeeId(): number {
           return this.employeeId;
       }
   }

   const manager = new Manager(123);
   console.log(manager.getEmployeeId()); // Output: 123
   // console.log(manager.employeeId); // Error: Property 'employeeId' is protected and only accessible within class 'Employee' and its subclasses.
   ```

Access modifiers help encapsulate and protect the internal state of objects, ensuring that only authorized parts of the code can access or modify certain properties.

[Next: 12-Modules-and-Namespaces](./12-Modules-and-Namespaces.md)