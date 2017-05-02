---
layout:     post
title:      Vue&#58; Understanding the bind syntax
date:       2017-05-01
summary:    Knowing when and why to use the v-bind syntax in Vue.js
minutes:    5
---
I’ve said it once and I’ll say it again a thousand times: Vue is a fantastic framework. But there’s a part of it I see being misunderstood and somewhat misused fairly often, whether it’s from developers on my team, published plugins, or even developers looking for help in the Vue slack channel. And that is the `v-bind` syntax when used with html attributes and props.

## The problem
I get slightly triggered when I come across something along the lines of `<my-component v-bind:custom-prop-text="'Hello World'"></my-component>` in the wild. If you’re asking what’s wrong here, you’re probably one of those people I’m talking about. And that’s completely fine, but it’s fundamentally backwards, and (hopefully) by the end of this article you’ll understand why.

## About the syntax
So what is `v-bind`? Well, with Vue, you’re able to dynamically bind one or more attributes, or a component prop to an expression directly in the HTML. The magic comes into play when you prepend an attribute with the `v-bind` directive.

Let's take a standard link. `<a href="http://twitter.com/SamTurrellDev">My twitter</a>` for example. What if we wanted to make this dynamic? Well, you might try and link it up to your Vue component data using something like `<a href="user.twitter_link">My twitter</a>`. So would this insert the `twitter_link` value into our `href`? No - you'd just end up with a link to `user.twitter_link` in the `href` once your page had rendered.

However, when you prepend the `href` tag with `v-bind` syntax like so: `<a v-bind:href="user.twitter_link">My twitter</a>`, you end up with something very different. You see, when Vue recognises that you’re using this directive it will try and resolve the value from the current component/instance data. 

In this example `user.profile_link` will try to resolve to `this.user.twitter_link` and, assuming you have an object in your data which matches this structure, it will insert the value of `twitter_link` into the `href` of your link. Great right?

This is a very basic example obviously, and you’re able to pass many different types of data into a `v-bind` such as a literal object, a function, or any type of data your components prop allows. The takeaway here, is that v-bind will try and resolve whatever you pass into it, into a javascript expression. It’s like saying "Hey Vue, I’m passing you some data, can you work out the value for me and handle it? Cheers, mate."

## Why this is being used wrong
So let’s go back to our first example: `<my-component v-bind:custom-prop-text="'Hello World'"></my-component>`. With what we’ve learnt above, we know that, as we’re using `v-bind`, Vue will try and evaluate this data as an expression. The data we’re passing in here is a little different than a path to an object value though, it’s a literal string. 

So what does Vue do in this instance? Luckily, it won’t try and find `this.Hello World` on the model because that would throw a nasty error, it’s a little smarter than that. It will actually detect that it’s a string, and treat is at such. This means `v-bind:custom-prop-text="'Hello World'"` will resolve to `this.customPropText === 'Hello World'` in the `my-component` component. That’s all good right? Sure, but it still doesn’t make sense.

Using `v-bind` on a string allows you to do string interpolation such as `<my-component v-bind:custom-prop-text="'Hello ' + user.first_name"></my-component>` which is handy. But we’re not doing that. So what if we drop the `v-bind` altogether? 

A lot of people think that just because we’re using custom props on a component, we need to use `v-bind` in order to pass the value in, but this is incorrect. If we’re using string literals with no need of evaluating it we can get away with the following: `<my-component custom-prop-text="Hello World"></my-component>`. When we pass in the data this way, we don’t need Vue to try and work it out because the data will be exactly as we passed it in.

## Conclusion
If you’re just passing in a string, you don’t need to use `v-bind` at all. There’s no point making Vue try and evaluate something when it doesn’t need to. If it’s not dynamic, don’t force it to be. 

I would also drop the `v-bind` altogether and use the shorthand colon convention so `v-bind:href="value"` would be `:href="value"`, it reads a lot nicer in my opinion.