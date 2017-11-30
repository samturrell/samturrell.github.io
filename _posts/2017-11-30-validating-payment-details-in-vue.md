---
layout:     post
title:      Validating payment details in Vue
date:       2017-11-28
summary:    A simple Vue plugin to validate card details
---

If you’ve ever built a payment form on a website, you’ve probably come across things such as credit card input masks and validation/formatting of various fields. The guys over at stripe have made a fantastic library for this known as jQuery.payment.

Although it’s easy enough to manually set up the fields to mask and validate as and when you need them, it’s not exactly convenient. For you folks using Vue, this one’s for you.

This package is built with jQuery, so if that’s a no-no for your project, this package might be a no-go for you. If not, read on!

Introducing [vue-stripe-payment](https://www.npmjs.com/package/vue-stripe-payment) - a simple wrapper library for jQuery.payment integration into Vue. This simply plugin registers a `v-payment` directive to automatically bind to form fields. Simply add the type of mask/format validation you require for the field as the directive arg, and away you go.

For example:

```html
<form>
    <div class="form-group">
        <label>Card number</label>
        <input class="form-control" v-payment:formatCardNumber>
    </div>
    <div class="form-group">
        <label>Card Expiry</label>
        <input class="form-control" v-payment:formatCardExpiry>
    </div>
    <div class="form-group">
        <label>Card CVC</label>
        <input class="form-control" v-payment:formatCardCVC>
    </div>
    <div class="form-group">
        <label>Numeric input</label>
        <input class="form-control" v-payment:restrictNumeric>
    </div>
    <button class="btn btn-primary">Submit</button>
</form>
```

You can also bind to parent elements of inputs if you do not have direct access to the input element, for example if you’re using a UI library such as vuetify which wraps inputs in a custom wrapper.

And if that isn’t enough, you have full access to the payment plugin via `this.$payment` in your components so you can programmatically format and validate any data at any time.

If you find this plugin helpful, please star on GitHub and share.
