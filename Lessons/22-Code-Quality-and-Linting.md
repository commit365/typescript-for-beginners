## 22. Code Quality and Linting

Maintaining code quality is essential for building reliable and maintainable applications. This lesson will guide you through setting up ESLint with TypeScript and using Prettier for code formatting.

### Setting up ESLint with TypeScript

ESLint is a popular linting tool that helps identify and fix problems in your JavaScript and TypeScript code. Here's how to set it up in your TypeScript project:

1. **Install ESLint and TypeScript ESLint Parser**: Add ESLint and the necessary TypeScript packages as development dependencies.

   ```bash
   npm install eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev
   ```

2. **Initialize ESLint**: Create an ESLint configuration file by running the following command and following the prompts.

   ```bash
   npx eslint --init
   ```

   Choose the following options:
   - How would you like to use ESLint? (To check syntax, find problems, and enforce code style)
   - What type of modules does your project use? (CommonJS or ES Modules)
   - Which framework does your project use? (None or your preferred framework)
   - Does your project use TypeScript? (Yes)
   - Where does your code run? (Node, Browser, or both)
   - What format do you want your config file to be in? (JavaScript, YAML, or JSON)

3. **Configure ESLint for TypeScript**: Update your `.eslintrc.js` (or equivalent) configuration file to include the TypeScript parser and plugin.

   ```javascript
   module.exports = {
       parser: '@typescript-eslint/parser',
       parserOptions: {
           ecmaVersion: 2020,
           sourceType: 'module',
       },
       extends: [
           'eslint:recommended',
           'plugin:@typescript-eslint/recommended',
       ],
       rules: {
           // Customize your rules here
       },
   };
   ```

4. **Run ESLint**: You can now run ESLint on your TypeScript files.

   ```bash
   npx eslint 'src/**/*.{ts,tsx}'
   ```

   This command will lint all TypeScript files in the `src` directory.

### Code Formatting with Prettier

Prettier is an opinionated code formatter that helps maintain consistent code style across your project. Here's how to set it up:

1. **Install Prettier**: Add Prettier as a development dependency.

   ```bash
   npm install prettier --save-dev
   ```

2. **Create a Prettier Configuration File**: Create a `.prettierrc` file in your project root to customize your formatting options.

   ```json
   {
       "semi": true,
       "singleQuote": true,
       "tabWidth": 4,
       "trailingComma": "all"
   }
   ```

   You can adjust these options based on your preferred coding style.

3. **Ignore Files**: Create a `.prettierignore` file to specify files and directories that Prettier should ignore.

   ```
   node_modules
   dist
   ```

4. **Format Your Code**: You can format your code using Prettier by running the following command:

   ```bash
   npx prettier --write 'src/**/*.{ts,tsx}'
   ```

5. **Integrate ESLint and Prettier**: To avoid conflicts between ESLint and Prettier, you can install additional packages to integrate them.

   ```bash
   npm install eslint-config-prettier eslint-plugin-prettier --save-dev
   ```

   Update your ESLint configuration to include Prettier:

   ```javascript
   extends: [
       'eslint:recommended',
       'plugin:@typescript-eslint/recommended',
       'plugin:prettier/recommended', // Add this line
   ],
   ```

### Conclusion

By setting up ESLint and Prettier in your TypeScript project, you can ensure high code quality and maintain consistent code formatting. This will help improve collaboration among team members and reduce the likelihood of bugs and style inconsistencies.

[Next: 23-Conclusion-and-Next-Steps](./23-Conclusion-and-Next-Steps.md)