---
layout: post
title: "Travis CI and how I both love and hate you"
date: 2013-04-05 20:50
comments: true
categories: technology, development, github, internet
---
After recently rediscovering my love of [Github](http://www.github.com/parttimelegend) I was interested to see some of the additional functionality.

You see I have long had a background of developing Open Source software. I haven't in recent years as I have had more interest in making money rather than making the world a better place. Well now I feel I have skills to offer the Open Source community as well as learning new skills.

I love the idea of Continuos Integration and I wished it was easier to support and implement. I develop in several languages, and I have recently decided to learn Ruby as a something to do project.

I had seen systems such as [Jenkins CI](http://jenkins-ci.org/), but the fact that I needed an additional server of my own to use it limited me from real useage for real time CI.

I then came to find [Travis CI](https://travis-ci.org/)! It seemed simple enough to setup, just sign in and activate for your project.

Then came the hard part, the `.travis.yml` file! Oh I understand the need for it, don't get me wrong. I just wish it was easier to figure out the real options.

```
language: ruby
rvm:
  - 1.9.3
  - jruby-18mode # JRuby in 1.8 mode
  - jruby-19mode # JRuby in 1.9 mode
  - rbx-18mode
  - rbx-19mode
  - 1.8.7
```

Well that looks simple enough. Let's go! Oh wait, it's more than that.

Well it decides it will run `bundle install` which is fine by me, then it runs 'rake install'. Wait a second! I'm not using rake! So it fails as I have no `Rakefile`. Surey there is a way around this. There is!

```
script: bundle install
```

Now let's move on to the way that Travis decides to email you constantly about the status of a build. I don't like email. I really want a replacement for email, but what?

First let's disable the email alerts.

```
notifications:
  email:
    on_success: never
    on_failure: never
```

That's better already, but I'm going to need you to alert me somehow. Preferably something I can automate. Let's look back at one of the oldest uses of the internet IRC. I have an issue with IRC as it is always idle people or people trying to get into [QDB](http://bash.org). However for alerts it's perfect!

```
notifications:
  irc: "rowling.freenode.net#parttimelegend"
```

I can then have an application monitor and investigate failures. I can even set it to fix common ones if I wish.

Then Travis is perfect! Well almost. The last fix for me is branches.
If you're like me, then some of your branches are broken. This is because they are development branches and I check code in a lot.
So we want to tell Travis not to read certain branches, or more simply only to check certain branches.

```
branches:
  only:
    - master
```

This tells Travis to only check the master branch. I'm going to assume this always builds, or at least it should. My only complaint is that master is checked first so can't be excluded simply.
Such as in the case of [this blog](https://github.com/PartTimeLegend/parttimelegend.github.com). In this case the master branch is not code, but the source branch is.
I've not found a fix for this yet though. :(
