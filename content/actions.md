#Publishing actions

Sauce makes publishing actions to Facebook significantly easier that just using Facebook's SDKs.


##The basics

You need to create an action using `new Sauce.Action`, for example:

```js
// create an action
var action = new Sauce.Action({
  type: "sauce_demo:purchase",
  object: {
    type: "product",
    url: "http://mysite.com/product1.html"
  }
});

// save it
action.save();
```

__Note:__ Always wrap `new Sauce.Action` inside a `Sauce.ready` callback function.


##Parameter reference

Any of the below attributes can be passed.

|        Key         |   Type  |                                                                                                                                     Description                                                                                                                                      |
| ------------------ | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`             | string  | The action type, e.g. "sauce_demo:purchase"                                                                                                                                                                                                                                          |
| `object`           | object  | The object we're sharing the Facebook                                                                                                                                                                                                                                                |
| `object.type`      | string  | The type of object we're sharing, e.g. "product"                                                                                                                                                                                                                                     |
| `object.url`       | string  | The URL of the object we're sharing to Facebook. Note that Facebook will scrape this page when the action is posted to Facebook.                                                                                                                                                     |
| `explicitlyShared` | boolean | Utilises Facebook's [explicit sharing](https://developers.facebook.com/blog/post/2012/08/13/building-user-intent-into-the-open-graph/) functionality to allow for actions to have a higher prominence in news feed. Requires the explicitly shared extended permission. Recommended. |
| `message`          | string  | Post a user-inputted message to Facebook along with the action.                                                                                                                                                                                                                                                             |


Here's a slightly more complex example utilising some of the additional features:

```js
// create an action
var action = new Sauce.Action({
  type: "sauce_demo:purchase",
  object: {
    type: "product",
    url: "http://mysite.com/product1.html"
  },
  message: "I love this product!!!",
  explicitlyShared: true
});

// save it
action.save();
```

##Mentioning friends

Sauce automatically parses the `message` parameter and looks for friend names within it. If found, the friends are mentioned and tagged on Facebook.


##Handling success & error

Sauce utilises JavaScript promises, so you can run the following to detect when the action has been shared successfully, or something went wrong:

```js
action.save().done(function (action) {
  alert(action.get("id") + "was created!");
}, function (err) {
  alert("coming went wrong: "+err);
});
```















