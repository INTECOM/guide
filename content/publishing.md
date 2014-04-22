#Publishing your app

The apps API is used to provide a simple way for developers to publish apps to the Sauce platform.


##Using the Sauce command line tool

All apps should be published to Sauce using our [command line tool](https://github.com/sauce/cli):

```
sauce publish
```

To overwrite a previous version, you can add an `-f` parameter.


##App config

The application config should be specified in the `sauce.app.json` file. Below is an example configuration setup:

```json
{
  "version": "0.0.18",
  "name": "button",
  "title": "Button",
  "description": "An enticing description goes here.",
  "images": {
    "thumb": "150x150.gif",
    "card": "310x100.gif"
  },
  "setup": {
    "steps": [
      {
        "title": "Introduction",
        "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.",
        "image": "http://dtt617kogtcso.cloudfront.net/img/420x228.gif"
      },
      {
        "title": "Create Open Graph action",
        "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.",
        "image": "http://dtt617kogtcso.cloudfront.net/img/420x228.gif"
      }
    ],
    "finish": {
      "message": "You made it! Any questions or ideas? Drop us a message on live chat below.",
      "buttonText": "Back to apps list",
      "buttonLink": "#apps"
    }
  }
}
```