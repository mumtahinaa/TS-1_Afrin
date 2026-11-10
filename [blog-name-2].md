# Access Modifiers in TypeScript OOP

## Introduction

The access modifiers in TypeScript are used to control access to members of classes such as properties and methods. The access modifier are responsible for implementing encapsulation since they control the access to the class members both from the outside of the class and its subclasses. They help to implement encapsulation, provide code security and structure the object oriented programs. TypeScript provides 4 main modifiers: public, private, protected and readonly.

## Detailed Body

<b>1. Public </b>
Public modifier allow accessing the properties and methods from any place. In TypeScript, it is the default access modifier.

```ts
class Student {
    public name: string = "John";

    public displayName(): void {
        console.log(this.name);
    }
}

const student = new Student();
console.log(student.name);
student.displayName();
```

<b>2. Private </b>

Access to the class where a property or function is declared is restricted by the private modifier. It is not possible to access it from outside of this class.

```ts
class BankAccount {
    private balance: number = 5000;

    public showBalance(): void {
        console.log(this.balance);
    }
}
```

<b>3. Protected</b>
The protected modifier allows access to the declaring class and its subclasses but not from the outside

```ts
class Animal {
    protected sound: string = "Bark";
}

class Dog extends Animal {
    makeSound(): void {
        console.log(this.sound);
    }
}
```

<b>4. Readonly</b>
The property can only be assigned either inside the constructor or at the time of declaration due to readonly modifier. It cannot be changed afterwards.

```ts
class Employee {
    readonly id: number;

    constructor(id: number) {
        this.id = id;
    }
}

const employee = new Employee(101);
console.log(employee.id);
```

## Conclusion

In order to write safe and maintainable applications in TypeScript, one has to use access modifiers. public is used for accessing everywhere, private is used for accessing within the class in which it was declared, protected is used for supporting inheritance, readonly is used to avoid reassigning.
