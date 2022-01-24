---
layout: post
title: Git rebase
author: [Mirnes Hasanovic]
category: [Github]
tags: [rebase]
---

Rebasing a branch updates one branch with another by applying the commits of one branch on top of the commits of another branch.

For example, if working on branch named **wip-8712-test-module** but the branch is out of date with a **master** branch. Rebasing the **wip-8712-test-module** branch onto **master** will allow all the new commits from **master** to be included in **wip-8712-test-module**. 

Here is the way how to do that:

{% highlight java %}

$ git checkout master
$ git pull origin master
$ git checkout wip-8712-test-module
$ git rebase origin/master
...
<resolved conflicts>
...
$ git rebase --continue, git rebase --continue, …
$ git push -f origin wip-8712-test-module
{% endhighlight %}

What we did here?

Firstly we have updated our **master** branch, then checkout to **wip-8712-test-module** branch and then rebase **wip-8712-test-module** branch onto **master**.