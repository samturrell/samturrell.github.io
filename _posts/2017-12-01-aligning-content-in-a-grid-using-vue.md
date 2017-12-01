---
layout:     post
title:      Aligning content in a grid using Vue
date:       2017-12-01
summary:    A Vue plugin to ensure grid content pleases the eye.
---

Another quick Vue package, to achieve a fairly common issue. [vue-match-heights](https://www.npmjs.com/package/vue-match-heights) exists to aid in grid layouts with elements of varying heights. Simply put, this package provides a single Vue directive that loops through given selectors and ensures they are the same height.

Similar functionality can be achieved with flexbox, but if browser compatibility is a concern or you need greater depth in deciding which elements should scale, this plugin may be useful to you.

For instance, you might have blocks with a header, content and button block. You want the content to start at the same height, and the buttons to be aligned to the bottom of the block. To do this, you would ensure the title is the same height, then the content, and the button should fall into place. This can be achieved with the following markup:

```html
<div
    class="row"
    v-match-heights="{
        el: ['.title', '.content'],
    }"
>
    <div class="col-sm-6" v-for="post in posts">
        <div class="block">
            <div class="title">
                <h3>...</h3>
            </div>
            <div class="content">
                ...
            </div>
            <div class="button">
                <a class="btn">Button</a>
            </div>
        </div>
    </div>
</div>
```

You can also pass in another option to disable the sizing of elements on specific viewports. For details on this, check the [Github repo](https://github.com/samturrell/vue-match-heights).

If you like this plugin, please share and ⭐️ on Github.
