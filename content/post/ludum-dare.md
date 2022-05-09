---
title: "Ludum Dare"
date: 2022-04-11T07:03:03Z
draft: false
---

Two weeks ago was the Game Jam "Ludum Dare".  I had heard about it for a few years running (this was the 50th instance of it), but had never gotten my act together to actually participate.  The gist is a 48 hour period where you create a game from start to finish: all graphics, concepts, code, music etc.  You can be pretty intense about it and not sleep a lot, or you can be like me and forget about it until partway through Saturday, then spend a couple hours on Sunday hurriedly throwing something together.

The game I submitted was very much not polished, but was a fun concept.  The theme was "delaying the inevitable".  I had been kicking around some ideas about orbital mechanics as part of a Kerbal Space Program binge (more on that in another post), and I thought it would be fun to have an element of needing to work with Gravity to avoid some inevitable situation.

My first thought was that the sun has gone supernova, and you need to flee the solar system, however, you can never really go fast enough, so eventually it catches up and kills you.  Another idea was something about a black hole, where you've crossed the event horizon, so you're definitely going in, but you've got some ability to delay your demise.

I started with the supernova idea, and thought about a few stages.  You'd have to go from a low-earth orbit, and transfer to Mars first.  I hadn't really dug into interplanetary transfers yet, and I was actually thinking somehow working out a slingshot via the moon would be really cool and hopefully challenging.  However, [it turns out that you don't actually save that much on the way to Mars by leveraging the moon](https://space.stackexchange.com/questions/14768/multiple-gravity-assist-from-moon-to-reach-mars).  I thought of a way around that which was to put some more fuel orbiting the moon that you could pick up which would incentivize making a stop over / slingshot past it.

With all of that "settled", I got to coding the game.  I wanted to get basic gravity around the earth working first, and figured maybe grabbing a fuel tank would be a good "warm-up" before the whole moon situation.  I quickly realized a few things.  First, there wasn't that much room on the screen.  If I also wanted to have the moon on there, I was going to either have to scroll / zoom a lot, or have a tiny ship.  Second, I realized that in order to do complex orbital maneuvers, I was really going to need some kind of planning interface.  I had learned from my "Hohmann transfer" notebook, that applying "delta v" was actually pretty straightforward as long as I didn't worry too much about the actual rocket mechanics (i.e. I just increase/decrease velocity, I don't contemplate the mass of the fuel or rocket etc.).  However, I also learned that it's very finicky to execute a precise manuever.  The example in that notebook is a simple transfer and re-circulazation, and I needed super precise burns at super precise locations to get a perfect circle.

That meant that if I wanted to have "perfect" burns, I was going to have to do a lot of guiding / restricting to help the player get it right.  There was pretty much no way they'd be able to nail it with just timing a thrust button.  I could do something like indicate a "thrust" button only triggers at your next apo or periapsis, and then have a "mario golf" like bouncing meter to determine the amount of thrust, but that would require a lot of "training" of the player to know what I was even talking about and why, and still the thrust selection would leave a lot of room for error.

I figured that an interplanetary transfer would require some pretty precise burns.  It's possible I could simplify it, but I wasn't confident I could make that experience fun.  Meanwhile, I had a ship orbiting a planet, and the ability to change its orbit, so I hooked up delta-v to the buttons and decided to see how it went.

It was pretty fun to try to do a Hohmann transfer with just timing the buttons, so I figured I'd try to add a mechanic around that.  I had been thinking a sort of "interplanetary drivers ed" mechanic where parking in a new, higher circular orbit could be interesting, kind of like a parallel parking test.  There would be some "green circle" parking area that if you stayed in for a full orbit would count as passing.

That didn't really hit the theme though, which led me to think about running out of air, and trying to grab some oxygen tanks.  (I had thought about this as part of the initial challenge to go to the moon, so my sequence might be a little off here.)  I put in the oxygen tank and found it was actually pretty hard to get it.  I hadn't been considering the different speeds. In my head, if you did a transfer to the same circular orbit, you'd grab it, but that's not true at all, and getting to the same orbit is not a great strategy for a rendezvous.  Being on the same orbit only works if you're also at the same angle around that orbit, and if you're not, you'll never catch up.  Instead, it's all about (1) making your orbits intersect AND (2) having both objects hit the intersection point at the same time.

Realizing that was kind of fun, and made me realize that it was simple enough to figure out while hitting the buttons, but also pretty challenging.  It also told me that anything more involved would be challenging.  And I didn't have much more time.  So I went with it!

The game turned out pretty fun, but was super unpolished.  After some pointers (TODO add YT links) from Shawn, I spent a few hours over the next week adding some "juice" to it:
- small screen shake when you hit the thrust
- particles when you thrust 
- animated sprites for the character (now an astronaut), o2 tank, and earth
- sound effects
- drumbeat background noise
- an intro screen
- smaller status bars
- background stars
- easter egg exploding earth

Adding these was very fun and really changed the overall feel of the game.  I did introduce a few bugs, like your score goes up while you're waiting on the start screen, and the exploding earth is less of an easter egg since it's hit box is a little large.  I was happy with the overall result, and made me excited for next time when hopefully I'll have time to add polish to the game I actually submit.


Other topics to touch on:
- pico-8 
    - sprite editor is like a built-in timecap on how much time to spend on that piece
         - movement / animation of the sprite makes up for an unrecognizable initial sprite
    - sound being intimidating at first, but like sprites, delightfully constrained
    - forces you to think about precision early (due to integer overflow)
    - publishing is super easy, very difficult to break, and works really well on mobile