---
layout:     post
title:      Automated Pull Request Checks on Github
date:       2018-11-26
summary:    Using Probot to create automated checks on Github Pull Requests
---

There aren’t many jobs out there where you have the direct ability to make your day to day tasks more efficient. This is part of what makes being a developer so great. Problem solving is our jam. We can identify problems and simplify them or automate them entirely.

As a lead, one of my duties is to approve and merged Pull Requests on GitHub. A task that can take long enough in itself (depending on the size of the PR) without the semi-frequent back and forth involved in making sure appropriate guidelines are followed. With the beta launch of [GitHub Actions](https://github.com/features/actions) a couple of weeks ago, it seems like as good a time as any to start looking at this area and see how we can streamline this process.

So, some of the problems:
* Titles not following the correct format
* PR template not being adequately filled out
* Users not reviewing their own code before submitting
* Debug code left in
* Make sure WIP branches cannot be merged
* Etc, etc.

Don’t get me wrong, these things don’t happen all the time, but all of these can be automated out of existence before we even come to check the PR. This means that merges are not needlessly delayed, and our Project Managers don’t get twitchy. So how do we do that?  Well, if you’ve ever used Travis or similar CI tooling you’ve probably seen how “Checks” are used to prevent PRs being merged until the test suite has passed or the assets have been built. Seems to be the perfect functionality for most of our problems.

<figure class="image">
    <img src="/images/github-travis-checks.png" alt="Travis CI Checks on Github">
    <figcaption>Travis CI Checks on Github</figcaption>
</figure>

The handy GitHub REST API allows us to achieve everything we need here, and even better than manually calling multiple endpoints there is an entire framework for building GitHub apps to install your integrations across your entire organisation. Check out the docs for [Probot](https://probot.github.io/) if you’re interested in building one yourself.

As it was my first time using Probot I decided to start with a simple one: PR Titles. There are only two things required in a title. The Jira task identifier and a short description of the changes.

The plan:
* When a PR is created we’ll run a check
	* Webhook via Probot ✅
* Check that the title matches the format
	* JavaScript logic ✅
* If the check fails leave a comment on the PR for the user to fix
	* GitHub API via Probot ✅
* When the PR is updated we’ll check again
	* Rinse and repeat ♽

Probot was incredibly straight forward to use and within a few hours I had the had completed the app, with a full test suite on all possible title variants using jest and nock (again, Probot made this almost effortless).

Deployment of your bots is documented as being incredibly simple, but in my experience it was a bit of a pain. However I put this down to never having used now.sh before and a recent major bump in their version that didn’t play too well with the setup. I downgraded to the earlier major and it was a lot more pleasant.

There’s still some work to be done to iron out the kinks, but this initial app makes me excited to expand on our automation in this area. Hopefully we can build up a comprehensive suite of checks to make everything run just that little bit smoother.

If you’d like to check out the code for the App, you can do so [here](https://github.com/netsells/probot-pr-title-check).
