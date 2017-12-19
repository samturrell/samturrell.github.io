---
layout:     post
title:      Progressively Infiltrating Google
date:       2017-12-19
summary:    Attending the Google Academy for a course on Progressive Web Apps
---



Last week myself and a colleague had the opportunity of attending the Google Academy in London for a course on Progressive Web Apps. I’ve built a progressive website before (see the [Netsells website](https://netsells.co.uk/)) using a framework that did all the hard work for you behind the scenes, so I was looking forward to seeing how you would go about implementing features such as offline mode yourself.

<div class="media-right media-50-width">
<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-permalink="https://www.instagram.com/p/BcrjAM0HPF-/" data-instgrm-version="8" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px;"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50.0% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAMUExURczMzPf399fX1+bm5mzY9AMAAADiSURBVDjLvZXbEsMgCES5/P8/t9FuRVCRmU73JWlzosgSIIZURCjo/ad+EQJJB4Hv8BFt+IDpQoCx1wjOSBFhh2XssxEIYn3ulI/6MNReE07UIWJEv8UEOWDS88LY97kqyTliJKKtuYBbruAyVh5wOHiXmpi5we58Ek028czwyuQdLKPG1Bkb4NnM+VeAnfHqn1k4+GPT6uGQcvu2h2OVuIf/gWUFyy8OWEpdyZSa3aVCqpVoVvzZZ2VTnn2wU8qzVjDDetO90GSy9mVLqtgYSy231MxrY6I2gGqjrTY0L8fxCxfCBbhWrsYYAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div> <p style=" margin:8px 0 0 0; padding:0 4px;"> <a href="https://www.instagram.com/p/BcrjAM0HPF-/" style=" color:#000; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none; word-wrap:break-word;" target="_blank">I have successfully infiltrated Google. First google, then the world.</a></p> <p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;">A post shared by <a href="https://www.instagram.com/samturrell/" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px;" target="_blank"> samturrell</a> (@samturrell) on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2017-12-14T11:08:29+00:00">Dec 14, 2017 at 3:08am PST</time></p></div></blockquote> <script async defer src="//platform.instagram.com/en_US/embeds.js"></script>
</div>

The course was a two-day event in the centre of London at the old Google offices, now repurposed and known as the Google Academy, lead by Edsel Tham a Senior Learning consultant from QA. Edsel was extremely energetic and entertaining and was great at keeping attendees engaged in the course material which is amazing considering it was his 14th session covering this particular course material.

The general goals of the course were the following:
* Understand benefits of Progressive Web Apps
* Be familiar with PWA design principles, technologies and tools
* Learn how to build a resilient mobile web app and integrate tooling
* Register and install a service worker for offline functionality and high performance

Our group was one of the smaller groups that the course leader had taught, with ~24 of us vs a usual 50 or so. There was a few people from the BBC attending the course (iPlayer team I believe) but mostly small agencies or freelance.

Day one kicked off with a quick ice-breaker exercise where we would split into groups of around 5 and complete a couple of quick fire challenges with the fastest teams being rewarded with chocolate. You could feel the social anxiety in the room when trying to find 5 things in common with the strangers in your team (my team were all spaces on the tabs vs spaces debate, so that made me happy) but we just about made it through

The course claimed to be aimed at beginner-intermediate developers which was quite obvious with what we were learning on day 1. We covered things such as responsive design, responsive images and promises. Pretty simple stuff.

Lunch was provided by way of a buffet table that you could help yourself to. The food was pretty standard but nothing to complain about, and I definitely ended up having too much of it.

Day two was much more of what I was looking for, delving into the inner workings of service workers and how to achieve different caching techniques depending on the requested resource. I’ll go into my learnings here in a separate, more technical post later, but it’s safe to say I will definitely be working them into my workflow and all future projects my team works on.

<div class="media-centre media-50-width">
<blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/BcuHF9Ln52r/" data-instgrm-version="8" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px;"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50.0% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAMUExURczMzPf399fX1+bm5mzY9AMAAADiSURBVDjLvZXbEsMgCES5/P8/t9FuRVCRmU73JWlzosgSIIZURCjo/ad+EQJJB4Hv8BFt+IDpQoCx1wjOSBFhh2XssxEIYn3ulI/6MNReE07UIWJEv8UEOWDS88LY97kqyTliJKKtuYBbruAyVh5wOHiXmpi5we58Ek028czwyuQdLKPG1Bkb4NnM+VeAnfHqn1k4+GPT6uGQcvu2h2OVuIf/gWUFyy8OWEpdyZSa3aVCqpVoVvzZZ2VTnn2wU8qzVjDDetO90GSy9mVLqtgYSy231MxrY6I2gGqjrTY0L8fxCxfCBbhWrsYYAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/BcuHF9Ln52r/" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A post shared by samturrell (@samturrell)</a> on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2017-12-15T11:02:20+00:00">Dec 15, 2017 at 3:02am PST</time></p></div></blockquote> <script async defer src="//platform.instagram.com/en_US/embeds.js"></script>
</div>

The group was split into teams of 3/4 to complete a “Pub Quiz” to test our knowledge of what we had learned on the first day of the course. I was given the initial task of assigning ourselves with a team name. My suggestion of “Santa’s Little Service Workers” was met with groans from my fellow team members, but it was festive and on topic so it stuck (and it got the most laughs when we read it out, so I’ll count that as a win). We ended up winning the Quiz with 25 points with the majority of teams achieving 23 points. I’d like to think it was down to me being an absolute nerd and memorising the viewport meta tag, earning us a solid 3 points. We were awarded “limited edition smarties” - I’m pretty sure they were just off-brand smarties rip-offs, but I’ll allow it.

To finish the day there was a “hackathon” of sorts where we would get some hands on experience implementing everything we learnt so far on a basic web app. The group was split into teams of 3/4 and given ~30 minutes to complete the task. The app was a basic static e-commerce website that needed to work offline via caching and the ability to pin to the home screen on mobile devices. After a painfully long `npm install` (where’s my `yarn.lock` file at, Google?) we were away. The task took us around 12 minutes to complete and we ended being the first group to finish by quite some margin, with some groups not managing to finish at all. Winning the hackathon earned us a QA branded drawstring bag, but as it was the last time the course was running everybody ended up with one anyway.

I learnt a great deal from the course and will definitely be using a lot of it in practice very soon. I will also be passing on the knowledge I have gained to other members of my team so that they are also able to utilise it.

_![Google PWA Course Group](/images/google-pwa-group-shot.jpg)_