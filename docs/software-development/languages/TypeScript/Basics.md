# TypeScript Basics

> [!INFO]
> Free and open-source [TypeScript book](https://github.com/basarat/typescript-book)

Install with `npm i -g typescript`

Compile with `tsc <filename>.ts`

Create config `tsconfig.json`

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

  `let text:string = 'TypeScript'`
  `let num:any = 15`

2. Custom Types

```js
type Style = 'bold' | 'italic';
let font: Style;
```

3. Strong Typing Objects (interface)

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

4. Functions

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

5. Arrays

```js
const arr: number[] = [];
```

6. TypeScript Tuples
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

7. Generics

Use type internally inside a function or class

```js
class Observable<T>{
   constructor(public value: T){}
}

let x: Observable<number>;
let y: Observable<Person>;
let z = new Observable(23); // Here, the type is implicitly `number`


```
