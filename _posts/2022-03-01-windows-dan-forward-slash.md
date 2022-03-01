---
layout: post
title: "Dailyfound: Kenapa Windows menggunakan backslash"
tags: 
    - writing
    - development
        
category: [geeking]
comments: true
published: true
page_type: long
image:
    teaser: "/images/posts/yasin-hosgor-MUjep_e-YuY-unsplash.jpg"
    feature: "/images/posts/yasin-hosgor-MUjep_e-YuY-unsplash.jpg"
    author: "Yasin Hoşgör"
    creditlink: "https://unsplash.com/photos/MUjep_e-YuY"
    url: false
---

Melihat tautan ini dari Twitter di group Telegram.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">I heard Microsoft tried to change the file path separator in Windows, but it received tons of backslash from the community</p>&mdash; Aaron Patterson (@tenderlove) <a href="https://twitter.com/tenderlove/status/1498354428734107649?ref_src=twsrc%5Etfw">February 28, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

Untuk yang *tau* dan mengerti perbedaan sistem operasi antara Windows dan Unix-*like*, contohnya GNU/Linux, macOS, BSD dan lainnya, lelucon mengenai kenapa Windows di-commandline menggunakan *backslash* untuk pemisah direktori daripada forward slash seperti sistem operasi lain.

> Most of the utilities included with DOS were written by IBM, and they used the / character as a “switch” character. You can still see this today in the command prompt — running the command dir /w tells the dir command to run with the wide list format option, while running the command dir c:\ tells the dir command to list the contents of drive C:\. The different types of slashes here indicate whether you’re specifying an option or a directory path. (On Unix, the – character is used instead of the / character to indicate switches.)

Untuk yang penasaran, ini karena forward slash sudah dipakai untuk kebutuhan lain didalam sistem operasi tersebut, dan drive mapping/direktori menjadi menggunakan forward slash.