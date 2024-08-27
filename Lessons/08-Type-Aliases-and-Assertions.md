## 8. Type Aliases and Assertions

TypeScript provides ways to create custom types and assert types when you know more about a value than TypeScript does. These features help you write more readable and maintainable code.

### Creating Type Aliases

Type aliases allow you to create a new name for a type. This can be useful for simplifying complex types or making your code more readable.

```typescript
type Point = {
    x: number;
    y: number;
};

function printPoint(point: Point): void {
    console.log(`x: ${point.x}, y: ${point.y}`);
}

const myPoint: Point = { x: 10, y: 20 };
printPoint(myPoint);
```

In this example, `Point` is a type alias for an object with `x` and `y` properties. Using a type alias makes it easier to reuse and understand this structure throughout your code.

Type aliases can also be used with union types:

```typescript
type ID = number | string;

let userId: ID;
userId = 101;       // Valid
userId = "A101";    // Valid
```

Here, `ID` is a type alias for a union type that can be either a `number` or a `string`.

### Type Assertions

Type assertions allow you to override TypeScript's inferred type when you know more about the value than TypeScript does. This is similar to type casting in other languages.

There are two ways to perform type assertions:

1. **Angle-bracket syntax**:

   ```typescript
   let someValue: unknown = "Hello, TypeScript";
   let strLength: number = (<string>someValue).length;
   console.log(strLength); // Output: 17
   ```

2. **`as` syntax** (preferred in JSX and modern TypeScript):

   ```typescript
   let anotherValue: unknown = "Hello, World";
   let anotherStrLength: number = (anotherValue as string).length;
   console.log(anotherStrLength); // Output: 12
   ```

In both examples, `someValue` and `anotherValue` are initially of type `unknown`. Type assertions are used to tell TypeScript that these values are actually strings, allowing you to access string-specific properties like `length`.

Type assertions should be used cautiously, as they can lead to runtime errors if the assertion is incorrect. Always ensure that the value is indeed of the asserted type.

[Next: 09-Literal-Types-and-Type-Guards](./09-Literal-Types-and-Type-Guards.md)