Title: The core difference between type and interface
Introduction:
In typescript, both type and interface are used to define the structure of data improve type safety. Although they are used in similar purposes most often, they have some important differences.
The differences can be disscussed in almost 4 aspects.

1. Defining Object Structure.

interface User {
    name: string;
    age: number;
}

type UserType = {
    name: string;
    age: number;
}

** Here both approaches provide type checking and ensure that objects follow the defined structure. But need to see notice that while defining an intercace we don't use any '=' sign abd while defining type we use '=' sign.

2. flexibility
A type alias can represent unions, tuples, primitives, and object types, while an interface primarily describes object structures.

type ID = string | number;
type Coordinate = [number, number];

** For this reason type is particularly useful when working with complex type combination.

3. Extending types

interface Person {
    name: string;
}

interface Employee extends Person {
    salary: number;
}

type Admin = Person & {
    role: string;
};

** Interfaces use extends for inheritance, while type aliases commonly use intersections (&) to combine types.


4. Declaration Merging.
interface Student {
    name: string;
}

interface Student {
    age: number;
}
** TypeScript combines these declarations into a single interface containing both properties.

Conclusion:
We should choose interface when we need to define object structures, especially when inheritance and declaration merging is useful. On the other hand, we should use type when we are working with unions, tuples, primitives, or advanced type combinations.