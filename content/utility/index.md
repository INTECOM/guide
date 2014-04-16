# Utility methods

## Meta tags

TODO


## Passing data from the page to Sauce

Any data you wish to make available to Sauce should be passed via `Sauce.describe`:

```js
// Describe a full transaction object (e.g. after a purchase has been made)
Sauce.describe("transaction", {
  orderId: "1234231",
  lineItems: [{
    product: {
      id: "12324",
      name: "Sparkly shoes",
      unitPrice: 15,
      image: "http://mysite.com/image.png"
    } 
  }]
});

// Describe the page you're on
Sauce.describe("page", {
  type: "Confirmation"
});
```

The first parameter passed should always be a string describing the name of the data, the second should always be an object, containing the data.

This data can then be accessed after `Sauce.ready` using the `Sauce.page` model. Below are a few examples:

```js
Sauce.data.get("transaction")
// => Returns the full transaction object passed in describe.
```

__Note:__ Sauce does not have a prescriptive structure for passing data at this stage, although we follow a structure similar to the [Universal Variable](http://docs.qubitproducts.com/uv) by Qubit.
