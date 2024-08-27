## 10. Generics

Generics in TypeScript allow you to create reusable components that work with a variety of types, providing flexibility and type safety. They enable you to define functions, interfaces, and classes that can operate on different data types without sacrificing type checking.

### Introduction to Generics

Generics provide a way to create components that can work with any data type. You define a generic type parameter using angle brackets (`<>`), which can then be used throughout your component.

```typescript
function identity<T>(value: T): T {
    return value;
}

console.log(identity<number>(42));    // Output: 42
console.log(identity<string>("Hello")); // Output: Hello
```

In this example, the `identity` function is generic, with the type parameter `T`. This allows the function to accept and return a value of any type, specified when the function is called.

### Generic Functions and Interfaces

1. **Generic Functions**: You can use generics to create functions that work with different types while maintaining type safety.

   ```typescript
   function wrapInArray<T>(value: T): T[] {
       return [value];
   }

   const numberArray = wrapInArray<number>(5); // Type: number[]
   const stringArray = wrapInArray<string>("Hello"); // Type: string[]
   ```

   Here, the `wrapInArray` function takes a value of any type `T` and returns an array containing that value.

2. **Generic Interfaces**: Interfaces can also be generic, allowing you to define a structure that can work with various types.

   ```typescript
   interface Pair<T, U> {
       first: T;
       second: U;
   }

   const numberPair: Pair<number, number> = { first: 1, second: 2 };
   const stringNumberPair: Pair<string, number> = { first: "Age", second: 30 };
   ```

   In this example, the `Pair` interface is generic with two type parameters `T` and `U`, allowing you to create pairs of different types.

### Constraints in Generics

Constraints allow you to restrict the types that can be used with generics, ensuring that the generic type meets certain criteria.

```typescript
interface Lengthwise {
    length: number;
}

function logLength<T extends Lengthwise>(item: T): void {
    console.log(item.length);
}

logLength("Hello"); // Output: 5
logLength([1, 2, 3]); // Output: 3
// logLength(123); // Error: Argument of type 'number' is not assignable to parameter of type 'Lengthwise'.
```

In this example, the `logLength` function has a constraint `T extends Lengthwise`, meaning `T` must have a `length` property. This ensures that you can safely access `length` on the `item` parameter.

Constraints help you create more robust and type-safe generic components by enforcing certain properties or methods on the types used.

[Next: 11-Classes](./11-Classes.md)