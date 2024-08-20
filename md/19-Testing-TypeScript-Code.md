## 19. Testing TypeScript Code

Testing is a crucial part of software development, ensuring that your code behaves as expected. This lesson will guide you through setting up testing tools for a TypeScript project and writing tests for your TypeScript code.

### Setting up Testing Tools

1. **Choose a Testing Framework**: Popular testing frameworks for TypeScript include Jest and Mocha. Here, we'll use Jest as an example.

2. **Install Jest and TypeScript Support**: Add Jest, its type definitions, and `ts-jest` to your project.

   ```bash
   npm install jest @types/jest ts-jest --save-dev
   ```

3. **Initialize Jest**: Create a Jest configuration file using `ts-jest`.

   ```bash
   npx ts-jest config:init
   ```

   This generates a `jest.config.js` file configured to work with TypeScript.

4. **Update `package.json`**: Add a test script to your `package.json`.

   ```json
   "scripts": {
       "test": "jest"
   }
   ```

### Writing Tests for TypeScript Code

1. **Create a Function to Test**: Write a simple TypeScript function in the `src` directory.

   ```typescript
   // src/calculator.ts
   export function add(a: number, b: number): number {
       return a + b;
   }
   ```

2. **Write a Test for the Function**: Create a test file in the `src` directory with the `.test.ts` extension.

   ```typescript
   // src/calculator.test.ts
   import { add } from './calculator';

   test('adds two numbers', () => {
       expect(add(1, 2)).toBe(3);
       expect(add(-1, 1)).toBe(0);
   });
   ```

   In this example, the `add` function is tested to ensure it correctly sums two numbers.

3. **Run the Tests**: Use the test script to run your tests.

   ```bash
   npm test
   ```

   Jest will execute the tests and output the results, indicating whether they passed or failed.

4. **Test Coverage**: Jest can also generate a test coverage report. Update your test script to include coverage:

   ```json
   "scripts": {
       "test": "jest --coverage"
   }
   ```

   Run the tests again to see the coverage report.

   ```bash
   npm test
   ```

   The coverage report provides insights into which parts of your code are tested and which are not.

Using testing tools with TypeScript helps ensure that your code is reliable and behaves as expected. It also provides confidence when making changes or adding new features.
