## 20. TypeScript in Build Systems

Integrating TypeScript into your build system allows you to take advantage of modern JavaScript features and optimizations. This lesson will guide you through using TypeScript with Webpack and integrating TypeScript with Babel.

### Using TypeScript with Webpack

Webpack is a popular module bundler that can be configured to work with TypeScript, allowing you to bundle your TypeScript code for deployment.

1. **Install Webpack and TypeScript Loader**: Add Webpack, Webpack CLI, and the TypeScript loader to your project.

   ```bash
   npm install webpack webpack-cli ts-loader --save-dev
   ```

2. **Create a Webpack Configuration File**: Create a `webpack.config.js` file in your project root.

   ```javascript
   const path = require('path');

   module.exports = {
       entry: './src/index.ts',
       module: {
           rules: [
               {
                   test: /\.tsx?$/,
                   use: 'ts-loader',
                   exclude: /node_modules/,
               },
           ],
       },
       resolve: {
           extensions: ['.tsx', '.ts', '.js'],
       },
       output: {
           filename: 'bundle.js',
           path: path.resolve(__dirname, 'dist'),
       },
   };
   ```

   This configuration tells Webpack to use `ts-loader` for `.ts` and `.tsx` files and outputs the bundled code to `dist/bundle.js`.

3. **Update `package.json`**: Add a build script to your `package.json`.

   ```json
   "scripts": {
       "build": "webpack"
   }
   ```

4. **Run the Build**: Use the build script to bundle your TypeScript code.

   ```bash
   npm run build
   ```

   Webpack will compile your TypeScript files and output the bundled JavaScript file.

### Integrating TypeScript with Babel

Babel is a JavaScript compiler that can be used alongside TypeScript to transform modern JavaScript features into a format compatible with older environments.

1. **Install Babel and TypeScript Preset**: Add Babel, Babel CLI, and the TypeScript preset to your project.

   ```bash
   npm install @babel/core @babel/cli @babel/preset-env @babel/preset-typescript --save-dev
   ```

2. **Create a Babel Configuration File**: Create a `.babelrc` file in your project root.

   ```json
   {
       "presets": ["@babel/preset-env", "@babel/preset-typescript"]
   }
   ```

   This configuration tells Babel to use the TypeScript preset along with the preset for modern JavaScript features.

3. **Update `package.json`**: Add a build script to your `package.json`.

   ```json
   "scripts": {
       "build": "babel src --out-dir dist --extensions \".ts,.tsx\""
   }
   ```

4. **Run the Build**: Use the build script to compile your TypeScript code.

   ```bash
   npm run build
   ```

   Babel will compile your TypeScript files and output the JavaScript files to the `dist` directory.

Using TypeScript with Webpack and Babel allows you to leverage modern JavaScript features, optimize your code for production, and ensure compatibility with various environments.

[Next: 21-Best-Practices](./21-Best-Practics.md)