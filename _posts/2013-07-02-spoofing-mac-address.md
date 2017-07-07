---
layout: post
title: Spoofing mac address
tags: [osx, python, network]

category: blog

---

another tool that i use for covering my ass from tracking beside my tunnel tool, i use [spoof-mac](https://github.com/feross/SpoofMAC), a python library that can be called from your lovely terminal, you could install it via `pip install SpoofMAC`.
run `sudo spoof-mac randomize wi-fi` and you'll get a random mac address assigned to your ether. you could set the spoof-mac to run everytime you boot up your machine and before joining the network (see their github project).

or maybe if you don't want to install spoof-mac you could always use good old fashion `ifconfig` by runnning this command `sudo ifconfig en0 ether xx:xx:xx:xx:xx:xx` (remember, use hex for macaddr). or you can use a generated value by using this `openssl rand -hex 6 | sed 's/\(..\)/\1:/g; s/.$//'`
