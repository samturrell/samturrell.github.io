---
layout:     post
title:      Scoped vs Unscoped Styles in Vue Components
date:       2017-05-27
summary:    How to structure Vue components with the ability to style subcomponents when using scoped styles.
---

When working with Vue, the ideal development setup is to use [vue-loader](https://github.com/vuejs/vue-loader) to load .vue files. If you've never heard of .vue files, they basically take the idea of self contained components to the next level by allowing you to contain the template, css and component logic within a single file, and have it compile and render on your page at runtime. Nice right?

However, the way the style loader works is that it inserts the css into the DOM in a style tag, which could potentially pollute the styling of other elements on the page if your selectors are very generic. To get around this, you can append the "scoped" attribute to the style tag. What this does is add a unique identifier to every element in your template, and add this same rule to your styling rules so that that rule will only ever be applicable within the component that defined it. Great! No more leaky styles!

However, it's quite common (for me at least) to be using sub components within my single component, for instance <contact-modal> might pull in a <modal> component wrapper that has the HTML markup of a modal. So what if we want to tweak the styles in this instance of the wrapper component? As this component isn't in the compilation scope our unique identifier won't be applied to these elements.

Luckily there is a solution to this. It's actually possible to use as many `<style>` tags as you want within a vue component file, and they will each be compiled separately. This means you can have your main style tag scoped to the current instance, and a non-scoped version that is allowed to touch anything that your component isn't. In my modal example, the modal sub component inherits its id attribute from the parent component so it's easy to set a semi-reliable scope by nesting each rule under that id.

Again though, you are modifying global scope with anything you put in this tag, but it greatly reduces potential style pollution.

UPDATE:

While I was in the process of writing this article, [vue-loader 12.2.0](https://github.com/vuejs/vue-loader/releases/tag/v12.2.0) was released. This release brings support for “deep” selectors in scoped style tags. The deep selector is in the format `.element >>> .sub-component-element {}` and will compile down so that styles applied to the sub-component are outside the parent component scope. For example, the above would compile down to something like `.element[data-v-xxxxxxx] sub-component-element {}`.
