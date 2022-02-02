---
title: "Garden Fun"
date: 2022-01-30T10:40:33Z
draft: false
---

A list of fun things I want to play around with on this:
- A favicon that has the moon but adjusts with the phase
- Similarly, but on the top of the page
- Some kind of counter that says how long its been since I posted, maybe some kind of "staleness" -- could be an encouragement to write more or an indicator that it's time to delete some things
- Generally messing with "themes" to personalize it more (there's 3 different "modes" of PaperMod)
- Trying to make the [[post title]] style links from Logseq work here



## Emoji favicon

https://css-tricks.com/emoji-as-a-favicon/

Combined with some code similar to the CLI:
https://github.com/pcarleton/moon/blob/master/src/main.rs#L61

We get this:

```
<script>

    // 2000/01/06 18:14 UTC, arbitrary new moon starting point
    var lun0 = new Date(947182440000);
    var now = new Date();

    // diff in days
    var diff_days = ((+now) - (+lun0)) / 1000 /* ms */ / 60 /* s */ / 60 / 24;


    // Average time it takes to go from new moon to new moon
    var mean_lunation = 29.530588;

    // diff in lunations
    var diff_lun = diff_days / mean_lunation;

    // current one is how close we are to the next lunation
    var cur_lun = diff_lun - Math.floor(diff_lun);


    function get_char(lun) {
        var buffer = 0.015;
        if (cur_lun < buffer) {
            return "🌑";
        }

        if (cur_lun < (0.25 - buffer)) {
            return "🌒";
        }

        if (cur_lun < (0.25 + buffer)) {
            return "🌓";
        }

        if (cur_lun < (0.5 - buffer)) {
            return "🌔";
        }

        if (cur_lun < (0.5 + buffer)) {
            return "🌝";
        }

        if (cur_lun < (0.75 - buffer)) {
            return "🌖";
        }

        if (cur_lun < (0.75 + buffer)) {
            return "🌗";
        }

        if (cur_lun < (1 - buffer)) {
            return "🌘";
        }

        return "🌑";
    }


    var cur_char = get_char(cur_lun);


    var link = document.querySelector("link[rel~='icon']");
    if (!link) {
        link = document.createElement('link');
        link.rel = 'icon';
        document.getElementsByTagName('head')[0].appendChild(link);
    }
    link.href = 'data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2280%22>' + cur_char + '</text></svg>';
</script>
```