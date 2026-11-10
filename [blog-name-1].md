# How TypeScript code operates during compilation (tsc)?

## Introduction

TypeScript is a strongly-typed programming language that is based on JavaScript; however, the challenge here is that browsers cannot run TypeScript but only JavaScript. In this regard, the TypeScript Compiler (tsc) will help to translate .ts code into executable JavaScript.

## Detailed Body

<b>1. TypeScript Compilation Process </b>

Once executing the command:

```
  tsc
```

The TypeScript compiler will follow these steps:

1. Converts the typescript code into the internal representation.
2. Checks whether the program satisfies all the rules, including types of variables, function parameters, types of return values and so on.
3. Removes TypeScript-specific functionality like type annotations and interfaces.
4. Creates the JavaScript code.

For example:

In TypeScript,

```ts
interface Bottle {
    brand: string;
    country: string;
}

const message = (bottle: Bottle): string => {
    return `This is, ${bottle.brand} and imported from  ${bottle.country}`;
};
```

After compiling, the code will look as follows:

```js
const message = (bottle) => {
    return `This is, ${bottle.brand} and imported from ${bottle.country}`;
};
```

<b>2. What is tsconfig.json? </b>

It is the core of any TypeScript project. It is a configuration file and specifies compiler-options, sourcefiles which are required to compile the TS code into JS.

Configuration file can be generated using:

```
  tsc --init
```

Basic Structure:

```ts
  {
    "compilerOptions": {
      "target": "ES6",
      "module": "CommonJS",
      "strict": true
    },
    "include": ["src/**/*.ts"]
  }
```

Key Compiler Options:

# Working mechanism of TypeScript Code during compilation (tsc) and role of tsconfig.json?

## Introduction

TypeScript is a strongly typed programming language which is built on JavaScript but the problem is that browsers execute JavaScript not TypeScript. This is where the TypeScript Compiler or transform the .ts code into runnable JavaScript.

## Detailed Body

<b>1. How TypeScript Compilation Works </b>

After running the following command:

```
  tsc
```

The compiler of Typescript performs the following steps:

1. After reading the typescript code it converts into internal syntax structure.
2. Here it checks different rules such as variable types, function parameters, return values, other type-related.
3. Here the TypeScript-specific features are removed, such as type annotations and interfaces.
4. At last JavaScript code is produced which can runs in JavaScript environment.

For example:

In TypeScript,

```ts
interface Bottle {
    brand: string;
    country: string;
}

const message = (bottle: Bottle): string => {
    return `This is, ${bottle.brand} and imported from  ${bottle.country}`;
};
```

After compiling, the JavaScript looks like:

```js
const message = (bottle) => {
    return `This is, ${bottle.brand} and imported from ${bottle.country}`;
};
```

<b>2. What is tsconfig.json? </b>

It is the heart of any TypeScript project. It is a configuration file and defines compiler options, source files that are needed for compiling the TS code to JS.

The configuration file can be created using:

```
  tsc --init
```

Basic Structure:

```ts
  {
    "compilerOptions": {
      "target": "ES6",
      "module": "CommonJS",
      "strict": true
    },
    "include": ["src/**/*.ts"]
  }
```

Key tsconfig.json Compiler Options:

| Option   | What it does                                          |
| -------- | ----------------------------------------------------- |
| `target` | Sets the ECMAScript version of the emitted JavaScript |
| `module` | Sets the module system used in the emitted code       |
| `strict` | Turns on the full set of strict type-checking flags   |
| `outDir` | Sets the folder where compiled files are written      |

```
  tsc
```

## Conclusion

The tsc compiler performs the conversion from TS to JS using techniques like parsing, type-checking, transformations, and code generation. And tsconfig.json is used to control the entire process of compilation.
