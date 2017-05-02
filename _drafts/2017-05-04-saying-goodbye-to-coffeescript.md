---
layout:     post
title:      Saying goodbye to CoffeeScript
date:       2016-05-04
summary:    How I fell in and out of love with CoffeeScript for the better
---

Set the scene. The summer of 2014. A junior developer (me) in their first development job, sat in the office on a weekend for a team “Hack day”. Mission? Learn something new.

## The discovery phase
We used hipchat for internal coms at the time, and often sent hilarious pictures of each other to the group chat. Most of the time we had to trawl through files to find the image the next time we thought it witty to share. Why not solve this problem, I thought? Sounds good!

I decided to write a hipchat “bot” to save and regurgitate our hilarious memes on command. I set out to find a platform to help point me in the right direction. I soon stumbled on [Hubot by GitHub](https://hubot.github.com/docs/) - an extendable chatbot that can be customised with your own scripts. Excellent!

Looking through the documentation I spotted a language I’d never seen before. And there it was. “CoffeeScript.” A couple of hours, and my first ever cup of actual coffee later (Seems fitting), I was the CoffeeScript master. My mind was blown by this new language. Gone were the days of `that = this` and endless closing brackets. And hello you gorgeous Class definitions! It was beautiful. I never did write that bot, I was having too much fun with this fancy new syntax.

## The day of enlightenment
Scene change. Date: March 31st 2017. The years of websites later, operation ES6 commences. All of the websites I had built since that day had been using CoffeeScript for my scripting needs. Until one day I proposed the switch to my team.

They were keen, but I was hesitant at first. Mainly because most of the features boasted by ES6 were available in my beloved CoffeeScript so why would I switch? Well, mainly it meant newcomers didn’t have to learn a completely new language. That’s a bonus. 

I then stepped back and reevaluated my thoughts on the matter and realised that, well, if the features are basically the same why am I still relying on a preprocessor to get the goodness we all deserve? I’m sold. With this, the decision was a unanimous yes - to the annoyance of some new members who had just about grasped CoffeeScript.

## Making the switch
The switch was fairly easy. ES6 is just vanilla javascript at the core, so nothing to worry about there. To the benefit of my team, I decided to push for the company to purchase the fantastic “ [ES6 for everyone](https://es6.io/) ” course by Wes Bos. This course has been a great resource and has allowed everyone to pick up both the basic new additions to the spec as well as the more advanced features.

Since then we haven’t look back, and hate having to go back to legacy projects. We can usually be heard muttering to ourselves when we try to write standard JavaScript in a CoffeeScript file out of muscle memory. For bigger projects I’ve actually converted the whole codebase from CoffeeScript to ES6 using a handy tool named [Decaffeinate](https://github.com/decaffeinate/bulk-decaffeinate) which has worked surprisingly well! Check it out if you’re in a similar situation.

So goodbye CoffeeScript. It’s been fun, but I have another love, and it’s a standardised one.