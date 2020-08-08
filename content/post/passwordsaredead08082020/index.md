---
title: "Passwords are dead... now what?"
date: 2020-08-08T11:24:55-05:00
description: "A repost of an article I wrote over eight years ago on Neowin.net. Nothing much has changed, and although two-factor authentication is starting to gain traction, it's nowhere near as ubiquitous as it should be."
categories: ["technology","infosec"]
toc: false
displayInmenu: false
displayInList: true
draft: true
dropCap: true
resources:
- name: featuredImage
  src: "passwordlock.jpg"
  params:
    description: "A lock with the word password on it"
---

Reposted from an article I wrote for [Neowin.net](https://www.neowin.net/news/passwords-are-dead-now-what/)
on June 7th, 2012...  Over eight years ago... And most of it still holds true. The only piece I would modify
today would be to downplay the use of SMS as SIM Swapping is a real threat, and is the reason why NIST 
released [Special Publication 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html), depricating the use
of SMS as a means of MFA.  

Enjoy a piece of history that is still an issue today.

-----
It seems that our cyber-identities are constantly under attack and the recent password leaks from high 
profile sites like LinkedIn, eHarmony, and last.fm are signaling the fact that our data in the cloud is 
not as secure as some had hoped. Most people use dozens, if not hundreds of different websites and keeping 
track of all of these logins is difficult. The result is that many people use the same password on multiple 
sites, compounding the criticality of these security breaches. So what's the solution?

The first issue is that companies need to do a better job protecting our data and especially our security 
credentials. The fact that LinkedIn never salted the password hashes has made the task of cracking passwords
infinitely easier. The salt would've had minimal overhead to LinkedIn and would've gone a long way to 
reducing the impact of the breach. In addition, there are many tools available that help organizations 
detect and stop these types of attacks. While at HP Discover, we've seen several good offerings that would 
also help an organization know that they were under attack. From tools like HP Fortify that tests application
security to Tipping Point for network monitoring to ArcSight for information analysis, there are 
applications and processes that can be put into place to help prevent these leaks from happening in the 
first place.

Having said that, no system is 100% secure; breaches will happen and passwords will be released. So is the 
password a dinosaur, a relic from the past that has outlived its usefulness? And if so, how should we be 
protecting our identities?

One way is to have a central password safe that all sites rely on for authentication. This is something that 
Facebook as a platform is offering. Indeed, you can even login to Neowin with your Facebook account if you 
so choose. This has the benefit of allowing you to pick an ultra-secure password and not risk forgetting it.
It also means that you can hopefully rely on the universal platform to properly store and secure your 
credentials in such a way that even if they are compromised, the actual data can not be read. However this 
seems to be a poor idea overall for many reasons, not the least of which is that if history has proven 
anything it's that no system is safe. Indeed, putting all of your valuables in a single repository just means 
the bad guys will focus their fire at that target.

Another idea is to use a token in your possession that constantly changes. Sites like eBay and World of 
Warcraft already provide this functionality and it's a good way to help secure your identity. Even if 
someone steals your password, they can't login as you without the token. This isn't a foolproof solution 
though, as last year's attack on RSA proved, but it's another layer of protection (called two-factor 
authentication) that is a step in the right direction. Unfortunately this doesn't scale well if you have to 
carry 100 tokens around on your key chain in order to access the web.

Perhaps the best solution would be to tie access information into your mobile phone. More and more people 
are using smartphones, so instead of a token, sites could provide an app for your phone or perhaps send an 
SMS message that contains a passcode to you. The downside is that more companies would have access to your 
phone number and if you lose your device, you increase the chance of allowing anyone to access your data on 
the web, but this might be a better solution than having poorly secured passwords that attackers can easily
obtain.

Do you think the age of the password is nearing an end and that we need something more secure? Or are you 
not concerned about most of the data sitting out on the web anyway?

Image by [Gino Crescoli](https://pixabay.com/users/absolutvision-6158753) from [Pixabay](https://pixabay.com)

