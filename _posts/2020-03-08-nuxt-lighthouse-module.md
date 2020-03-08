---
layout:     post
title:      New package - Nuxt Lighthouse Module
date:       2020-03-08
summary:    Implementing automated Lighthouse audits on each deploy of your Nuxt.js application.
---

When building applications for the web, there are certain metrics you need to actively think about during the development process. Things such as Speed and Performance are becoming increasingly more important to get right, especially with [Google taking these metrics into account when ranking search results](https://webmasters.googleblog.com/2018/01/using-page-speed-in-mobile-search.html).

To aid in analysing these metrics, Google released a tool known as "Lighthouse". This tool has gone through a few stages, starting as a browser extension, and now natively a part of the Chrome Devtools Audits tab. 

> Lighthouse is an open-source, automated tool for improving the quality of web pages. You can run it against any web page, public or requiring authentication. It has audits for performance, accessibility, progressive web apps, SEO and more.
> 
> [Google Developer Documentation](https://developers.google.com/web/tools/lighthouse/)

Essentially this tool will run a specific page through a whole bunch of tests and output scores and appropriate recommendations to improve, broken down into a handful of key categories:

- Performance - how fast the page loads, and whether the content returned is appropriately compressed and efficient over the network.
- Accessibility - how accessible your web application is for users of assistive software or users with visual impairments
- Best Practices - whether your code is written in a general safe and secure way.
- SEO - how crawlable your application is to search engine bots and content is optimised accordingly.
- Progressive Web App - whether your app is ready to be used as a fully fledged PWA. 

While this tool is extremely helpful, it is often not utilised often enough. It's incredibly important that metrics are monitored during development, as well as after deploying new changes to production.

Introducing: [@samturrell/nuxt-lighthouse-module](https://www.npmjs.com/package/@samturrell/nuxt-lighthouse-module)!

This module provides a simple integration with Google Lighthouse, to automatically perform Lighthouse reports on each successful deploy of your application.

This module can log to three different locations:

- Directly to the console
- To a file in the static folder of your app
- To Slack via a Slack Webhook

The module will run a Lighthouse report after your application has been built, or more specifically when the `ready` hook is fired.

This module will also store previous reports in a `.lighthouse/` directory in your project root, and will use this to compare and return a `change` value, for how much each metric has changed since the last report.

## Installation

The module is available on npm, and can be installed with the following command:

```sh
yarn add @samturrell/nuxt-lighthouse-module
```

## Usage

Simply add the module to your nuxt config:

```js
module.exports = {
    modules: [
        '@samturrell/nuxt-lighthouse-module',
    ],
};
```

And define any applicable options:

```js
module.exports = {
    lighthouse: {
        slackWebhookUrl: '',
        htmlOutput: true,
        consoleNotifier: true,
    },
};
```

This module can be disabled completely by setting the `LIGHTHOUSE_DISABLED` environment variable to `true`.

For documentation on available module options, check out the package on [Github](https://github.com/samturrell/nuxt-lighthouse-module).
