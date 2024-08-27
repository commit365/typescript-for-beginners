## 13. Decorators

Decorators in TypeScript are a special kind of declaration that can be attached to classes, methods, properties, or parameters. They provide a way to add annotations and a meta-programming syntax for class declarations and members.

### Introduction to Decorators

Decorators are functions that are prefixed with an `@` symbol and are used to modify or enhance classes and their members. They are a powerful feature that allows you to add additional behavior to your code in a declarative way.

To use decorators, you need to enable the `experimentalDecorators` option in your `tsconfig.json` file:

```json
{
  "compilerOptions": {
    "experimentalDecorators": true
  }
}
```

### Class, Method, and Property Decorators

1. **Class Decorators**: A class decorator is applied to the constructor of a class. It can be used to observe, modify, or replace a class definition.

   ```typescript
   function sealed(constructor: Function) {
       Object.seal(constructor);
       Object.seal(constructor.prototype);
   }

   @sealed
   class Greeter {
       greeting: string;
       constructor(message: string) {
           this.greeting = message;
       }
       greet() {
           return `Hello, ${this.greeting}`;
       }
   }
   ```

   In this example, the `sealed` decorator seals the `Greeter` class, preventing new properties from being added to it.

2. **Method Decorators**: A method decorator is applied to a method's property descriptor. It can be used to modify the method's behavior.

   ```typescript
   function log(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
       const originalMethod = descriptor.value;
       descriptor.value = function (...args: any[]) {
           console.log(`Calling ${propertyKey} with arguments: ${args}`);
           return originalMethod.apply(this, args);
       };
   }

   class Calculator {
       @log
       add(a: number, b: number): number {
           return a + b;
       }
   }

   const calculator = new Calculator();
   console.log(calculator.add(2, 3)); // Output: Calling add with arguments: 2,3
                                      //         5
   ```

   Here, the `log` decorator logs the method name and arguments every time the `add` method is called.

3. **Property Decorators**: A property decorator is applied to a class property. It can be used to modify the property's metadata.

   ```typescript
   function readonly(target: any, propertyKey: string) {
       Object.defineProperty(target, propertyKey, {
           writable: false
       });
   }

   class Person {
       @readonly
       name: string = "John Doe";
   }

   const person = new Person();
   // person.name = "Jane Doe"; // Error: Cannot assign to read-only property 'name'
   ```

   In this example, the `readonly` decorator makes the `name` property of the `Person` class read-only.

Decorators provide a powerful way to add behavior to your classes and their members, making your code more modular and expressive. They are commonly used in frameworks like Angular to add metadata to classes and methods.

[Next: 14-Mixins](./14-Mixins.md)