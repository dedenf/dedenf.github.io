---
layout: post
title: 'Zev'
tags: 
    - review
    - software
    - artificial intelligence

category: [blog]
comments: false
published: true
page_type: long
image:
    
---

Stumbled [this tool, `zev`](https://github.com/dtnewman/zev), when browsing Github, a tool that we use in the Terminal to remember which command needed to do certain things, or discovering 'new' command that you might did not know before, it uses Natural Language Processing to interpreting our query.

For NLP it uses various LLM provider, currently it support OpenAI, Gemini, Ollama, and Azure OpenAI, Zev will connect to one of the LLM vendor using our API key (it connect through their API), in my case, i’m using Gemini.

The installation quite simple, since it use python, and the project owner already distributed the package via `pip`. 

#### Install

`pip install zev` and that’s it! in my case i use `venv` for environment management, create the env first and then install it there.

#### Usage

To use `zev` it’s easy, in the terminal, just call zev, at first it will ask you which provider you wanted to use?

![](/images/posts/zev1.png)

In my case, i use Gemini, so i type `gemini` and it will ask for API key.

![](/images/posts/zev2.png)

After all of that finished, call `zev` again, there’s a prompt asking what you want to find, just type your question, mine look like this.

![](/images/posts/zev3.png)

After that, you will get answer based on your query, and if the command you want to remember or discover, `zev` will give you option(s), just select with your arrow key, and the command ready to be executed. 