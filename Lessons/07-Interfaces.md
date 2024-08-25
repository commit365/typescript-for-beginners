## 7. Interfaces

Interfaces in TypeScript are used to define the structure of an object, providing a way to enforce specific properties and types. They are a powerful tool for ensuring consistency and type safety in your code.

### Defining and Implementing Interfaces

You can define an interface to specify the expected properties and their types for an object. Classes or objects can then implement this interface to ensure they adhere to the defined structure.

```typescript
interface User {
    username: string;
    email: string;
    age: number;
}

function getUserInfo(user: User): string {
    return `Username: ${user.username}, Email: ${user.email}, Age: ${user.age}`;
}

const user: User = {
    username: "johndoe",
    email: "john@example.com",
    age: 30
};

console.log(getUserInfo(user));
```

In this example, the `User` interface defines the structure for a user object. The `getUserInfo` function accepts a parameter of type `User`, ensuring that the object passed to it has the required properties.

### Optional Properties and Readonly Properties

1. **Optional Properties**: Use the `?` symbol to mark a property as optional. This means the property may or may not be present in the object.

   ```typescript
   interface Product {
       name: string;
       price: number;
       description?: string; // Optional property
   }

   const product: Product = {
       name: "Laptop",
       price: 999.99
       // description is optional
   };
   ```

   In this example, the `description` property in the `Product` interface is optional.

2. **Readonly Properties**: Use the `readonly` modifier to make a property immutable, meaning its value cannot be changed after initialization.

   ```typescript
   interface Car {
       readonly make: string;
       model: string;
   }

   const myCar: Car = {
       make: "Toyota",
       model: "Corolla"
   };

   // myCar.make = "Honda"; // Error: Cannot assign to 'make' because it is a read-only property.
   ```

   Here, the `make` property in the `Car` interface is readonly, preventing it from being modified.

### Extending Interfaces

Interfaces can be extended to create new interfaces with additional properties. This allows for code reuse and a more modular design.

```typescript
interface Animal {
    name: string;
    age: number;
}

interface Dog extends Animal {
    breed: string;
}

const myDog: Dog = {
    name: "Buddy",
    age: 3,
    breed: "Golden Retriever"
};

console.log(`Dog's Name: ${myDog.name}, Breed: ${myDog.breed}`);
```

In this example, the `Dog` interface extends the `Animal` interface, inheriting its properties and adding a new `breed` property. The `myDog` object must include all properties from both `Animal` and `Dog`.
