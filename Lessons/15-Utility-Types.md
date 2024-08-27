## 15. Utility Types

TypeScript provides several built-in utility types that help transform and manipulate types. These utility types make it easier to work with complex type transformations and can significantly enhance code readability and maintainability.

### Partial, Readonly, Pick, Omit, etc.

1. **Partial**: The `Partial` utility type makes all properties of a type optional. This is useful when you need to work with objects that may not have all properties set.

   ```typescript
   interface User {
       name: string;
       age: number;
       email: string;
   }

   function updateUser(user: User, updates: Partial<User>): User {
       return { ...user, ...updates };
   }

   const user: User = { name: "Alice", age: 30, email: "alice@example.com" };
   const updatedUser = updateUser(user, { age: 31 });
   console.log(updatedUser); // Output: { name: "Alice", age: 31, email: "alice@example.com" }
   ```

2. **Readonly**: The `Readonly` utility type makes all properties of a type readonly, preventing them from being modified.

   ```typescript
   const user: Readonly<User> = { name: "Bob", age: 25, email: "bob@example.com" };
   // user.age = 26; // Error: Cannot assign to 'age' because it is a read-only property.
   ```

3. **Pick**: The `Pick` utility type creates a new type by selecting a subset of properties from an existing type.

   ```typescript
   type UserPreview = Pick<User, "name" | "email">;

   const preview: UserPreview = { name: "Charlie", email: "charlie@example.com" };
   ```

   In this example, `UserPreview` includes only the `name` and `email` properties from the `User` type.

4. **Omit**: The `Omit` utility type creates a new type by excluding specific properties from an existing type.

   ```typescript
   type UserWithoutEmail = Omit<User, "email">;

   const userWithoutEmail: UserWithoutEmail = { name: "Dave", age: 40 };
   ```

   Here, `UserWithoutEmail` includes all properties from `User` except for `email`.

5. **Record**: The `Record` utility type constructs a type with a set of properties `K` of type `T`.

   ```typescript
   type Role = "admin" | "user" | "guest";

   const rolePermissions: Record<Role, string[]> = {
       admin: ["read", "write", "delete"],
       user: ["read", "write"],
       guest: ["read"]
   };
   ```

   In this example, `rolePermissions` is a record where each role has an associated array of permissions.

6. **Required**: The `Required` utility type makes all properties of a type required.

   ```typescript
   interface OptionalUser {
       name?: string;
       age?: number;
   }

   const completeUser: Required<OptionalUser> = { name: "Eve", age: 28 };
   ```

   Here, `completeUser` requires both `name` and `age` to be present.

Utility types are powerful tools that help you work with types more effectively in TypeScript, allowing you to create more flexible and expressive type definitions.

[Next: 16-Advanced-Type-Manipulation](./16-Advanced-Type-Manipulation.md)