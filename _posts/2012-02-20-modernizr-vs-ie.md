---
layout: post
title: Modernizr vs IE
tags: [javascript, ie, web-development]

category: blog

---

Today, i’ve found out something weird, we took an internal launch of our newly developed app that display numerous graph and statistics, it went crash. not the app, but the browser, and you can guess, it’s IE.

From IE6 on XP sp2 until IE8 on windows 7, it all went crash, first i thought about many ‘add-ons’ like Yahoo! websearch (curse you!), and other kind of IE rubbish. i’m heading to the code to look something that might be not right, first i disabled header() from the code, but it’s not it, and the look at the doctype, maybe
`<!--[if lt IE 7]> <html lang="en"> <![endif]-->`,

delete that line, but still it doesn’t work.

ook a shot disabled Modernizr (mine is v2.0.6), and it went ok, that’s the ‘culprit’ behind the IE6-IE8 assasinations, as usual, went to google, stumbling at the Modernizr github repo to see maybe other users experienced the same thing, and yes, there is. many [asking](https://github.com/scottjehl/Respond/issues/27) about the positioning of the Modernizr call, is it before css, or after css calls. the documentation [says](http://www.modernizr.com/docs/#installing) that to install Modernizr is after CSS calls. went to see my code again, it is after CSS calls, a mystery that should be solve, but it’s not, the IE still crashing.

Right now, i just disabled the Modernizr, because can’t find any windows machine right now, too much if i’m firing my VM right now. but i still do believe that placing jQuery and Modernizr is the problem, and some about some CSS3 code that i’ve written, oh they all plotted together to kill our beloved IE.

well, time to write about Sherlock's ending.
