---
title: "Breaking Docker and Kubernetes"
date: 2020-08-07T19:44:48-05:00
description: "Some high level stuff I learned at Black Hat 2020 about breaking out of containers."
categories: ["technology","infosec"]
toc: true
displayInmenu: false
displayInList: true
draft: false
dropCap: true
resources:
- name: featuredImage
  src: "DockerAndKubernetes.png"
  params:
    description: "The docker and kubernetes logos"
---
I have been in IT for a long time (20+ years), but have never had any hands on experience with containers.
Conceptually, I understand what they are and how they work, but since I've never had to implement them,
I wasn't sure how it worked. In addition, I had no idea how to actually secure them. Again, the concept
sounds great, but the old adage of "as security increases, usability decreases" sat in my head, and 
with how EASY everything container-related sounded, it also seemed like security was going to be an 
afterthought.

Turns out I was right.

To get up to speed, I signed up for the Black Hat 2020 session entitled,
["From Zero to Hero: Pentesting and Securing Docker Swarm and Kubernetes Environments."](https://www.blackhat.com/us-20/training/schedule/listing.html#from-zero-to-hero---pentesting-and-securing-docker-swarm--kubernetes-environments-19045). The course, taught by [Sheila A. Berta](https://twitter.com/UnaPibaGeek) and 
[Sol Ozzan](https://twitter.com/encodedwitch) literally started with a description of how Docker
containers worked and went all the way through a Kubernetes deployment. It was entirely hands on - students
were required to install Docker and [microk8s](https://microk8s.io/) on their own machine before the class -
and was a great way to see how the tools communicate, where the weak points are, and most importantly, how
to try locking it down.

Unfortunately, while the course says you'll be a "hero" at the end of two days, I feel like I am just
starting down the road and have a lot more to learn. That said, I wasn't going into it expecting to be an
expert after only 16 hours of training.

Below are some of my takeaways from both a Red Team and Blue team perspective.

## Red Team

**Most containers run things as root**

This means if you compromise a host, you'll probably have full control of the container. That makes the
following steps a lot easier.

**The docker.sock Bind Mount is dangerous**

If you're root in a container and install Docker in a container that has a Docker socket
(var/run/docker.sock), you'll be able to inspect the entire cluster, including getting a shell inside of any
other container. At that point, none of the network segmentation or other controls will prevent access.

**Environment variables often contain secrets**

In many cases, people send passwords into the container using simple environment variables. So if you have
access to the account, you can see the environment variables and further expand your powers.

**The Docker API can give a lot of information**

The Docker API, by default, is unauthenticated and can expose a lot of information. Using Shodan, you can
easily find a list of open ports and from there, can get details about the cluster and pivot to taking it
over completely. [Trend Micro has an interesting blog post about the topic](https://blog.trendmicro.com/trendlabs-security-intelligence/exposed-docker-control-api-and-community-image-abused-to-deliver-cryptocurrency-mining-malware/).

## Blue Team

**Don't run things in the container as root**

While it's easy to run things as root, you shouldn't do it. Instead, run applications with lower permissions
by mapping the UID. I need to look into this further, as I didn't fully understand the "how" piece of the
advice.

**Don't let containers install things**

Almost every attack started with us installing something. From nmap to ifconfig to Docker itself (within 
the container), installation of something in the container was a common thread. This is why you should 
always block any unused ports at your boundary. This also helps prevent Command and Control communication
if someone does infect your machine.

**Protect the Docker Socket**

The Docker socket is how communication is handled between container and cluster, so it must be protected.
While I won't go into detail here (mostly because I'm still new and don't want to give bad information),
the Docker webpage has what appears to be a
[great article detailing how to lock it down](https://docs.docker.com/engine/security/https/).

**Use Docker Secrets instead of environment variables**

Docker Secrets has [been around since 2017](https://www.docker.com/blog/docker-secrets-management/). 
While not fool-proof, it's still better than using environment variables to pass secrets.

This is just a high level view of Docker (and most of this applies to Kubernetes as well). In the future, I
might try to write a more technical article on the topic, but since I'm still digesting the topic myself,
and there are far better resources available online, I'll leave this fairly high level. If you take nothing
else away from this article, just remember this: A lot of work goes into securing containers, and if you
select the defaults, as with most technology, you're probably exposed.
