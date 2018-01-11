---
layout:     post
title:      Responsive Blocks and Vertical Alignment
date:       2018-01-11
summary:    How to create responsive cross-browser blocks with vertically aligned content
---

Today I’m going to show you two of my favourite CSS “hacks.” Responsive height blocks, and vertical alignment. These two often go hand in hand, usually with some sort grid of blocks with text in the centre. I’m sure you’ve come across the pattern before.

## Responsive blocks
First up, responsive blocks. We’ve all used responsive width columns, but you’ve probably never used responsive heights. If you apply `height: 50%;` to an element, you’re not going to see any results. Unlike width, height cannot be set as a percentage as block container elements do not not have a height, whereas they do default to 100% width.

We can, however, make the height relative to the width. To do so, we will be making use of the `padding` rule. If you apply the rule of `padding-bottom: 100%;` to a div, you will end up with a perfect square. However, a full page square isn’t exactly helpful is it. We want a grid of squares. You may think this is easy to a accomplish by setting a width on this div and watching it scale, however that is not the case. The padding is actually relative to the **parent** element, _not_ the element with the rule applied.

So to make box smaller and responsively sized, we just need a container element with a width value. This is usually fine as it’s probably within a grid column anyway. Now you just tell the child how big it should be relative to the parent and there you have a perfect responsive height square.

<div class="playground">
    <div style="margin: 0 -10px;" class="clearfix">
        <div style="width: 25%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 100%;"></div>
        </div>
        <div style="width: 25%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 100%;"></div>
        </div>
        <div style="width: 25%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 100%;"></div>
        </div>
        <div style="width: 25%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 100%;"></div>
        </div>
    </div>
</div>

```
<div style="margin: 0 -10px;" class="clearfix">
    <div style="width: 25%; float: left; padding: 0 10px;">
        <div class="primary" style="padding-bottom: 100%;"></div>
    </div>
    ...
</div>
```

You can of course do responsive rectangles by following the pattern and just adjusting the padding percentage.

<div class="playground">
    <div style="margin: 0 -10px;" class="clearfix">
        <div style="width: 33.33333%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 45%;"></div>
        </div>
        <div style="width: 33.33333%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 45%;"></div>
        </div>
        <div style="width: 33.33333%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 45%;"></div>
        </div>
    </div>
</div>

## Vertical Alignment
Ah, vertical alignment, the bane of frontend developers lives. However it doesn’t have to be. Depending on usage, you can follow a simple pattern to achieve vertical alignment that works extremely well with the above responsive blocks tip.

You’ll probably shudder at the thought, but we’re going to be using tables! Well, not exactly tables. Fake tables. Tables have the awesome ability of being able to make use of the `vertical-align` CSS rule for aligning content, and with the use of `display: table;` and `display: table-cell;` we can actually take advantage of this functionality with standard divs.

All you need is a div with `display: table;` and within it, a div with `display: table-cell;` and `vertical-align: middle;`. Just give the parent div a height and you’ll have perfectly entered content.

<div class="playground">
    <div class="primary" style="display: table; height: 100px; max-width: 100%; width: 100%; text-align: center;">
        <div style="display: table-cell; vertical-align: middle; padding: 15px;">
            Look at me being all vertically aligned!
        </div>
    </div>
</div>

```
<div class="playground">
    <div class="primary" style="display: table; height: 100px; max-width: 100%; width: 100%; text-align: center;">
        <div style="display: table-cell; vertical-align: middle; padding: 15px;">
            Look at me being all vertically aligned!
        </div>
    </div>
</div>
```

Some may argue flexbox can solve this problem in much less lines of code, however table-cell is supported in every browser for a worry free dev experience.

## The double whammy
Combining with the above is simple. If you try to put your faux-table inside the responsive block however, you’ll end up with a no longer reliably responsive block. This is because of the height from the padding trick combined with the height of your table. Instead we’ll need to add another container block within the responsive block.

Simply set `position: relative;` on the block with the padding, and add a new div within this with `position: absolute; top: 0; right: 0; bottom: 0; left: 0;` which will make this div the same size as the parent which allow you to add content to the block.

This block also now has a fixed height, so you can now used a percentage height value for your content. Simply add your vertical aligned block to this div and give it a 100% height and width and you’ll have perfectly aligned content within your block.

<div class="playground">
    <div style="margin: 0 -10px;" class="clearfix">
        <div style="width: 50%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 50%; position: relative;">
                <div style="position: absolute; top: 0; right: 0; bottom: 0; left: 0;">
                    <div style="display: table; background: darkgrey; height: 100%; max-width: 100%; width: 100%; text-align: center;">
                        <div style="display: table-cell; vertical-align: middle; padding: 15px;">
                            Look at me being all vertically aligned!
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div style="width: 50%; float: left; padding: 0 10px;">
            <div class="primary" style="padding-bottom: 50%; position: relative;">
                <div style="position: absolute; top: 0; right: 0; bottom: 0; left: 0;">
                    <div style="display: table; background: darkgrey; height: 100%; max-width: 100%; width: 100%; text-align: center;">
                        <div style="display: table-cell; vertical-align: middle; padding: 15px;">
                            Hey, I'm vertically aligned over here too!
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
