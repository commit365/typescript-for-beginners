## 9. Literal Types and Type Guards

TypeScript allows you to use literal types and type guards to create more precise and safe code. These features help you define exact values a variable can hold and safely operate on different types.

### String and Number Literal Types

Literal types allow you to specify exact values a variable can have. This is useful for defining variables that can only hold a specific set of values.

1. **String Literal Types**:

   ```typescript
   type Direction = "up" | "down" | "left" | "right";

   function move(direction: Direction) {
       console.log(`Moving ${direction}`);
   }

   move("up");    // Valid
   move("left");  // Valid
   // move("forward"); // Error: Argument of type '"forward"' is not assignable to parameter of type 'Direction'.
   ```

   In this example, `Direction` is a union of string literal types. The `move` function only accepts one of the specified directions, preventing invalid input.

2. **Number Literal Types**:

   ```typescript
   type DiceRoll = 1 | 2 | 3 | 4 | 5 | 6;

   function rollDice(): DiceRoll {
       return (Math.floor(Math.random() * 6) + 1) as DiceRoll;
   }

   const roll = rollDice();
   console.log(`You rolled a ${roll}`);
   ```

   Here, `DiceRoll` is a union of number literal types, representing possible outcomes of a dice roll.

### Using Type Guards

Type guards are techniques used to determine the type of a variable at runtime, allowing you to safely perform operations based on that type.

1. **`typeof` Operator**:

   ```typescript
   function printValue(value: string | number) {
       if (typeof value === "string") {
           console.log(`String value: ${value.toUpperCase()}`);
       } else {
           console.log(`Number value: ${value.toFixed(2)}`);
       }
   }

   printValue("hello"); // Output: String value: HELLO
   printValue(42);      // Output: Number value: 42.00
   ```

   In this example, the `typeof` operator is used to check if `value` is a string or a number, allowing the function to handle each type appropriately.

2. **`instanceof` Operator**:

   ```typescript
   class Dog {
       bark() {
           console.log("Woof!");
       }
   }

   class Cat {
       meow() {
           console.log("Meow!");
       }
   }

   function makeSound(animal: Dog | Cat) {
       if (animal instanceof Dog) {
           animal.bark();
       } else {
           animal.meow();
       }
   }

   const myDog = new Dog();
   const myCat = new Cat();

   makeSound(myDog); // Output: Woof!
   makeSound(myCat); // Output: Meow!
   ```

   Here, the `instanceof` operator is used to determine if `animal` is an instance of `Dog` or `Cat`, allowing the function to call the appropriate method.

Type guards help ensure that your code operates safely on different types, reducing the risk of runtime errors.
