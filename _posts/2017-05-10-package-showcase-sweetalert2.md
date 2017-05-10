---
layout:     post
title:      Package Spotlight&#58; Sweetalert2
date:       2017-05-10
summary:    Turn those ugly native alerts from zero to hero with a simple package
minutes:    2
---

You know those awful native browser alerts and prompts? Don’t you wish you could switch them out for something a bit nicer looking? Something that just worked out the box for a simple alert and even something… more? Well, introducing [Sweetalert2](https://github.com/limonte/sweetalert2)!

![netsells](/images/sweetalert2.png)

Sweetalert2 is the actively maintained successor of the highly popular drop-in modal package [sweetalert by t4t5](https://github.com/t4t5/sweetalert). Forked from the original package at the beginning of 2015, sweetalert2 is not a new package by any means, but it is actively maintained and and crammed with extra handy features, and that’s what’s important.

I’ve implemented numerous fixes and the main build process to bundle the package, so I'm quite close to the project myself. Utilising [rollup.js](https://rollupjs.org/) I added functionality to efficiently build for both commonjs, umd, and the ability to add more in the future. I also overhauled the general codebase from a single file to a more ES6 module-based setup.

Owner of this supported fork, [limonte](https://github.com/limonte), has done a great job of adding new features at the request of the community and being there to assist and fix issues promptly, with the help of his team of contributors. The package boasts the following features:
* Promise-based modals
* Plugin API methods
* Multiple alert types (success, error, warning, info, question)
* A whole host of configuration options to customise your alert
* Chaining functionality using queues 
* Tests!

If you haven’t checked it out yet, and are in the market for a new alert package, I would recommend you [head over to the docs](https://limonte.github.io/sweetalert2/) and take a look for yourself. And if you know anyone still using the original package, make sure you point them in the right direction, because remember, *friends don’t let friends use unmaintained software*.