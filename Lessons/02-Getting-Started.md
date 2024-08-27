## 2. Getting Started

### Installing TypeScript

To begin using TypeScript, you need to install it on your machine. Follow these steps:

1. **Ensure Node.js and npm are Installed**: TypeScript requires Node.js and npm. If you haven't installed them yet, download and install them from the [official Node.js website](https://nodejs.org/).

2. **Install TypeScript Globally**: Open your terminal or command prompt and run the following command to install TypeScript globally:

   ```bash
   npm install -g typescript
   ```

   This command installs the TypeScript compiler (`tsc`) globally, allowing you to compile TypeScript files from any location on your system.

3. **Verify the Installation**: Check if TypeScript is installed correctly by running:

   ```bash
   tsc --version
   ```

   You should see the installed TypeScript version number, confirming the installation was successful.

### Understanding the TypeScript Compiler

The TypeScript compiler (`tsc`) is a command-line tool that compiles TypeScript code into JavaScript. Here's how it works:

- **Input**: You write your code in TypeScript files with a `.ts` extension.
- **Compilation**: The `tsc` command compiles the TypeScript files into JavaScript files with a `.js` extension.
- **Output**: The resulting JavaScript files can be executed in any JavaScript environment, such as a web browser or Node.js.

The TypeScript compiler also performs type checking during the compilation process, helping you catch errors early.

### Your First TypeScript Program

Let's create and run a simple TypeScript program:

1. **Create a New TypeScript File**: Open your code editor and create a new file named `hello.ts`.

2. **Write TypeScript Code**: Add the following code to `hello.ts`:

   ```typescript
   function greet(name: string): string {
       return `Hello, ${name}!`;
   }

   console.log(greet("World"));
   ```

   This code defines a function `greet` that takes a string parameter and returns a greeting message.

3. **Compile the TypeScript File**: Open your terminal, navigate to the directory containing `hello.ts`, and run:

   ```bash
   tsc hello.ts
   ```

   This command compiles `hello.ts` into a JavaScript file named `hello.js`.

4. **Run the JavaScript File**: Execute the compiled JavaScript file using Node.js:

   ```bash
   node hello.js
   ```

   You should see the output: `Hello, World!`

Congratulations! You've written, compiled, and executed your first TypeScript program. You're now ready to explore more features and capabilities of TypeScript.

[Next: 03-Primitive-Types](./03-Primitive-Types.md)