# The Notorious  `this`  keyword

---

### Ways to invoke functions in JS

* function invocation: `alert('Hello World!')`
* method invocation: `console.log('Hello World!')`
* constructor invocation: `new ClassName()`
* indirect invocation: `alert.call(undefined, 'Hello World')`

---

### Function Invocation

```js
function hello(name) {  
  return 'Hello ' + name + '!';
}
// Function invocation
var message = hello('World');  
console.log(message); // => 'Hello World!'  
```

`hello('World)` is the function invocation

---

### `this` in function invocation

`this` is the `window` object in a function invocation

```js
function inspectContext() {
  console.assert(this === window)
  this.foo = 'foo'
}

inspectContext()
console.log(window.foo) // 'foo'
```

---

### Function invocation in strict mode

`this` is `undefined` in a function invocation happens in strict mode

```js
function inspectContext() {
  'use strict'
  console.assert(this === undefined)
  this.foo = 'foo'
}

inspectContext()
`Uncaught TypeError: Cannot set property 'foo' of undefined`
```

---

### Method invocation

```js
var myObject = {  
  // helloFunction is a method
  helloFunction: function() {
    return 'Hello World!';
  }
};
myObject.helloFunction();  // this is the method invocation
```

---

### `this` in method invocation

```js
let obj = {
  method: function() {
    console.assert(this === obj)
  }
}

obj.method()
```

---

Pitfall: `this` in an inner function

```js
let obj = {
  method: function() {
    console.assert(this === obj)
    function inner () {
      console.assert(this !== obj)
    }
    inner()
  }
}

obj.method()
```

---
