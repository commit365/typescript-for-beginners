### 3. Primitive Types

TypeScript provides several basic types that are similar to those in JavaScript, but with added type safety. Let's explore these types:

#### Number, String, Boolean

1. **Number**: Represents both integer and floating-point numbers. TypeScript also supports hexadecimal, octal, and binary literals.

   ```typescript
   let age: number = 30;
   let price: number = 19.99;
   ```

2. **String**: Used for text data. You can use single quotes, double quotes, or template literals (backticks) for string values.

   ```typescript
   let firstName: string = "John";
   let greeting: string = `Hello, ${firstName}`;
   ```

3. **Boolean**: Represents true or false values.

   ```typescript
   let isActive: boolean = true;
   let hasPermission: boolean = false;
   ```

#### Arrays and Tuples

1. **Arrays**: A collection of values of the same type. You can define an array using square brackets or the `Array` generic type.

   ```typescript
   let numbers: number[] = [1, 2, 3, 4, 5];
   let fruits: Array<string> = ["apple", "banana", "cherry"];
   ```

2. **Tuples**: An array with a fixed number of elements, where each element can have a different type.

   ```typescript
   let person: [string, number] = ["Alice", 25];
   ```

   In this example, `person` is a tuple with a `string` and a `number`.

#### Enums

Enums allow you to define a set of named constants, making your code more readable and maintainable.

```typescript
enum Color {
    Red,
    Green,
    Blue
}

let favoriteColor: Color = Color.Green;
```

By default, enum values start at 0 and increment by 1. You can also assign specific values to enum members:

```typescript
enum Status {
    Active = 1,
    Inactive,
    Pending
}

let currentStatus: Status = Status.Active;
```

In this example, `Status.Active` is assigned the value 1, and the subsequent members increment from there.
