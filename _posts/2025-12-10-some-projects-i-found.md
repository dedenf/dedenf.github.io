---
layout: post
title: 'Some projects I found interesting'
date: "2025-12-10"

tags: 
    - software
    - projects
    - daily found
    - development
    
category: [blog]
comments: false
published: true
page_type: false
image:
---

Somtimes you can found some interesting projects on GitHub. I was looking for something to help me with my daily tasks, and found these projects, mind you these projects was packaged using docker, so it was easy to run on my mac or any other machine that support containerization.

#### 1. [Bento PDF](https://github.com/alam00000/bentopdf)

#### 2. [Actual Budget](https://github.com/actualbudget/actual/tree/master)

#### 3. [Wallos](https://github.com/ellite/Wallos)

#### 4. [Beszel](https://github.com/henrygd/beszel)

#### 5. [Dawarich](https://github.com/Freika/dawarich)

#### 6. [Linkwarden](https://github.com/linkwarden/linkwarden)

You can try all of the app directly from the docker hub, just run the following command:

```bash

docker run -d --name bentopdf -p 3000:8000 bentopdf/bentopdf:latest

```

or if you are using Podman as your container runtime, you can run the following command:

```bash

podman run -d --name actual -p 3000:8000 bentopdf/bentopdf:latest
``

