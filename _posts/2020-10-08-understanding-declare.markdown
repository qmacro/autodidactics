---
layout: post
title:  "Understanding declare"
date:   2020-10-08 06:24:11 +0100
---
_I've been looking into declare, and also how it compares to typeset and local._

Sometimes you discover a treasure trove of content to look through and learn from; [Mr Rob](https://rwx.gg)'s [dotfiles](https://gitlab.com/rwxrob/dotfiles/-/tree/master) is one such thing. Looking at just a small script like `ix` brought forth three posts:

- [Using exec to jump](/autodidactics/2020/10/03/using-exec-to-jump/)
- [curl and multipart/form-data](/autodidactics/2020/10/04/curl-and-multipart-form-data/)
- [Checking a command is available before use](/autodidactics/2020/10/04/check-command-available/)

I've now turned my attention to the [`twitch`](https://gitlab.com/rwxrob/dotfiles/-/blob/master/scripts/twitch) script which he uses during his [live streams](twitch.tv/rwxrob). I don't get very far until I light upon this section:

```sh
declare gold=$'\033[38;2;184;138;0m'
declare red=$'\033[38;2;255;0;0m'
declare grey=$'\033[38;2;100;100;100m'
```

Now, there's a keyword that I've seen before but never fully understood or embraced. Seems like this is a good time to fix that.

So `declare` is a builtin, which means that rather than it be an external executable (such as `echo`, or even '[)
