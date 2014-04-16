# UI Components

Sauce offers a number of in-built UI components for you to use within your apps. While you could certainly build these out yourself, we strongly encourage utilising these components to provide a consistent look and feel for the end customer, and to make it simpler for clients to customise the design. (Did we also mention it makes your life simpler!)

## Modal

The modal component is accessible via `Sauce.Modal`, and is useful for user prompts and share dialogs. 

Methods available:

* open
* alert
* loading
* close


###Sauce.Modal.open

The main function for opening a modal, it can have the following attributes passed:

|    Key    |  Type  |                                                                                      Description                                                                                      |
| --------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `title`   | String | The title of the modal.                                                                                                                                                               |
| `content` | String | The content or HTML you'd like to pass to the modal. You can pass absolutely any HTML you like in here.                                                                               |
| `buttons` | Object | The modal can have two buttons: `primary` and `secondary`. Each has two attributes: `label`, the text in the buttons, and `callback`, an arbitrary callback function to run on click. |
| `alert`   | Object | If you'd like to alert the user, you can pass an alert object with the `title` and `content` attributes. `type` will dictate the type of modal. Possible values: "danger", "info", "success", "warning" |


Example:

```js
Sauce.Modal.open({
  title: "Share this to Facebook",
  content: "<p>I've got some HTML in here... oh yes.</p>"
  buttons: {
    primary: {
      label: "Share",
      callback: function () {
        alert("Yes! They shared it!");
      }
    },
    secondary: {
      label: "Cancel"
      callback: function () {
        alert("Oh noes!");
      }
    }
  }
});
```

__Credits:__ We've taken a lot of inspiration from the [Shopify Embedded App SDK modal](http://docs.shopify.com/embedded-app-sdk/methods#Modal-open) API design.


###Sauce.Modal.alert

A higher level of `Sauce.Modal.open`, this can be run to make life simpler when showing an alert:

|    Key    |  Type  |                      Description                      |
| --------- | ------ | ----------------------------------------------------- |
| `title`   | String | The title of the alert.                               |
| `content` | String | The content you'd like to show inside the alert. |
| `type`    | String | The type of the alert. Possible values: "danger", "info", "success", "warning". |

__Credits:__ we've used the same default stylings and colour schemes as [Bootstrap alerts](http://getbootstrap.com/components/#alerts).

Example:

```js
Sauce.Modal.alert({
  title: "Oh my goodness",
  content: "Something went very, very wrong."
});
```


###Sauce.Modal.loading

Another higher level version of `Sauce.Modal.open`, this can be run to show a loading spinner.

|    Key    |  Type  |                    Description                    |
| --------- | ------ | ------------------------------------------------- |
| `content` | String | The message you'd like to show above the spinner. |

Example:

```js
Sauce.Modal.loading({
  content: "Posting to Facebook..."
})
```
