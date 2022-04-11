---
title: "Notebook CSS"
date: 2022-03-08T20:33:01Z
draft: false
---

What if I wanted this page to look like a notebook?  Like with the dots like I had in [e-notes]({{<relref "e-notes" >}}) (TODO make a shortcode for doign this: https://gohugo.io/templates/shortcode-templates/)

I can do it for sure, I guess the question is whether it actually looks good.  One of the issues is that it's not really lined up with the written text.

{{< rawhtml >}}
<style>
    .main {
        background-image: radial-gradient(#212121 5%, #fdfdfd 6%);
        background-position: 0 7px;
        background-size: 15px 15px;
        height: 10px;
        width: 100%;
    }
</style>
{{< /rawhtml >}}
