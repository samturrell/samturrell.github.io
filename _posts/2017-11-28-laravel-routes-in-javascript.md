---
layout:     post
title:      Referencing Laravel routes in javascript
date:       2017-11-28
summary:    How to avoid hard coding urls in your client side code
---

When building websites, it’s very tempting to hardcode links to the page you want to go to when clicked, however this creates a huge problem when you typo or want to change this link. You either go through and manually change each link, or you add a dirty redirect for the old urls. Gross.

If you’ve ever used Laravel (if you haven't, you should), you’ve probably used named routes with the `route()` helper. With this you can give a route a unique identifier and reference it with the helper while being blissfully unaware of the actual url scheme that it translate to. If the route requires parameters, these can be passed via the second argument as an associative array of named parameters.

With there being a lot more client side logic in websites these days you end up with the exact same problem. Whether it’s generated html markup with links, or even API endpoints you have no choice but to hardcode the path. Until now.

I’ve recently started using the `lord/laroute` package in my laravel projects. This package takes all your routes and generates a handy javascript module for you to reference your apps routes. It gives you all the same functionality as the route helper, but within your javascript.

The package actually provides a lot more features such as the ability to link to an action by referencing the routes controller and method, however I feel this is an unnecessary way off referencing a route and gives far too much visibility of your web apps underlying structure.

In order to remove this data from the packages output, I’ve gone ahead and extended the original package and removed and unnecessary traces to anything that is not strictly route name related, as this is the best convention for referencing routes. The package can be seen [on packagist](https://packagist.org/packages/samturrell/laroute).

The only thing to note, is that if you do change/add a route, be sure to regenerate the routes file so that the references update.

If you enjoy the package (both mine and the original) please do star them on GitHub and share.
