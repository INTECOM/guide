#Global events

Global events is a great way of subscribing to events that happen in apps using [Backbone.Events](http://backbonejs.org/#Events) functionality.


##Subscribing to events

You can use either `on` or `once` to subscribe to events. (`once` is the same as `on`, but only happens once)

```js
Sauce.events.on("action_publish", function (model) {
  alert("action " + model.get("id") + " was published to Facebook!");
});
```

##Triggering events

Custom events can also be triggered within your apps:

```js
// Trigger the party event
Sauce.events.trigger("party", { host: "Tony Stark" });

// When the party happens, let's go!
Sauce.events.once("party", fucntion (data) {
  alert(data.name + " is the host - it's gonna be awesome!");
});
```


##Standard events

Any event can be triggered using this system, however we do have a set of standard events that are automatically triggered:

|       Name       |                 Description                 |
| ---------------- | ------------------------------------------- |
| action_publish   | When an action is published to Facebook     |
| action_unpublish | When an action is unpublished from Facebook |