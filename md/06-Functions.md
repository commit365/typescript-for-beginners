## 6. Functions

Functions are a fundamental part of TypeScript, allowing you to encapsulate logic and reuse code. TypeScript enhances functions with type safety and additional features like optional and default parameters.

### Function Types and Signatures

In TypeScript, you can specify the types of a function's parameters and its return value, creating a function signature. This helps ensure that functions are used correctly.

```typescript
function add(a: number, b: number): number {
    return a + b;
}

let result: number = add(5, 3); // Valid
// let wrongResult: number = add("5", "3"); // Error: Argument of type 'string' is not assignable to parameter of type 'number'.
```

In this example, the `add` function takes two `number` parameters and returns a `number`. The function signature enforces these types, preventing incorrect usage.

### Optional and Default Parameters

TypeScript allows you to define optional and default parameters in functions, providing flexibility in how functions are called.

1. **Optional Parameters**: Use the `?` symbol to mark a parameter as optional. Optional parameters must come after required parameters.

   ```typescript
   function greet(name: string, greeting?: string): string {
       return `${greeting || "Hello"}, ${name}!`;
   }

   console.log(greet("Alice"));          // Output: Hello, Alice!
   console.log(greet("Bob", "Hi"));      // Output: Hi, Bob!
   ```

   In this example, the `greeting` parameter is optional. If not provided, it defaults to `"Hello"`.

2. **Default Parameters**: Assign a default value to a parameter, which is used if no argument is provided.

   ```typescript
   function multiply(a: number, b: number = 1): number {
       return a * b;
   }

   console.log(multiply(5));             // Output: 5
   console.log(multiply(5, 3));          // Output: 15
   ```

   Here, the `b` parameter has a default value of `1`, so calling `multiply(5)` uses this default value.

### Rest Parameters

Rest parameters allow you to pass an arbitrary number of arguments to a function. Use the `...` syntax to define a rest parameter, which collects all remaining arguments into an array.

```typescript
function sum(...numbers: number[]): number {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3));               // Output: 6
console.log(sum(4, 5, 6, 7, 8));         // Output: 30
```

In this example, the `sum` function uses a rest parameter `numbers` to accept any number of `number` arguments and calculates their sum.
