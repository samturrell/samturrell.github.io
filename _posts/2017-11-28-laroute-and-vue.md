---
layout:     post
title:      Using laroute and Vue together
date:       2017-11-28
summary:    The missing "link" between laravel routes and the Vue.js framework
---

Following on from my previous blog post on [laroute](https://samturrell.github.io/2017/11/28/laravel-routes-in-javascript/), I went ahead and created a helpful plugin to ease the integration with projects utilising the Vue.js framework.

Introducing [vue-laroute](https://www.npmjs.com/package/vue-laroute). A simple package with a simple purpose. Simply provide your routes, and access them from within your Vue components and templates using the accessor you provide. By default this is `$routes` but can be changed to avoid conflicts.

From there you have all the routes in your app at your fingertips. For example:

A link:
```html
<p>Let's go <a :href="$routes.route('home')">Home</a></p>
```

An API request:
```js
axis.get(this.$routes.route('products.show', { id: 1337 }))
    .then((response) => { /* Got Product */ });
```

To pull in the plugin, simply `yarn add vue-laroute` and follow the instructions in the documentation.

If you like this plugin, please do star it on GitHub and share.
