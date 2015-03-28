---
layout: post
title: "An Idiots Guide to Using Jekyll for your Blog"
permalink: idiot-guide-jekyll
---

##Part I: In Which The Idiot Installs Jekyll

It started with a blog post from *[Smashing Magazine](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/)*. 

*Smashing Magazine* is smart and chic. This didn't look to hard and I wanted to hang out with the cool kids. So let's install Jekyll. 

I did a little research and everyone else said it was easy too. My problem was they all know way more about web development than I do and I was really unclear on what "gems" are up to this point. And I still haven't quite figured out how I put a simple string into Terminal and it installs things. As in three little words and my computer magically knows where to go? From Terminal?! If you want lay some knowledge down, talk to me on [Twitter](http://www.twitter.com.heymicky). I would legitimately appreciate it.

Install Jekyll. It's so easy! Ruby is installed on your Mac. Just go:

```
$ gem install jekyll
```

But, um, that didn't work. Because I'm a trusting sort and an optimist, I tried:

```
$ sudo gem install jekyll
```

As an idiot's guide, I should note, when you use "sudo", you're telling the computer you're the super user ("super user do"). It should do whatever you're telling it. If you don't know what you're doing, you can break things.

>I should also mention that you, um, don't have to install Jekyll. If your ultimate goal is to host this site on GitHub Pages, that does all the behind the scenes stuff. Skip to Part II below, fork an existing Jekyll blog, and you can be live in five minutes. You really only need Jekyll if you want to build this website locally, develop from there, and then push it live. If you're like me, you're not getting many hits so you can fumble around a bit on a live site and skip this whole process. But if you're into it, good for you. I did learn something.

The fear of using sudo, according to Stack Overflow was that I'd have versioning problems if I start doing Ruby development and other things I completely don't understand.

Back to installing Jekyll, I plugged the error codes I was seeing into Google. It seemed I was missing a ruby-dev package. With only the faintest idea of what that meant, I plowed forward. 

First I installed Xcode, then Homebrew. I continue to have no idea what either do. Then rbenv, which I believe helps you pick a version of Ruby.

One problem I seem to be having is not having access to the version of Ruby that my Mac OS is using. I tried installing another version of Ruby, using rbenv (I think!). Still no "gem install jekyll". I didn't try sudo because at this point I was legitimately worried about breaking something.

Next stop, rvm, which is a ruby version manager (or something). I installed that and said,

```
$ rvm use 2.2.1
```
 
It said I didn't have it. So I installed Ruby again. At this point, I assume I have three versions Ruby installed, though no idea where to find them.

I try that code again, telling the computer to *use* this version of Ruby. And it seems to work. *Sure, bud.* It said something like that.

```
$ gem install jekyll
```

Finally!

That took about two hours to figure out. 

##Part II: In Which the Idiot Gets His Blog

When you're learning something, you definitely need a lot of small victories to keep you going. Diving into whatever Jekyll is and figuring gems and Ruby meant I probably didn't have the mental stamina to then creat a blog from scratch. So I found templates for Jekyll that used more technology I don't particularly understand. I chose Poole.

Poole is effectively a Jekyll blog preconfigured for you, featuring simple, attractive templates and example posts. It's bare bones but read to me as clean and sophisticated.

But instead of simply forking Poole, through more online research, I found a really helpful blog post by [Joshua Lande](http://joshualande.com/jekyll-github-pages-poole/). He talks about his experience creating a Jekyll blog. He used one of the templates provided by Poole, and made a few of his own customizations that I really liked. On his aforementioned post, he shows you how to add an *Archive* page, comments, and Google Analytics. [In another post](http://joshualande.com/short-urls-jekyll/), he shares how to get "pretty URLs" for his permalinks.

Other than these upgrades, and a different font, Joshua's blog appears identical to one of the themes offered by Poole. To take advantage of his customizations, I forked [his blog](https://github.com/joshualande/joshualande.github.io) instead of a Poole theme.

The *Smashing Magazine* post was helpful in figuring out the forking process. Read [Part 2. Host On Your GitHub Account](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/). The writer helpfully notes common problems. I encountered both common problems #2 and #3 because I didn't follow instructions closely enough. To have this Jekyll blog served by GitHub, you need to create a user website, not a project one. What I didn't understand was when I named my repository, it you must type in *yourusername.github.io*. I was just typing in my username which wasn't enough and broke where the template was pointing.

##Part III: The Idiot Looks Around

This was where the fun started for me, to look through the file structure and learn how Jekyll worked. It's a static site generator, piecing together the pages it ultimately serves by combining separate elements. Jekyll also uses the Liquid, a secure templating language originally developed by Shopify. 

I don't quite know what that means but this bit from [jekyllbootstrap.com](http://jekyllbootstrap.com/lessons/jekyll-introduction.html#toc_16) was pretty interesting:

>Liquid is designed for end-users to be able to execute logic within template files without imposing any security risk on the hosting server... GitHub cannot afford to run arbitrary code on their servers so they lock developers down via Liquid.

I'm familiar with markup, not programming, but the implementation in Poole is basic and fun to explore. And my ignorance meant I was pretty thrilled when I was able to figure something out. For example, I really wanted the dates on the blog posts to display the full month. Alan Smith wrote a [blog post](http://alanwsmith.com/jekyll-liquid-date-formatting-examples) that goes into a wild level of detail about this.  

Beyond that, Poole also includes pretty basic CSS files, so it's easy to personalize the site to your liking.

##Part IV: Wait, Why are We Using Jekyll Anyway, Asks the Idiot

Jekyll is great. It's much simpler than a lot of other bloggin solutions, like WordPress. It's fast and minimal. No need to worry about security because there's no CMS. And GitHub will host it for free and handle version control.

That said, if you're just going to blog a few times a year, you could just create a simple website with similar styling and just post that somewhere, right? Also, Markdown certainly has its limitations.

But I chose to undertake this whole exercise because I wanted to learn something new. The file structure in Jekyll was new to me. I got to see how what ultimately renders as a web page is made up of constituent parts that Jekyll pulls together. With the help of a [Lynda.com](http://www.lynda.com/GitHub-tutorials/GitHub-Web-Designers/162276-2.html) class, I was typing using git via a command line. And occasionally, it did what I thought it would!

It's a fun exercise and, ultimately, worth the effort. Again, I do think I learned a lot and this has definitely made me interested in learning more about gems. But I also really like how my blog turned out. And I look forward to using it.

I'd love to hear about your experience building a Jekyll site. I'm not ready for the can of worms that are comments, though [Joshua Lande](http://joshualande.com/jekyll-github-pages-poole/) will teach you how. But talk to me on Twitter [@heymicky](http://www.twitter.com/heymicky).
