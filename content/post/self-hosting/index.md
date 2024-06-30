---
title: "Self-Hosting Series on Neowin"
date: 2024-06-30T17:41:10-05:00
draft: false
description: "I've started a series about self-hosting. What is it? Why would you want to do it? And most importantly, step-by-step guides to do it and start learning from it. Check it out!"
categories: ["technology"]
toc: false
displayInmenu: false
displayInList: true
dropCap: true
resources:
- name: featuredImage
  src: "SelfHostedAIGenerated.jpg"
  params:
    description: "An AI generated image of a person in space with computers around them."
---
I thought I'd use Flutterduck more than I am, but... it's still nice to have my own little space on the Internet to do things I want to do on.
Even if I only do them once a year apparently...

I could spend time talking about the Bills' last season - lost to the Chiefs in the playoffs, again... - but instead I want to focus on technology.
Specifically, I've started series on Neowin that focuses on self-hosting. Back in the day, I used to self-host (before it was called that) my own
web server, Nethack server, and email server. However as my responsibilities have grown and my professional role changed to a managerial one, I found
I wasn't touching technology as much as I wanted to. That led me to start building some of my own projects at home.

A few years ago, I decided to ditch DirecTV, so put up an antenna, [built a Plex server on a Synology NAS, and used HDHomeRun to get local channels](https://www.neowin.net/news/synology-plex-and-hdhomerun-how-to-cut-the-cord-forever/). It was the best thing ever and has worked great - even my
family can seamlessly use it.

But I wanted to do more playing around. I took an old HP Microserver Gen8 I had laying around, upgraded the CPU, put an old SSD in it, and installed
Proxmox. Worked, but was litle kludgy because the hardware was so old.

Then I received a miniPC from AceMagic and decided to try installing Proxmox again. That worked much better (except there's no ILO...). I played 
with some VMs, using Synology storage as the base. I was having fun!

That got me thinking that there were probably a lot of people out there who wanted to try self-hosting but just didn't know where or how to start.
So I figured I'd write some guides on Neowin to help people get started. It took awhile to make the time, but I now have three articles done, including
two step-by-step guides, and the first two articles have been published.

The first article is an explanation of what exactly self-hosting is. It also lists many pros and cons as well as many of the things you can do with
self-hosting. Check it out here: [https://www.neowin.net/news/self-hosting-what-is-it-and-why-you-might-or-might-not-be-interested/](https://www.neowin.net/news/self-hosting-what-is-it-and-why-you-might-or-might-not-be-interested/)

The second article is an article explaining what a hypervisor is, followed by  step-by-step instructions on how to install your very own Type 1
hypervisor, Proxmox. Check it out here: [https://www.neowin.net/guides/self-hosting-installing-the-proxmox-hypervisor/](https://www.neowin.net/guides/self-hosting-installing-the-proxmox-hypervisor/)

There will be more later, and you can always get to the entire series by looking for the [selfhosting-guide tag on Neowin](https://www.neowin.net/news/tags/selfhosting-guide/).

I'd love if you checked it out and provided feedback. I hope it helps someone out there!
