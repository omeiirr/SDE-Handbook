# TypeScript Basics

> [!INFO]
> Free and open-source [TypeScript book](https://github.com/basarat/typescript-book)

Install with `npm i -g typescript`

Compile with `tsc <filename>.ts`

Create config `tsconfig.json` with `tsc --init` (gives documented config)

Compile all files in directory with `tsc`

Auto compile on save with `tsc --watch`

### Important compile options

```js
"compilerOptions:" {
    // Flavour of JavaScript to compile to
    "target": "esnext",
    // Recompile on every save
    "watch": true
}
```

1. Strong Typing

   - Implicit

     `let num = 10` will set type as `number`

   - Explicit

     `let text: string = 'TypeScript'`
     `let num: any = 15`

1. Custom Types

   ```js
   type Style = 'bold' | 'italic';
   let font: Style;
   ```

1. Strong Typing (Object and Interface)

   #### Object

   ```js
   type User = {
     id: number,
     name: string,
   };

   const user1: User = {
     id: 1,
     name: 'Carl',
   };
   ```

   #### Interface

   ```js
   interface Person {
     // Mandatory properties
     first: string;
     last: string;
     // Optional properties
     [key: string]: any;
   }

   const person1: Person = {
     first: 'Omeir',
     last: 'Fawaz',
   };

   const person2: Person = {
     first: 'Linus',
     last: 'Torvalds',
     smart: true,
   };
   ```

   #### Difference between custom type and interface

   - No equal sign for interface `interface Person { }` `type User = { }`
   - Type can be used with primitives and unions, but interface cannot be used

     ```js
     type Point  = number | string
     const p1: Point = 1; // Valid

     interface Point  = number | string; // Invalid
     const p1: Point = 1;
     ```

1. Type Assertion

   ```js
   let id: any = 1;
   // We want customerId to be a specific type. There are two ways:

   // Option 1
   let customerId = <number>id
   customerId = '2'; // Will give error

   // Option 2
   let customerId = cid as number

   ```

1. Functions

   ```js
   function exponent(a: number, b: number) {
     return Math.pow(a, b);
   }
   ```

   We can specify return type as:

   ```js
   function exponent(a: number, b: number): string {
     return Math.pow(a, b).toString();
   }
   ```

   For functions (like event listeners or side effects) that don't return any value:

   ```js
   function func(a: number, b: number): void
   ```

   ```js
   function greet(message: string | number): void {
     console.log(message);
   }

   greet('Hello!'); // Valid
   greet(2); // Valid
   greet(true); // Invalid
   ```

1. Arrays

   ```js
   const arr: number[] = [];
   ```

1. TypeScript Tuples
   A fixed-length array where each item has its own type

   ```js
   type MyList = [number, string, boolean];
   const arr: MyList = [12, 'abc', true];
   ```

> [!TIP]
> Optional values (using `?`).
>
> ```js
> type MyList = [number?, string?, boolean?];
> ```
>
> Can also be used with function arguments

> [!TIP]
> Read-only values (using `readonly`)
>
> ```js
> interface User {
>  readonly id: number
>  name: string
> }
>
> const user1: User = {
>  id: 1,
>  name: 'John'
> }
>
> user1.id = 3; // Invalid
> ```

8. Tuple Array

   ```js
   let employee: [number, string][] = [
     [1, 'A'],
     [2, 'B'],
     [3, 'C'],
   ];
   ```

9. Unions

   To store multiple data types in a variable

   ```js
   let id: number | string = 22;
   id = 'A244'; // Valid
   ```

10. Enums

    Define a set of named constants (either numeric or string)

    #### Numeric

    ```js
    enum Direction1 = { Up, Down, Left, Right } // By default, values are 0, 1, 2, 3 resp.
    console.log(Direction1.Up); // 0
    console.log(Direction1.Left); // 2
    ```

    We can change the numbering

    ```js
    enum Direction1 = {
      Up = 2,
      Down,
      Left,
      Right
    }
    console.log(Direction1.Up); // 2
    console.log(Direction1.Left); // 4
    ```

    #### String

    ```js
    enum Direction2 ={
      Up = 'A',
      Down = 'B',
      Left = 'C',
      Right = 'D'
    }
    console.log(Direction2.Up); // A
    console.log(Direction2.Left); // C
    ```

11. Generics

    Use type internally inside a function or class

    ```js
    class Observable<T>{
      constructor(public value: T){}
    }

    let x: Observable<number>;
    let y: Observable<Person>;
    let z = new Observable(23); // Here, the type is implicitly `number`
    ```

    Example

    ```
    function getArray<T>(items: T[]): T[] {
      return new Array().concat(items);
    }

    let numArray = getArray<number>[1, 2, 3, 4];
    let strArray = getArray<string>['A', 'B', 'C'];

    numArray.push('D') // Invalid
    strArray.push(5) // Invalid
    ```
