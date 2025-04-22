---
layout: post
title: 'Slow death for RSS?'
tags: 
    - review
    - software
    - rss
category: [blog]
comments: false
published: true
page_type: long
image:
    teaser: "https://images.unsplash.com/photo-1546422904-90eab23c3d7e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1200&q=80"
    feature: "https://images.unsplash.com/photo-1546422904-90eab23c3d7e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1200&q=80"
    author: "Filip Mishevski"
    creditlink: "https://unsplash.com/@filipthedesigner"
    url: true
---

Kinda disappointed that it seems [RSS](/2024/05/looking-out-for-rss-reader-in-windows) or Atom [feeds](/2019/10/aplikasi-reeder-sebuah-review-singkat) are no longer a thing, quite few sites have stopped providing feed, I have quite extensive feeds collection,ranging from personal blogs, news sites, and even some of the big tech companies, many of which talk about tech, finance amongst other things, I look upon few sites, for instance:

- [Airbnb Engineering Blog](https://airbnb.io/)
- [Uber Engineering Blog](https://www.uber.com/en-ID/blog/jakarta/engineering/)
- [Google Developer Blog](https://developers.googleblog.com/en/)
- [Shopify Engineering](https://shopify.engineering/)

Above sites did not provide [RSS feed](/2017/11/1on-rss), it's easier to read on the RSS reader rather than opening up the site, it's also easier to subscribe to the RSS feed, and get notified when there's a new post.

Not every site put a link tag to provide a feed `<link />`, like this `<link rel="alternate" type="application/rss+xml" title="" href="" />`, so RSS reader could find the appropriate feed URI, and subscribe to it, some site did not provide this tag, so I have to open the source and look for the feed link (it can be rss, atom or json feed format).

Not sure whether sites abandoning RSS feed or simply they wanted people to visit the site to read the post in the [browsers](/2023/10/benchmark-browser), might be because they can't measure the engagement of the post, it's quite hard to put some kinda [analytics](/2023/11/user-profile-finger-printing) on RSS feed, even though there's service like [Feedburner](https://feedburner.google.com/) who can do that, but it's another hassle for someone or company to configure, it's easier to install analytics on the website obviously.

Anyway, you can subscribe to my RSS feed, [here](https://feeds.feedburner.com/dedenf/notes-feed).