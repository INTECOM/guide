#Troubleshooting

Let's face it, integrating your site with Facebook can be a little tricky. It's our aim at Sauce to make this as simple as possible, so we've added a list of common issues here, and how to overcome them.


##Actions aren't publishing to Facebook

There's a number of things that could cause this:

###Open Graph meta tags aren't on your product pages

Facebook uses these meta tags to determine how the content should look when shared to Facebook. These are required on any pages you'd like shared to Facebook via Sauce. 

The meta tags look something like this:

```html
<meta property="og:type" content="product" />
<meta property="og:title" content="Flower print jeans" />  
<meta property="og:image" content="http://cdn.shopify.com/s/files/1/0399/1157/products/shoes3_grande.jpg?v=1394656926" />
<meta property="og:image:secure_url" content="https://cdn.shopify.com/s/files/1/0399/1157/products/shoes3_grande.jpg?v=1394656926" />  
<meta property="og:price:amount" content="45.00" />
<meta property="og:price:currency" content="GBP" />
```

You can check how Facebook views your page by using their [debugger](https://developers.facebook.com/tools/debug) tool.


###Has your custom story been approved?

For the public to be able to publish custom actions to Facebook with your app, your app needs to be approved by Facebook. You can submit the action for approval at _[developers.facebook.com](https://developers.facebook.com) > Your app > Status & Review_.


###Your app is still in sandbox mode

When your app is in sandbox mode, only Administrators, Developers or Testers can use & test your app. To add them:

* Go to [developers.facebook.com](https://developers.facebook.com)
* Open up the roles page in _Apps > your app name > Roles_
* Add the user as an admimistrator/developer/tester

__Note:__ With many Sauce apps it's possible to mention friends with a custom message (using @name). When your app is in sandbox mode, only users added in the roles can be mentioned.


###There's something wrong with Sauce, or the app you're using

Unfortunately bugs happen with any tech company. If you think you've found an issue please report it at [hello@sauce.ly](hello@sauce.ly).
