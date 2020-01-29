---
layout:     post
title:      New package - Storybook Directories
date:       2020-01-29
summary:    A simple module for generating your storybook story structure based on your directory structure.
---

If you haven't heard of storybook, you're missing out. We're big fans of it at Netsells, and it has really helped us have clear visibility of what's available to us when build our web apps. In a nutshell, Storybook gives you an isolated sandbox environment in which you can code up your components outside of your main application. It has a variety of addons available, which allow you to influence your stories and test them with different data and situations. I highly recommend you check out the [Official docs](https://storybook.js.org/) and give it a go. 

Organisation is key in your storybook, whether it's only visible internally or is part of a public-facing component reference. Keeping your stories categorised will mean you're able to find the components you're looking for a lot easier, and ultimately save time.

What also takes time is figuring out the structure you want, and updating multiple stories with the perfect structure that works for you. This is a lot of duplicate code, just for the sake of formatting.

That's why I built this package. This simple module solves this problem by allowing you to control the story structure right from the drag and drop UI of your file system, meaning no code updates are required.

## Installation

```sh
yarn add @netsells/storybook-directories
```

## Usage

Simply import the package into your storybook config, and update your `configure` statement to pass in the `storybookDirectories` function with a `stories` parameter which matches your `require.context` call.

```js
import storybookDirectories from '@netsells/storybook-directories';

configure(
    storybookDirectories({
        stories: require.context('../stories', true, /\.stories\.js$/),
    }),
    module
);
```

Your stories now no longer need to specify a default export, although if you require it you can simply omit the `title` property. However, if you wish to override the directory structure for a story you can do this by simply specifying a title as you would normally.

Take the following directory structure:

```
stories/
│
├─ 0. Welcome/
│  └─ Welcome.stories.js
│
├─ 1. UI/
│  ├─ Typography.stories.js
│  ├─ Buttons.stories.js
│  └─ Icons.stories.js
│
├── 2. Forms/
│  ├─ Inputs/
│  │  ├─ TextInput.stories.js
│  │  └─ CheckboxInput.test.js
│  └─ ContactForm.stories.js
│
```

Would generate stories with titles in the following format:

```
0. Welcome|Welcome
1. UI|Buttons
1. UI|Icons
1. UI|Typography
2. Forms|Inputs/TextInput
2. Forms|Inputs/CheckboxInput
2. Forms|ContactForm
```

This format matches the Storybook separator formats, and would generator a storybook with grouped sections matching your directory structure.
