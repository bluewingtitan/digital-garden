---
title: "Something about complexity, simplicity, and hope."
description: "After years of watching overcomplicated systems collapse under their own weight, I learned to believe in simplicity. Here's why your blog doesn't need a cluster, and why file systems will outlast us all."
date: 2026-03-08T20:16:00Z
author: bwt
tags:
  - minimalism
  - software-engineering
  - web-development
---

> An idiot admires complexity, a genius admires simplicity  
> ~ Terry A. Davis

Having spent the last 7 or so years working in software development (which might not be a lot by your standards, but I started with 18, so...), I have developed quite a few strong feelings about this topic. I have seen mountains of distributed systems rise and fall. I have seen talented engineers shifting them around. I have seen people, how they invented new tooling to keep the ever growing pile manageable. Creating services on top of services on top of… - you get the gist. Then adding some meta-services to keep some of the more hidden ones monitored and well.

I have seen Kubernetes clusters hosting a few static files. Content management systems hosting a few markdown files. Handwritten, custom registries distributing patches that should have been included in the published binary itself.

I have seen them rise, and ultimately - I have seen them fall. Crushed under their own weight, collapsing and bringing down systems their stakeholders better had a backup for.

When I started, I admired them. I mean have you seen [JDSL](https://thedailywtf.com/articles/the-inner-json-effect)? _Like I said, Tom is a genius._

But time shaped me to believe in everything modern tech is not: Simplicity.

Modern hardware is _wicked fast_. You don't need a cluster to serve a few hundred to thousand requests per second. Chances are, that you don't need a CDN or microservices running stateless lambdas. If one well polished, monolithic server is enough to handle the biggest traffic spikes your usecase could ever dream of, you don't need automatic scaling, or load balancing.

And you don't need a CMS to manage text content. Or images. There is a solution for this that was established in the 60s! It is used by almost every server around the world and even by the system you are reading this on right now. It's called a **file system**. I have a floppy disk from the 80s formatted in FAT32. It contains some files in ASCII. Even though it's over 40 years old now, I can still just read everything on there just by inserting it into a reader attached to my modern system. And I will be able to do so in another 40 years, given that the disk itself lasts that long. Try that with your Wordpress installation. Or anything binary for that matter. Yes, backwards-compatibility lives long, but 40 years is a different time frame. There is a chance it'll work, but would you trust that chance enough to risk all of it? Will anyone even bother untangling that mess of bytes once you are gone?

For any data even remotely important to me, I prefer a standardised file system with files using well-established encodings any day of the week. There are multiple orders of magnitude more people relying on it working until long after I am dead than there are people on the planet ever having visited a Wordpress page, not even speaking of managing one. Because I know that if there is humanity with computers in 200 years, chances are they will know how to mount ext4 and read UTF-8.

<br/>

When I started my first blog, I got myself a free Wordpress webspace. Because of course I would. Lost in the magnitude of options, I clicked together something that worked and then ultimately stopped. Because I wasn't writing a blog, I was designing the framework for a blog. So much so, that I spent almost none of of my time writing.

When I realized this trap, I wanted to get the posts I've already written out of there. But that wasn't easy, especially not in a format I could just transfer.

I moved over to ghost. I enjoyed their propositions. Markdown-based? Sign me up. But then, I started developing a frontend, and lost myself again in a Vue.js project that was just getting way too big for a small side-project with a focus on writing the blog itself.

So I sat down for two days to ultimately solve this problem in the simplest way possible.

This little corner of the internet is defined by a few markdown files and a single html template. And a simple server ([5000blogs](https://github.com/5000K/5000blogs)) combining them. There is no database I manage. Literally no input OR output besides a config file, the markdown files I author, and a simple, static template. I could move to any markdown-based static page generator, or to something new entirely. I could put my blog into Obsidian Publish, or on GitHub Pages if I get sick of the current solution. I am ultimately free.

Because **obviously** there is no reason you should **ever** need more than that to serve a blog with some basic functionality like tags, automatic content updates via git and some quality of life like a full-text search. The web page you are looking at has literally no javascript, and that's by design. When you load the page, you send a basic GET request and my server answers with a single file. And once that is done, nothing and nobody will ever know that you were here. There is a certain peace in that.

Anyways, I am me, and I am here now. Hello.