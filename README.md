# JavaScript

---

## Diferencias arrow functions y regular functions

```javascript
// Regular function
function sayHello(name) {
  return `Hello ${name}`;
}
```

```javascript
// Arrow function
const sayHello = (name) => {
  return `Hello ${name}`;
};
```

Puedes llamar a una `regular function` antes de que sea declarada gracias al hoisting

```javascript
sayHello("aerozfx"); // Se puede llamar a pesar de no estar declarada.

function sayHello(name) {
  return `Hello ${name}`;
}
```

Por el contrario, si hacemos lo mismo con una `arrow function` nos dará `ReferenceError`

```javascript
sayHello("aerozfx"); // ReferenceError: Cannot access 'sayHello' before initialization

const sayHello = (name) => {
  return `Hello ${name}`;
};
```

Las `arrow function` tiene un `return` implícito, por lo que no necesitan la palabra `return`

```javascript
const sayHello = (name) => `Hello ${name}`;

sayHello("aerozfx");
```

Sin embargo, si nuestra `arrow function` tiene más de una línea, debemos usar `{}` y entonces si es necesario la palabra `return`

```javascript
const sayHello = (name) => {
  let text = "Nice to meet you!";
  return `Hello ${name}. ${text}`;
};

sayHello("aerozfx");
```

Las `regular functions` pueden acceder al objeto `arguments`, mientras que las `arrow functions` no.

```javascript
function sayHello(name) {
  console.log(arguments[0]); // "aerozfx"
  console.log(arguments); // {"0": "aerozfx"}
  let text = "Nice to meet you!";
  return `Hello ${name}. ${text}`;
}

sayHello("aerozfx");
```
