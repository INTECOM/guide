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

  "settings": {
    "global": {
      "formDescription": "You can customize all the fields in the login prompt. Note that all parameters are optional, if you leave a field blank the form will still work.",
      "fields": {
        "title": {
          "title": "Title",
          "type": "text",
          "placeholder": "The title of the prompt"
        },
        "minPageviews": {
          "title": "Minimum pageviews before show",
          "type": "number",
          "placeholder": "The number of pageviews to wait before showing the box."
        }
      },
      "codeDescription": "Copy & paste the below code directly after the <code>Sauce.init</code> line in your <a href='https://<%= client.siteDomain %>/admin/themes/<%= client.themeId %>?key=snippets/sauce.liquid' target='blank'>sauce.liquid</a> snippet."
    },
    "dom": {
      "formDescription": "",
      "fields": {},
      "codeDescription": ""
    } 
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