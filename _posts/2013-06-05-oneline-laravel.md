---
layout: post
title: Installing Laravel 4, oneliner
tags: [php, laravel, composer]

category: blog

---

downloading package or setup composer.json could become a hassle.
instead, just go with this one line of command on terminal. make sure you already installed composer and put it in the system wide bin (eg. /usr/local/bin/).

    $ composer create-project laravel/laravel

this command also work if you want to setup a new package on composer packagist repo. for example installing Slimframework `composer create-project slim/slim`
