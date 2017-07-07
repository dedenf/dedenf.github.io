---
title: Watching The Watcher
layout: post
tags:
    - development
    - operations
    - rant
---

This is a constant rant, we have a Job Service defined on our stack, using the very simple tool, Supervisor. this awesome tool do its job, but the thing is, our job service is sucks, and it did not cue or trigger anything if the job stuck/stalled, supervisor assumed that everything is working, because the service is still running, but failed to pass the job and execute it.

all we have to do is restarting the job on `supervisor`, guess we should refactoring the job service. *darn!*
