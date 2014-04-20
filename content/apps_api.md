#Apps API

The apps API is used to provide a simple way for developers to publish apps to the Sauce platform.


##Grunt deployment

TODO


##REST API

All API requests should be targeted at the `http://apps.sauce.ly` endpoint. 

A valid API key is required for all requests, and should be passed in the `Sauce-Api-Token` header.

|            Path            | Method |                             Description                             |
| -------------------------- | ------ | ------------------------------------------------------------------- |
| `/app`                     | POST   | Create a new app if it does not exist.                              |
| `/app/:id/latest           | GET    | Get the latest app with the `id`                                    |
| `/app/:id/version/:version | GET    | Get an app with the `id` and `version`, necessarily the latest one. |
| `/app/all                  | GET    | Get all apps with their latest versions                             |