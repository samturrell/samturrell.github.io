---
layout:     post
title:      Using jQuery plugins in Vue 2.0
date:       2017-11-04
summary:    Avoiding the pitfall of Virtual Dom when using jQuery plugins and custom event listeners
---

Vue is great in the fact that it’s lightweight enough that you can pull it into your project and only use it as and when you need it for specific functionality. The main use case we have found on standard CMS-driven websites, is contact forms and newsletter signups. Most other simple functionality can be achieved via the use of jQuery simple plugins.

With the introduction of Vue 2.0 some time back, the framework gained “Virtual dom”. What is Virtual Dom you may ask? Well, in its simplest form, it’s the DOM translated into code for easy diffing and updating. When Vue is initialised via `new Vue({ el: ‘#app’ });` the dom of the page is re-rendered in it’s Virtual DOM form, ready for Vue to do it’s thing when it’s required.

jQuery plugins, and your own custom vanilla event listeners even, are bound to elements on the page that you interact with in one way or another. When Vue comes along and re-renders the page, these events end up being lost. This poses quite the problem if you’re looking to utilise Vue late into a project and all these scripts are already set up. The listeners will no longer be bound, and you’re left with a static page. So what do we do?

Well, we have two options:

*Option 1* - we go the “correct” route and convert our functionality into vue components and directives that have lifecycle hooks that can fire when they know the dom has been loaded via Vue. Unless your app is small, this is going to be an issue, and most probably not a wise investment of time.

*Option 2* - we utilise a single lifecycle hook that tells our scripts when they’re *really* allowed to touch the dom.

To do this, it’s actually incredibly simple.

We’ve all used `$(document).ready(() => { /* scripts go here */ });` before right? In an ideal world, we would be able to fire this event again to let the scripts know that we’re ready. Unfortunately this event only fires once and it’s not possible to trigger it a second time. Instead, we need to use our own event.

I like to call my event `domReady`, because, well, it’s when the dom is ready, silly. Implementation is simple. When you set up your Vue instance we want to utilise the `mounted` hook. This hook is called when the instance has been attached to the dom, but not necessarily that other components have rendered. To get around this problem, we will use the `nextTick` method.

Implementation should look somewhat like the following:

```js
new Vue({
    el: '#app',

    mounted() {
        this.$nextTick(() => $(document).trigger('domReady'));
    },
});
```

Tada! We have a custom event fired at the point of virtual dom creation, where it’s safe to apply non-vue events.

Hooking your current scripts up to this event is also incredibly simple. Just replace all instances of:

```js
$(document).ready(() => {
    // Scripts...
});
```

with:

```js
$(document).on('domReady', () => {
    // Scripts...
});
```

Easy! If your scripts don’t currently use the ready event, simply wrap everything in our custom event and you’re good to go!
