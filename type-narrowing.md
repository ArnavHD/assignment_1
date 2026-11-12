Title: Type narrowing in Typescript and understanding the typeof, instanceof and in operator.
Introduction:
Narrowing down helps developers to work with different data types safely. It allows TypeScript to determine a more specific type of a variable based on certain conditions. This is usually useful when working with union types, where a variable can hold more than one type.

1. Type Narrowing Using typeof

const processValue = (value: string | number): void => {
    if (typeof value === "string") {
        console.log(value.toUpperCase());
    } else {
        console.log(value * 2);
    }
};

processValue("hello"); // HELLO
processValue(10);      // 20

** The typeof operator checks the type of a value at runtime. It is commonly used to distinguish between primitive types such as strings, numbers, and booleans.
** In the example Typescript understands that the value in the if block is string and number in the else block.

2. Type Narrowing Using instanceof
class Dog {
    bark() {
        return "Woof!";
    }
}

class Cat {
    meow() {
        return "Meow!";
    }
}

const makeSound = (animal: Dog | Cat): string => {
    if (animal instanceof Dog) {
        return animal.bark();
    }

    return animal.meow();
};

** The instanceof operator checks whether an object is an instance of a particular class or constructor.
** I helps to access class specific methods without causing type errors.

3. Type Narrowing Using the in Operator
interface Admin {
    name: string;
    permissions: string[];
}

interface User {
    name: string;
    email: string;
}

const getRole = (person: Admin | User): string => {
    if ("permissions" in person) {
        return "Admin";
    }

    return "User";
};

** The in operator checks whether a property exists in an object or its prototype chain.

Conclusion:
Type narrowing makes TypeScript code safer, more readable, and easier to maintain. We use typeof for primitive values, instanceof for class instances, and in to check object properties.
