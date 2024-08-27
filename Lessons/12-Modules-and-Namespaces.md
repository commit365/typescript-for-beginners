## 12. Modules and Namespaces

TypeScript provides modules and namespaces to organize and manage code, especially in larger projects. Modules are the preferred way to structure code, while namespaces are used for organizing code within a module.

### Importing and Exporting Modules

Modules allow you to break your code into separate files, each with its own scope. You can export functions, classes, variables, and interfaces from one module and import them into another.

1. **Exporting**: Use the `export` keyword to make a variable, function, class, or interface available outside the module.

   ```typescript
   // mathUtils.ts
   export function add(a: number, b: number): number {
       return a + b;
   }

   export const PI = 3.14;
   ```

2. **Importing**: Use the `import` keyword to bring exported members into another module.

   ```typescript
   // main.ts
   import { add, PI } from './mathUtils';

   console.log(add(5, 3)); // Output: 8
   console.log(PI);        // Output: 3.14
   ```

   You can also use `export default` to export a single value from a module, which can be imported without curly braces:

   ```typescript
   // logger.ts
   export default function log(message: string): void {
       console.log(message);
   }

   // main.ts
   import log from './logger';

   log('Hello, TypeScript!'); // Output: Hello, TypeScript!
   ```

### Understanding Namespaces

Namespaces are used to organize code within a single file or module, helping to avoid naming conflicts. They are useful for grouping related functionalities.

1. **Defining a Namespace**: Use the `namespace` keyword to define a namespace and group related code.

   ```typescript
   namespace Geometry {
       export function calculateArea(radius: number): number {
           return Math.PI * radius * radius;
       }

       export function calculateCircumference(radius: number): number {
           return 2 * Math.PI * radius;
       }
   }

   console.log(Geometry.calculateArea(5)); // Output: 78.53981633974483
   console.log(Geometry.calculateCircumference(5)); // Output: 31.41592653589793
   ```

   In this example, the `Geometry` namespace groups functions related to geometric calculations.

2. **Nested Namespaces**: You can nest namespaces to further organize code.

   ```typescript
   namespace Geometry {
       export namespace Circle {
           export function calculateArea(radius: number): number {
               return Math.PI * radius * radius;
           }
       }
   }

   console.log(Geometry.Circle.calculateArea(5)); // Output: 78.53981633974483
   ```

   Here, the `Circle` namespace is nested within the `Geometry` namespace, indicating that the function is specific to circles.

Namespaces are primarily used for organizing code within a module, while modules are used for organizing code across multiple files. In modern TypeScript, modules are generally preferred for code organization, especially when working with external libraries and frameworks.

[Next: 13-Decorators](./13-Decorators.md)