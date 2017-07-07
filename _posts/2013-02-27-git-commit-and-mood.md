---
layout: post
title: Git commit and mood
tags: [life, codes, scm]

category: blog

---


many developers push their code to git repo with funny or sometimes silly comments (i do that sometimes) like this [whatthecommit](http://whatthecommit.com/) site, but maybe it will be more hips (like hipsters do) if i can fetch last.fm api from current listened music and add them to my commit message.

here's the idea

`$ git commit -m "fixing some bugs $(last_fm)" `

the last command is to insert my last.fm current track.
so if we browse the log it will be shown `"fixing some bugs while listening to U2 - Stay"`. if i don't listened any track it will return `"with no music"` (or any other message).

**update 2013-03-05**

![hispter geek](http://i.imgur.com/93x0bpc.png)


here's the [gists on github](https://gist.github.com/dedenf/5097395) of course
