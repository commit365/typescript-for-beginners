## 5. Union and Intersection Types

TypeScript provides union and intersection types to create more flexible and powerful type definitions. Understanding these types can help you write more expressive and type-safe code.

### Understanding Union Types

Union types allow a variable to hold values of multiple types. You can define a union type using the pipe (`|`) symbol.

```typescript
let identifier: number | string;

identifier = 101;      // Valid
identifier = "A101";   // Valid
// identifier = true;  // Error: Type 'boolean' is not assignable to type 'number | string'.

function printId(id: number | string) {
    console.log(`ID: ${id}`);
}

printId(123);          // Valid
printId("ABC123");     // Valid
```

In this example, `identifier` can be either a `number` or a `string`. The `printId` function accepts an argument that can be a `number` or a `string`, allowing for more flexible input handling.

### Using Intersection Types

Intersection types allow you to combine multiple types into one. A value of an intersection type must satisfy all the combined types. You can define an intersection type using the ampersand (`&`) symbol.

```typescript
interface Person {
    name: string;
    age: number;
}

interface Employee {
    employeeId: number;
    department: string;
}

type StaffMember = Person & Employee;

let staff: StaffMember = {
    name: "John Doe",
    age: 30,
    employeeId: 12345,
    department: "Engineering"
};

function getStaffDetails(staff: StaffMember) {
    console.log(`Name: ${staff.name}, Age: ${staff.age}`);
    console.log(`Employee ID: ${staff.employeeId}, Department: ${staff.department}`);
}

getStaffDetails(staff);
```

In this example, `StaffMember` is an intersection type that combines `Person` and `Employee`. A `StaffMember` must have all properties from both `Person` and `Employee` interfaces. The `getStaffDetails` function demonstrates how to work with an intersection type.
