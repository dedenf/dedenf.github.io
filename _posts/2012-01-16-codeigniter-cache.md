---
layout: post
title: Codeigniter Cache Tips
tags: [php, cache, codeigniter]

category: blog

---

Cache system in Codeigniter is a quite nice feature, thanks to its modular system, you can add more than just a built in cache system, you can add your own.

if you want to make an app with search feature, if you don't implement cache feature in it, the app will always ask the database whether it has the data or not, this could make your database work for just a 'historical' data.
to make things faster, use cache. to get this cache (even it's in-memory or in-file cache) work, you could make a GET method (or if you have to use POST, that's ok, will work too) and create a [URI](https://en.wikipedia.org/wiki/URI) for that search.

for example, if you want to cache a user information, just put ?key=user_name in URI, so that the URI will be saved as cache by your app (of course you must enable the cache system on config file!).

"what if the user information is changed?", yes, if the user information is changed your cache will be something  to blame if the information is not updated instantly. to make this work, just delete the cache if there's a update action in your module, with that you'll get the same result after its get updated
