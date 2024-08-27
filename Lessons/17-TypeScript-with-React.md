## 17. TypeScript with React

Integrating TypeScript with React enhances your development experience by providing strong type-checking and improved code readability. This lesson will guide you through setting up a React project with TypeScript and using TypeScript to define props and state.

### Integrating TypeScript in a React Project

1. **Create a React App with TypeScript**: Use Create React App to set up a new React project with TypeScript support.

   ```bash
   npx create-react-app my-app --template typescript
   ```

   This command initializes a new React project named `my-app` with TypeScript configured.

2. **Project Structure**: The project structure will include `.tsx` files for components, which allow you to write JSX with TypeScript.

3. **Install Type Definitions**: If you need additional type definitions for libraries, you can install them using npm. For example, for React Router:

   ```bash
   npm install @types/react-router-dom
   ```

### Props and State with TypeScript

1. **Defining Props**: Use TypeScript interfaces or types to define the expected props for your components.

   ```typescript
   import React from 'react';

   interface GreetingProps {
       name: string;
       age?: number; // Optional prop
   }

   const Greeting: React.FC<GreetingProps> = ({ name, age }) => (
       <div>
           <h1>Hello, {name}!</h1>
           {age && <p>Age: {age}</p>}
       </div>
   );

   export default Greeting;
   ```

   In this example, `GreetingProps` defines the props for the `Greeting` component. The `age` prop is optional, as indicated by the `?`.

2. **Using State**: Use the `useState` hook with TypeScript to manage component state.

   ```typescript
   import React, { useState } from 'react';

   const Counter: React.FC = () => {
       const [count, setCount] = useState<number>(0);

       return (
           <div>
               <p>Count: {count}</p>
               <button onClick={() => setCount(count + 1)}>Increment</button>
           </div>
       );
   };

   export default Counter;
   ```

   Here, the `useState` hook is used to manage a `count` state of type `number`.

3. **Complex State and Props**: For more complex state or props, use interfaces to define their structure.

   ```typescript
   interface Todo {
       id: number;
       text: string;
       completed: boolean;
   }

   const TodoList: React.FC<{ todos: Todo[] }> = ({ todos }) => (
       <ul>
           {todos.map(todo => (
               <li key={todo.id}>
                   {todo.text} {todo.completed ? "✓" : "✗"}
               </li>
           ))}
       </ul>
   );
   ```

   In this example, the `TodoList` component receives an array of `Todo` objects as props, with each `Todo` having an `id`, `text`, and `completed` status.

Using TypeScript with React helps catch errors at compile time, provides better documentation through types, and improves the overall robustness of your application.

[Next: 18-TypeScript-with-Node.js](./18-TypeScript-with-Node.js.md)