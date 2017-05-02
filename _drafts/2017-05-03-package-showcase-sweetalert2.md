---
layout:     post
title:      Package Spotlight: Sweetalert2
date:       2016-05-03
summary:    Turn those ugly native alerts from zero to hero with a simple package
---

You know those awful native browser alerts and prompts? Don’t you wish you could switch them out for something a bit nicer looking? Something that just worked out the box for a simple alert and even something… more? Well, introducing [Sweetalert2](https://github.com/limonte/sweetalert2)!

Sweetalert2 is the actively maintained successor of the highly popular drop-in modal package [sweetalert by t4t5](https://github.com/t4t5/sweetalert). Forked from the original package at the beginning of 2015, sweetalert2 is not a new package by any means. But it is constantly actively maintained and and crammed with extra handy features, and that’s what’s important.

This package is quite close to my heart, as I am a contributor on the project, although not as much as I’d like these days due to crazy work commitments, but I hope to return soon! I’ve implemented numerous fixes, but my main achievement was implementing the build process to bundle the package. Built on [rollup.js](https://rollupjs.org/) it allows you to build for both commonjs, umd, and the ability to add more in the future. I also overhauled the general codebase from a single file to a more ES6 module-based setup. But enough about me, back to the package.

Owner of this supported fork, [limonte](https://github.com/limonte), has done a great job of adding new features at the request of the community and being there to assist and fix issues promptly, with the help of his team of contributors. The package boasts the following features:
* Promise-based modals
* Plugin API methods
* Multiple alert types (success, error, warning, info, question)
* A whole host of configuration options to customise your alert
* Chaining functionality using queues 
* Tests!

If you haven’t checked it out yet, and are in the market for a new alert package, I would recommend you [head over to the docs](https://limonte.github.io/sweetalert2/) and take a look for yourself. And if you know anyone still using the original package, make sure you point them in the right direction, because remember, *friends don’t let friends use unmaintained software*.