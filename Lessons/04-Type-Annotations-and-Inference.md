## 4. Type Annotations and Inference

TypeScript provides powerful type-checking features that help catch errors early. Understanding type annotations and inference is crucial for leveraging these features effectively.

### Explicit Type Annotations

Type annotations allow you to explicitly specify the type of a variable, function parameter, or return value. This makes your code more readable and helps prevent type-related errors.

```typescript
let username: string = "Alice";
let age: number = 25;
let isLoggedIn: boolean = true;

function add(a: number, b: number): number {
    return a + b;
}
```

In this example, `username`, `age`, and `isLoggedIn` have explicit type annotations. The `add` function specifies that it takes two numbers as parameters and returns a number.

### Type Inference

TypeScript can automatically infer the type of a variable based on its initial value. This means you don't always need to provide explicit type annotations.

```typescript
let city = "New York"; // Inferred as string
let temperature = 72;  // Inferred as number

function multiply(x: number, y: number) {
    return x * y; // Inferred return type as number
}
```

In the above code, TypeScript infers the types of `city` and `temperature` based on their assigned values. The `multiply` function's return type is inferred as `number`.

### Any and Unknown Types

1. **Any**: The `any` type allows a variable to hold values of any type, effectively opting out of type checking. Use it sparingly, as it can undermine the benefits of TypeScript's type system.

   ```typescript
   let randomValue: any = 42;
   randomValue = "Hello";
   randomValue = true;
   ```

   Here, `randomValue` can hold a number, string, or boolean without any type errors.

2. **Unknown**: The `unknown` type is similar to `any`, but safer. You must perform type checks before using a value of type `unknown`.

   ```typescript
   let userInput: unknown = "Hello, World";

   if (typeof userInput === "string") {
       console.log(userInput.toUpperCase());
   }
   ```

   In this example, `userInput` is of type `unknown`. Before calling `toUpperCase`, a type check ensures that `userInput` is a string.

[Next: 05-Union-and-Intersection-Types](./05-Union-and-Intersection-Types.md)