---
layout:     post
title:      Serving static content in Laravel Valet
date:       2017-12-03
summary:    Check out my custom valet driver for prototyping outside of a framework.
---

A couple of weeks ago I was working on a very non-conventional project where I had to create a bunch of UI components in standard php files like back in the day. My local server of choice is [laravel/valet](https://github.com/laravel/valet) which tries to automatically handle url resolution for frameworks.

However when accessing php files directly, by default it tries to route every request through an `index.php` entry point so that frameworks and general url rewriting works. So for example I have a directory with various template files such as `about.php` which pull in standard components to build up the template, but I can’t access this file on the frontend as it just requests the `index.php` file while the url is requesting `about.php`.

Not ideal.

The great thing about Laravel Valet however, is that you can create custom drivers that should run depending on the logic you provide. To enable the functionality I wanted, I created a [static valet driver](https://github.com/samturrell/static-valet-driver). The driver simply looks for a `static` file in the root of the project and runs. Easy.

Instructions on how to use the driver are included in the readme. Please share and star ⭐️ the project if you found it helpful.
