## 1. What is TypeScript?

### Overview of TypeScript

TypeScript is a strongly typed programming language that builds on JavaScript, giving you better tooling at any scale. Developed and maintained by Microsoft, TypeScript is a superset of JavaScript, which means any valid JavaScript code is also valid TypeScript code. It introduces static typing to JavaScript, helping developers catch errors early in the development process.

### Benefits of Using TypeScript Over JavaScript

- **Static Typing**: TypeScript's static typing allows you to specify types for variables, function parameters, and return values, reducing runtime errors and improving code quality.
- **Improved Tooling**: TypeScript provides enhanced code editors with features like autocompletion, navigation, and refactoring, making development more efficient.
- **Better Code Readability and Maintainability**: With explicit types, your code becomes more readable and easier to maintain, especially in large codebases.
- **Advanced Features**: TypeScript supports modern JavaScript features and adds additional capabilities like interfaces, enums, and decorators.
- **Community and Ecosystem**: TypeScript is widely adopted and supported by a strong community, with many libraries and frameworks offering TypeScript definitions and support.

### Setting Up the Development Environment

To start using TypeScript, you'll need to set up your development environment. Follow these steps:

1. **Install Node.js and npm**: TypeScript requires Node.js and npm (Node Package Manager). Download and install them from the [official Node.js website](https://nodejs.org/).

2. **Install TypeScript**: Open your terminal or command prompt and run the following command to install TypeScript globally:

   ```bash
   npm install -g typescript
   ```

   This command installs the TypeScript compiler (`tsc`) globally, allowing you to compile TypeScript files from anywhere on your system.

3. **Verify the Installation**: Check if TypeScript is installed correctly by running:

   ```bash
   tsc --version
   ```

   You should see the installed TypeScript version number.

4. **Set Up a Code Editor**: Use a code editor like [Visual Studio Code](https://code.visualstudio.com/) that supports TypeScript. Visual Studio Code offers excellent TypeScript integration with features like IntelliSense and debugging.

5. **Create a TypeScript File**: Create a new file with a `.ts` extension, such as `hello.ts`, and write your TypeScript code.

6. **Compile TypeScript to JavaScript**: Use the TypeScript compiler to convert your TypeScript code into JavaScript. Run the following command in your terminal:

   ```bash
   tsc hello.ts
   ```

   This command generates a `hello.js` file that you can run in any JavaScript environment.

With your development environment set up, you're ready to start exploring the world of TypeScript!

[Next: 02-Getting-Started](./02-Getting-Started.md)