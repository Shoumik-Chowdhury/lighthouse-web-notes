# Class
## A lesson on how to code with class (get it!)

***What is a class?*** In OOP, classes are blueprints (templates) that we use to create instances of objects. A class describes what the object is going to be and we can create new objects using the class.

### How to declare a class?
```js
class Pizza {

}
```
### Create a new Object from a class
```js
let pizza1 = new Pizza();
let pizza2 = new Pizza();
```
### To add a method and property to a class
```js
class SomeClass {
  methodName(parameters) {
    // this is a method
  }

  someMethod() {
    this.hello = "hi"; // Created a property called hello
  }
}
```
### What is a constructor and how to add one
***Constructor*** is a special kind of method that gets executed when an object instance is created from a class.

The constructor method is the best place to setup any default property values for an object. Since it's a method, we can also pass in values to the constructor method.
```js
class SomeClass {
  constructor(parameter1) {
    this.someKey = someValue;
    this.someKey2 = parameter1;
  }
}
```
Example:
```js
class Pizza {
  // A constructer that sets two default values, one of them takes the parameter value.
  constructor(size) {
    this.toppings = ["cheese"];
    this.size = size;
  }
  // A property that sets a new key (crust) and a value (soft).
  softCrust() {
    this.crust = 'soft';
  }
  // A method that adds new toppings.
  addTopping(topping) {
    this.toppings.push(topping);
  }

}

let pizza1 = new Pizza('large');

pizza1.addTopping('pineapple');
pizza1.softCrust();

console.log(inspect(pizza1));
/*
Pizza {
  toppings: [ 'cheese', 'pineapple' ],
  size: 'large',
  crust: 'soft'
}
*/
```

**Since a class is just a blueprint for creating objects, methods like `addTopping` will exist on the instances created from the class, but not on the class itself.*

## Javascript and other OO language
We saw an example of this with the `Todo List` app exercise. Reflect back on the code there. We created a **function** called newTask which would return a `new task` object each time it was called.

In this activity, we wrote code that lets us create new pizza objects using the class-based syntax. It allowed us to call `new Pizza()`. Upon reflection, you will see that it does the same thing but in a different way.

So with classes, the original goals of using objects are still the focus. The syntax is what seems different.

In class-based languages that are more strict (Ruby, Java, etc.), we are only able to use classes to solve this issue. In JavaScript we have both options.
