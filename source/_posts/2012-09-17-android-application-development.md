---
title: Android Application Development
author: Antony
layout: post
permalink: /android-application-development/
categories:
  - Software Development
tags:
  - Android
  - App Inventor
  - HTC Desire HD
  - HTC Sense
  - Integrated development environment
  - IntelliJ IDEA
  - Massachusetts Institute of Technology
---
# 

So it looks like I’m a little late to the party. I have been a fan of [Android][2] for a few years now, I am currently using a [HTC Desire HD][3] which is rooted and running a custom build of [Ice Cream Sandwich][4] with [HTC Sense][5] 3.6 as I’m not a huge fan of HTC Sense 4.0.

 [2]: http://code.google.com/android/ "Android"
 [3]: http://www.htc.com/www/product/desirehd/overview.html "HTC Desire HD"
 [4]: http://en.wikipedia.org/wiki/Android_version_history "Android version history"
 [5]: http://en.wikipedia.org/wiki/HTC_Sense "HTC Sense"

I have apps I can’t like without. I will write a post on my most favorite apps at a future date. This post is about my experiences with creating my first few Android applications.

There are several different [IDEs][6] available for [Android developers][7]. The ones I have been using using to test are:

 [6]: http://en.wikipedia.org/wiki/Integrated_development_environment "Integrated development environment"
 [7]: http://developer.android.com/resources/dashboard/platform-versions.html "Android Developers"

*   Eclipse
*   [IntelliJ IDEA][8] Community Edition
*   [MIT][9] [App Inventor][10]

 [8]: http://www.jetbrains.com/idea/ "IntelliJ IDEA"
 [9]: http://maps.google.com/maps?ll=42.35982,-71.09211&spn=0.01,0.01&q=42.35982,-71.09211 (Massachusetts Institute of Technology)&t=h "Massachusetts Institute of Technology"
 [10]: http://appinventor.googlelabs.com/about/ "App Inventor"

I must admit that for my first few attempts at creating something simple. I went with with the MIT App Inventor. It’s a simple to use [Web Application][11] with the nice [GUI][12] you expect from the likes of [Microsoft Visual Studio][13] which I am used to.

 [11]: http://en.wikipedia.org/wiki/Web_application "Web application"
 [12]: http://en.wikipedia.org/wiki/Graphical_user_interface "Graphical user interface"
 [13]: http://www.microsoft.com/visualstudio/en-us "Microsoft Visual Studio"

I started off with the standard vanity applications and created a simple business card application for myself and my [IT Consultancy][14] work.

 [14]: http://www.antonybailey.net



On the back of this I got asked to write a similar application for my friend who runs [Aran Fielder Subtitles Ltd][15] which you can download from [here][16].

 [15]: http://www.aranfielder.com
 [16]: http://www.antonybailey.net/app/android/AranFielder.apk

The MIT Application Inventor is so very easy to use. Instead of you requiring any real Java knowledge, you instead develop with a complete GUI. You drag and drop elements to the screen and then launch the Blocks Editor, which allows you to create logic to run on your events.

I have created a simple application for launching this blog which you can download [here][17]. This was written by creating a new application and then adding an Activity Starter.

 [17]: http://www.antonybailey.net/app/android/PartTimeLegend.apk

The action for the activity launcher is “android.intent.action.VIEW”.

Now in the blocks editor I select Screen1 and the initialize method. On this I attach the Activity Starter and I set the DataUri to a text option with my link. I then attach the StarActivity to tell the application to action the request. Finally adding the close application to end the app and free up memory as all it does it launch your web browser and load a link.

I have since created multiple small apps with more in depth logic involved. However this is to show as an example of what you can do.

So you have now written your app and you want to make it available to the world. This is the tough part.

You see if you want to list your app on Google Play you have to pay the registration fee of $25. While this is a small amount to pay, if you are creating free applications without the inclusion of ads because you are a jolly nice person then it’s a high cost.

There is also the option to list your application on [SlideMe][19] which is free of charge, but without the same exposure.

 [19]: http://SlideME.org "SlideME"

For now I am going to self host my applications on my own server, and see if there is much interest. If I do decide to start listing applications on Google Play, I will only ever provide them free of charge and if I require revenue generation I will include advertisements. I don’t agree with the freemium business model. I would rather have the full feature client with apps that have a half restricted with nag screen.

 

