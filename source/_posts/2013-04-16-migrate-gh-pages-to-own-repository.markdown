---
layout: post
title: "Migrate gh-pages to own repository"
date: 2013-04-16 00:29
comments: true
categories: github
---

After joining the [Buttercoin](https://github.com/buttercoin) development team, I was asked to move the `gh-pages` to it's own repository.

Whilst this is a really simple thing to do, it surprised me the lack of clear documentation on how to do this.

Go like this.

```
git clone -b gh-pages https://github.com/yourname/reponame.git temp
```

```
cd temp
```

```
git remote rm origin
```

```
git remote add upstream https://github.com/yourname/newrepo.git
```

```
git branch -m gh-pages master
```

```
git push origin master
```

You can now delete the `gh-pages` branch from your repository.
