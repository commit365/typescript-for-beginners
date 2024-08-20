## 16. Advanced Type Manipulation

TypeScript provides advanced features for manipulating types, allowing you to create more dynamic and flexible type definitions. These features include conditional types, mapped types, and template literal types.

### Conditional Types

Conditional types allow you to choose one type or another based on a condition. They use a syntax similar to ternary operators.

```typescript
type IsString<T> = T extends string ? "Yes" : "No";

type Test1 = IsString<string>; // "Yes"
type Test2 = IsString<number>; // "No"
```

In this example, `IsString` is a conditional type that checks if `T` extends `string`. If so, it resolves to `"Yes"`; otherwise, it resolves to `"No"`.

### Mapped Types

Mapped types allow you to create new types by transforming properties of an existing type. They are useful for applying the same transformation to each property in a type.

```typescript
interface User {
    name: string;
    age: number;
    email: string;
}

type OptionalUser = {
    [K in keyof User]?: User[K];
};

const partialUser: OptionalUser = { name: "Alice" };
```

In this example, `OptionalUser` is a mapped type that makes all properties of `User` optional. The `keyof` operator is used to iterate over the keys of `User`.

You can also use mapped types to make all properties readonly:

```typescript
type ReadonlyUser = {
    readonly [K in keyof User]: User[K];
};

const readonlyUser: ReadonlyUser = { name: "Bob", age: 25, email: "bob@example.com" };
// readonlyUser.age = 26; // Error: Cannot assign to 'age' because it is a read-only property.
```

### Template Literal Types

Template literal types allow you to create new string literal types by combining string literals with unions.

```typescript
type Color = "red" | "green" | "blue";
type Brightness = "light" | "dark";

type Theme = `${Brightness}-${Color}`;

const theme1: Theme = "light-red"; // Valid
const theme2: Theme = "dark-blue"; // Valid
// const theme3: Theme = "bright-yellow"; // Error: Type '"bright-yellow"' is not assignable to type 'Theme'.
```

In this example, `Theme` is a template literal type that combines `Brightness` and `Color` to create a set of valid theme strings.

Advanced type manipulation features in TypeScript allow you to create more expressive and flexible type definitions, enabling you to write more robust and type-safe code.
