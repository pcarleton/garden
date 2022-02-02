---
title: "Git pre push"
date: 2022-02-01T20:12:42Z
draft: false
---


I want to build my site on commit, here's what I tried first:


``` ./git/hooks/pre-commit
set -eux

rm -rf public
hugo
git add public
echo "updated build directory"
```


This worked! But it took some fiddling because I mistakenly set the date of this post in the future.  Apparently you can do that and Hugo won't add the pages for it, so it was running the build command but not actually updating anything.