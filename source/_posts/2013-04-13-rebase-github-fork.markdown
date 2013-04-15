---
layout: post
title: "Rebase Github fork"
date: 2013-04-13 15:16
comments: true
categories: github, development
---

So you are playing around with [Github](https://www.github.com) and you forked a repo. Good for you! Only the original author updated their repo and you need to rebase your fork to get the new commits.

Just do the following steps and you're done.

```
git clone https://github.com/youruser/reponame.git
```

```
cd reponame
```

```
git remote add upstream https://github.com/sourceuser/reponame.git
```

```
git fetch upstream
```

```
git rebase upstream/master
```

```
git push -f origin master
```
