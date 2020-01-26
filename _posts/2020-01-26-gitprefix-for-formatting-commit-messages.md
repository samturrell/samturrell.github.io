---
layout:     post
title:      Gitprefix - Automatically formatting commit messages
date:       2020-01-26
summary:    Git precommit hook for appending branch and emoji prefixes 
---

At work, part of our code standards means we are asked to prefix our branches and commits with the ID of the Jira issue we're working on. This allows our Jira instance to hook into our activity on Github. 

When you're working away on a few different issues, sometimes it's easy to forget to add this to each commit. To combat this I had been using a git pre-commit hook to prepend the branch ID to each commit for years. When I updated my mac to Catalina last year I performed a fresh install and subsequently lost this script, so I decided to recreate it, with a few additions of my own. 

I believe the original script was written in bash, and was extremely difficult to build on if I ever wanted to. Being a primarily frontend developer, it made sense to write this in javascript, or more specifically node. After a bit of research and poking I managed to get it built in a fairly short amount of time, and have been using it ever since.

Recently I was asked if it was available anywhere for anybody else to use, and obviously it wasn't as I'd built it to solve a problem of my own. This weekend I decided to change this and packaged it up. Rather than just stick up a gist and let people manually add it to their templates, I decided a CLI was the best choice to handle the automatic installation and update.

Introducing [gitprefix](https://www.npmjs.com/package/gitprefix)!

Gitprefix does a couple of things. Firstly it covers the functionality of the original script I used, and parses the branch you're on and prefixes the current commit message. A simple example of this would be, say you're on a branch named `task/ABC-123`, and ran the following command `git commit -m"Updated header text"`, the actual commit message would be logged as `ABC-123 - Updated header text` without any additional work from you.

The second feature of this formatter is something I'd wanted to do for a while. I wanted to easily and visually distinguish the type of change in a commit via emoji's, much like the [gitmoji](https://gitmoji.carloscuesta.me/) project.

Currently the formatter doesn't handle all of the different types of changes, but does handle a number of them, as listed in the table below. 

| Emoji | Text trigger | Description |
| ----- | ------------ | ----------- |
| 🔧 | `fix` | Fixing something |
| 🚧 | `wip` | Work in progress |
| 🐛 | `bug` | Related to a bug (often paired with fix) |
| 🔨 | `refactor` | Performed a refactor |
| ⏪ | `revert` | Reverted a change |
| 👌 | `pr ` | Changes based on PR comments |
| 🎉 | `initial commit` | Initial commit of the project |
| 📱 | `responsive` | Responsive changes |
| ♿️ | `accessibility` | Accessibility updates |

The way this works is by finding the text trigger in the message of the commit and appending the relevant emoji. Nothing clever, but it gets the job done.

The list is far from extensive, but does the job for now.

You can install the formatter extremely easily by running the following command:

```sh
npx gitprefix install
```

If you'd like to contribute, you can check out the source code [here](https://github.com/samturrell/gitprefix).
