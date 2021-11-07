# Getter & Setter
Getters and setters are special methods that are used to get the value of a property or set the value of a property.
Lets start with an example:

Traditionally we would write a method like this:
```js
class Pizza {
  //...
  // getPrice includes price calculation
  getPrice() {
    const basePrice = 10;
    const toppingPrice = 2;
    return basePrice + (this.toppings.length * toppingPrice);
  }

  // setSize now includes data validation
  setSize(size) {
    if (size === 's' || size === 'm' || size === 'l') {
      this.size = size;
    }
    // else we could throw an error, return false, etc.
    // We choose here to ignore all other values!
  }
}

// DRIVER CODE
let pizza = new Pizza();
pizza.getPrice();
pizza.setSize('s');
```
However we can have a nicer interface and make our `getPrice` and `setSize` act as if they are a property instead of a function. Using `get` and `set`:

```js
class Pizza {
  //...
  // replace our custom getters / setters with these ones!
  get price() {
    const basePrice = 10;
    const toppingPrice = 2;
    return basePrice + this.toppings.length * toppingPrice;
  }

  set size(size) {
    if (size === 's' || size === 'm' || size === 'l') {
      this._size = size;
    }
  }
}

// DRIVER CODE
let pizza = new Pizza();

pizza.price;      // instead of getPrice()
pizza.size = 's'; // instead of setSize(size)
```
Notice how `price` and `size` can be used like a key instead of function but they still perform the `calculation` and `validation`.
