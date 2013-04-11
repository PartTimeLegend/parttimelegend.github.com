---
layout: post
title: "Finally got Travis CI to work with C#.NET"
date: 2013-04-11 06:06
comments: true
categories: development, csharp, dotnet
---

I have been playing with [Travis CI](http://www.travis-ci.org) for a little while as I see the amazing advantage of using CI. One of the downsides I saw was the lack of .NET development testing.

Well I fixed that! Well, okay... sort of.

We need to do a few things to make it work, that are a bit tough to do to start with.

First the language. I would love to see the option for C# in the future, but for now we will just say it's C.

```
language: c
```

Now we need to install [Mono](http://mono-project.com/Main_Page) which is described on their own site as:

>"Mono is a software platform designed to allow developers to easily create cross platform applications. Sponsored by Xamarin, Mono is an open source implementation of Microsoft's .NET Framework based on the ECMA standards for C# and the Common Language Runtime. A growing family of solutions and an active and enthusiastic contributing community is helping position Mono to become the leading choice for development of Linux applications."

Obviously it's not as complete as Microsoft's, but it's good enough for me.

```
install:
  - sudo apt-get install mono-devel mono-gmcs
```

Now we simply call xbuild and pass in the solution.

```
script:
  - xbuild MarkdownSharp.sln
```

Does it work? Check it out for yourself.

[![Build Status](https://travis-ci.org/PartTimeLegend/PseudonymMatching.png?branch=master)](https://travis-ci.org/PartTimeLegend/PseudonymMatching)
