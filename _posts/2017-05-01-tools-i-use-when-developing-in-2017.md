---
layout:     post
title:      Tools I Use When Developing in 2017
date:       2017-05-01
summary:    Technology and tools that keep me sane when developing in an ever-evolving industry
minutes:    5
---

In order to get a good overview of me as a developer and how I work on a day-to-day basis, I’ve decided to write this post on the general tools and technology I work with. Hopefully future posts will build on this as changes to my workflow are introduced, so it’s nice to have a starting reference point. I’ll link everything I use, as I fully recommend everybody to check them out.

## Operating System and Hardware
For as long as I’ve professionally developed, I’ve been based on OS X. Starting about 4 years ago on a big 2012 17” MacBook Pro. Nowadays I’m rocking a 2014 15” MacBook Pro Retina with the following specs:
* 2.6GHz Quad-core Intel Core i7
* 16GB RAM
* 512GB Flash Storage

## IDE/Code Editor
I’ve come a long way since my Dreamweaver days. For a long time I was using the brilliant yet not officially released Sublime Text 3, however fairly recently (this year) I’ve moved over to a more fully functioning IDE. As I use both PHP and JavaScript fairly often, in order to get the level of compatibility I need I use [IDEA Ultimate Edition by IntelliJ](https://www.jetbrains.com/idea/) .

## Development Tools
### Development Environment
Over the past few years I’ve seen different development environments come and go. MAMP, docker, homestead, etc. The newest player in the game is [Valet](https://github.com/laravel/valet) by Laravel. It allows you to set one or more directories as your “root” for all of your projects, and then simply navigate to `project.dev` in the browser, where `project` is a directory in your root directory. No other setup required. No modifying hostnames or ports, or starting and stopping servers for different projects. It just works.

For more advanced server functionality, such as elastic search or catching outbound emails I also use docker alongside to provide these services. To make this workflow easier, I created a [couple of aliases](https://github.com/samturrell/valet-aliases) to synchronise the tasks of starting valet and a supporting Docker file.

### Terminal
I use iTerm, an improved version of the default macOS terminal.app. I replace the standard bash shell with the more powerful zsh alternative. This allows me to utilise many plugins to aid productivity such as [git](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git), [z](https://github.com/rupa/z) , [docker](https://github.com/AeonAxan/oh-my-zsh/blob/master/plugins/docker/README.md) and [more](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins) .

### Git GUI
Most of my git usage is done via the command line using the zsh git plugin, but for peace of mind in those times when you’re doing a potentially dodgy commit, I use [Tower](https://www.git-tower.com/mac/).

### FTP Client
In the rare instance I use FTP (usually to transfer images, and almost always over the SFTP protocol) I use [Transmit](https://panic.com/transmit/) to get the job done.

### MySQL Client
For any database management, whether local or on production servers, I use [Querious](https://www.araelium.com/querious/) by Araelium. 

### Misc
#### Avocode
As a frontend developer I have to deal with PSD and Sketch files sent over from the designer to code up. Both of which are paid license products, and I’d rather not have them on my machine if I can help it. Not to mention issues with fonts in Sketch files, but that’s beside the point. To get around this problem, I use an app called [Avocode](https://avocode.com/ ). This allows the designer to upload visuals once they’re ready for development, and for the developers to extract styles and assets in a pixel-perfect fashion from the interface. The app also boasts the following features:
* Store SASS/Less variables
* Upload revisions
* Comment and request feedback on parts of the design
* Multiple image export formats (SVG, PNG, JPEG, Base64)
* Export images at multiple resolutions
* Copy text as HTML

#### ImageOptim
When you work with images on the web, you have to be very careful about the images you’re adding, making sure they’re not too heavy for the user to download. To get around this I use a handy app for compressing and optimising images called [ImageOptim](https://imageoptim.com/mac) which does a great job at compressing for the web.

## Workflow 
### JavaScript
After years of using Coffeescript extensively at netsells, I recently made the decision to transition the team to using to the newer vanilla JavaScript standard of ECMAScript 2015 (or ES6). Big shoutout to Wes Bos for his [ES6 For Everyone](https://es6.io/) video course that made this transition a breeze. 

### CSS
I write all of my CSS using the [Less](http://lesscss.org/) pre-processor language, which is transpiled down the standard CSS using our webpack workflow.

### Bundler
[Webpack](https://webpack.js.org) is great. Like really great. But boy is it an endless struggle to set up a config for each project you use it on. Luckily, Jeffrey Way came and saved the day with the glorious Laravel Mix package that makes web pack setup a breeze with a fluent API for defining Webpack build steps, as well as a fully customisable webpack config you can tweak to your hearts content.

## Frameworks
### JavaScript
There’s a big joke in the development community about JavaScript frameworks, and how often a new one is released and adopted. I’m sure you’ve heard the one. The big boy on the block right now is [Vue.js](https://vuejs.org/) - an intuitive, fast and composable MVVM for building interactive interfaces. The best part of Vue is that it’s completely opt-in and lightweight. So you can use it for a single ajax contact form component, or a fully fledged Single Page Application with routing and Server Side Rendering + Hydration. There’s also a huge community of developers producing [plugins](https://github.com/vuejs/awesome-vue) and drop-in components - I’ve even [made one of my own](https://github.com/samturrell/vue-breadcrumbs) . It’s extremely powerful, and I recommend you check it out.

### CSS
[Bootstrap](http://getbootstrap.com/) is my CSS framework of choice, and has been for a long, long time. The grid, mixins and generally awesome features make it an easy win. It allows me to selectively pull in what I need for the specific project via it’s use of the Less pre-processor for the raw source files. Less code bloat, and no awful classes cluttering up the dom.




