---
layout: post
title: Hipsterized commit
tags: [ git, fun]

category: blog

---

After adding current listened track into my commit message, now i'm adding the action, i take picture everytime commiting something. here's how.

- get ImageSnap
 `brew install imagesnap` or `port install imagesnap`
- create this hook at your project .git/hooks/

the hook

    #!/bin/bash
    COMMITID=$(git rev-parse HEAD)
    imagesnap -q -w 1 .gitsnap/$COMMITID.jpg`

  save as post-commit (so it will run after commit)
