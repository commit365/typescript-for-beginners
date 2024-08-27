## 21. Best Practices

Writing clean and maintainable TypeScript code is essential for building scalable applications. This lesson will cover best practices for writing TypeScript code and highlight common pitfalls and how to avoid them.

### Writing Clean and Maintainable TypeScript Code

1. **Use Type Annotations Wisely**: While TypeScript's type inference is powerful, use explicit type annotations where they add clarity or are necessary for complex types.

   ```typescript
   const multiply = (a: number, b: number): number => a * b;
   ```

2. **Leverage Interfaces and Type Aliases**: Use interfaces and type aliases to define clear and reusable type definitions.

   ```typescript
   interface User {
       name: string;
       age: number;
   }

   type ID = number | string;
   ```

3. **Prefer `const` and `let` over `var`**: Use `const` for variables that won't be reassigned and `let` for those that will. Avoid `var` to prevent scope-related issues.

   ```typescript
   const MAX_USERS = 100;
   let currentUserCount = 0;
   ```

4. **Organize Code with Modules**: Use modules to organize your code into separate files, making it easier to manage and maintain.

   ```typescript
   // user.ts
   export interface User {
       name: string;
       age: number;
   }

   // main.ts
   import { User } from './user';
   ```

5. **Consistent Naming Conventions**: Use consistent naming conventions for variables, functions, classes, and interfaces to improve code readability.

   ```typescript
   class UserService {
       getUserById(id: string): User {
           // ...
       }
   }
   ```

6. **Write Tests**: Ensure your code is reliable by writing tests. Use a testing framework like Jest to automate testing.

   ```typescript
   test('multiply function', () => {
       expect(multiply(2, 3)).toBe(6);
   });
   ```

### Common Pitfalls and How to Avoid Them

1. **Ignoring `any` Type**: Avoid using `any` unless absolutely necessary, as it bypasses type checking and can lead to runtime errors.

   ```typescript
   // Avoid
   let data: any;

   // Prefer specific types
   let data: string | number;
   ```

2. **Overusing Type Assertions**: Type assertions can be useful, but overusing them can lead to incorrect assumptions about types.

   ```typescript
   // Avoid unnecessary assertions
   let input = "Hello" as any as number;

   // Use them judiciously
   let input: unknown = "Hello";
   if (typeof input === "string") {
       console.log(input.toUpperCase());
   }
   ```

3. **Not Handling Null and Undefined**: Always handle `null` and `undefined` to avoid unexpected errors.

   ```typescript
   function greet(name: string | null): string {
       return name ? `Hello, ${name}` : "Hello, Guest";
   }
   ```

4. **Circular Dependencies**: Be cautious of circular dependencies in modules, which can lead to runtime errors or undefined behavior.

   ```typescript
   // Refactor code to avoid circular dependencies
   ```

5. **Ignoring Compiler Warnings**: Pay attention to TypeScript compiler warnings and errors, as they often indicate potential issues in your code.

   ```bash
   tsc --noEmit
   ```

   Use the above command to check for type errors without emitting JavaScript files.

By following these best practices and being aware of common pitfalls, you can write clean, maintainable, and reliable TypeScript code.

[Next: 22-Code-Quality-and-Linting](./22-Code-Quality-and-Linting.md)