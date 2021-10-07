# Functions and Interfaces

1. Interface with Functions

   ```js
   interface MathFunction {
     (x: number, y: number): number;
   }

   const add: MathFunction = (x: number, y: number): number => x + y;
   const sub: MathFunction = (x: number, y: number): number => x - y;
   ```

1. Classes

   ```js
   class Person {
   id: number
   name: string

   constructor(id: number, name: stirng) {
       this.id = id // 'this' refers to the class we are currently in
       this.name = name
   }

   const p1 = new Person(1, "Tom Scott")
   const p2 = new Person(2, "Mike Pound")
   }
   ```

1. Classes with Interface

   ```js
   interface PersonInterface {
       id: number
       name: string
       register(): string // This function must return a string
   }

   class Person implements PersonInterface{
    private id: number // Can only be accessed by this class
    protected name: string // Can only be accessed by classes extended from this class
    public favFood: string // Here, 'public' is redundant

    register(){
        return 1; // Invalid
    }

    register(){
        return `${this.name} registered successfully`
    }
   }
   ```

1. Extending Classes

   ```js
   // Sub-class
   class Employee extends Person {
     position: string;

     constructor(id: number, name: string, position: string) {
       super(id, name);
       this.position = position;
     }
   }

   const emp1 = new Employee(3, 'Shawn', 'Dev');
   console.log(emp.register()); // Shawn registered successfully
   ```
