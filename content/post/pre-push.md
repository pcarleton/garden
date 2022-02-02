---
title: "Git pre push"
date: 2022-02-01T20:12:42Z
draft: false
---


I want to build my site on commit, here's what I tried first:


```
set -eux

rm -rf public
hugo
git add public
echo "updated build directory"
```