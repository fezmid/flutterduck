---
title: "Breaking Docker and Kubernetes"
date: 2020-08-07T19:44:48-05:00
description: "Some high leven stuff I learned at Black Hat 2020 about breaking out of containers."
categories: ["technology"]
toc: true
displayInmenu: false
displayInList: true
draft: true
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

