## 18. TypeScript with Node.js

Integrating TypeScript with Node.js allows you to leverage TypeScript's static typing and other features in server-side applications. This lesson will guide you through setting up a Node.js project with TypeScript and using TypeScript with the Express framework.

### Setting up a Node.js Project with TypeScript

1. **Initialize a New Node.js Project**: Start by creating a new directory for your project and initializing it with npm.

   ```bash
   mkdir my-node-app
   cd my-node-app
   npm init -y
   ```

   This creates a `package.json` file with default settings.

2. **Install TypeScript**: Add TypeScript and the necessary type definitions as development dependencies.

   ```bash
   npm install typescript @types/node --save-dev
   ```

3. **Initialize TypeScript**: Create a `tsconfig.json` file to configure TypeScript.

   ```bash
   npx tsc --init
   ```

   This generates a `tsconfig.json` file with default configurations. You can customize it as needed.

4. **Create Source and Build Directories**: Organize your project by creating `src` and `dist` directories.

   ```bash
   mkdir src
   ```

5. **Write Your First TypeScript File**: Create an `index.ts` file in the `src` directory.

   ```typescript
   // src/index.ts
   const greet = (name: string): string => {
       return `Hello, ${name}!`;
   };

   console.log(greet("World"));
   ```

6. **Compile and Run**: Compile your TypeScript code and run the resulting JavaScript.

   ```bash
   npx tsc
   node dist/index.js
   ```

   The `tsc` command compiles TypeScript files in the `src` directory and outputs JavaScript files in the `dist` directory.

### Using TypeScript with Express

1. **Install Express and Type Definitions**: Add Express and its type definitions to your project.

   ```bash
   npm install express
   npm install @types/express --save-dev
   ```

2. **Create an Express Server**: Set up a basic Express server using TypeScript.

   ```typescript
   // src/server.ts
   import express, { Request, Response } from 'express';

   const app = express();
   const PORT = process.env.PORT || 3000;

   app.get('/', (req: Request, res: Response) => {
       res.send('Hello, Express with TypeScript!');
   });

   app.listen(PORT, () => {
       console.log(`Server is running on http://localhost:${PORT}`);
   });
   ```

3. **Compile and Run the Server**: Compile your TypeScript code and start the server.

   ```bash
   npx tsc
   node dist/server.js
   ```

   Your Express server should now be running, and you can visit `http://localhost:3000` to see the response.

Using TypeScript with Node.js and Express enhances your development process by providing type safety, better code organization, and improved maintainability.

[Next: 19-Testing-TypeScript-Code](./19-Testing-TypeScript-Code.md)