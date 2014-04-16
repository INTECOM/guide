# Quick start


## Adding the Sauce snippet

The Sauce snippet is the code that makes everything else happen. Add the below code directly before the `</head>` on every page of your site:

```js
window.Sauce={isReady:false,options:{},init:function(e){for(var t in e){this.options[t]=e[t]}var n=document.createElement("script");n.src="/dist/sauce.js";n.async=true;n.id="sauce-js";document.getElementsByTagName("head")[0].appendChild(n)},readyCallbacks:[],ready:function(e){if(this.isReady){e()}else{this.readyCallbacks.push(e)}},loadApp:function(e,t,n){this.readyCallbacks.push(function(){Sauce.loadApp(e,t,n)})},loadCustomApp:function(e,t){this.readyCallbacks.push(function(){Sauce.loadCustomApp(e,t)})},_data:{},describe:function(e,t){this._data[e]=t}}

Sauce.init({ id: "yourclientid" });
```

### What does this code do? 

Coming soon.


## Running apps

Sauce provides the facility for running official apps that are part of the Sauce marketplace, and unofficial custom implementations. In reality they both work almost identically, but the custom ones are not yet in the marketplace. 

__Helpful tip:__ every single app corresponds to one JavaScript file.


### Official apps

Run the function `Sauce.loadApp` after the Sauce snippet (see below). The first parameter is the app name ("button") and the second is the app version ("0.0.17");

```js
Sauce.loadApp("button", "0.0.17");
```

You can also optionally add a callback function as the third argument when the app has finished loading:

```js
Sauce.loadApp("button", "0.0.17", function () {
  alert("the app has loaded!");
});
```

__Note:__ The callback function is fired after the app file has loaded but __before__ it has started executing.


### Custom apps

If you've built your own app that you'd like to run, you can use the `Sauce.loadCustomApp` function to load any JavaScript file:

```js
Sauce.loadCustomApp("http://mydomain.com/mycustombutton.js");
```

