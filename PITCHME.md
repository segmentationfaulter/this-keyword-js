# The Notorious `this` keyword

---

# Function Invocation Types

* function invocation `alert('Hello World!')`
* method invocation `console.log('Hello World!')`
* constructor invocation `new ClassName()`
* indirect invocation `alert.call(undefined, 'Hello World')`

Each invocation type defines the context in its own way, so `this` behaves differently with each type of the invocation
