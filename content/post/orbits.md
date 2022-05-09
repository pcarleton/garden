---
title: "Orbits"
date: 2022-05-09T06:40:26+01:00
draft: false
---

I have a bizarre way of playing Kerbal Space Program.  I've done it at least three times.  I go to a YouTube series by CheersKevin called ["Kerbal Space Programming"](https://www.youtube.com/watch?v=fNlAME5eU3o).  I watch the episodes, and play along.  I get to about episode #3 or #4, and somewhere along the way, I get deep into a rabbit hole with the math and optimization available.  I don't think I've ever made it to the episode where he lands on the "Mun" (the Moon equivalent of KSP).  There are 45 episodes. [45!](https://www.youtube.com/playlist?list=PLb6UbFXBdbCrvdXVgY_3jp5swtvW24fYv)

Previously my rabbit holes have been around PID controllers and hovering, and collecting data out of KSP.  It lets you publish data over telnet, so I spend some time setting up a listener and building some graphs (unfortunately lost to the sands of time, so I can't even tell how far I made it down that rabbit hole).

My latest rabbit hole began even before I launched Kerbal Space Program. I talked to a co-worker about KSP, which got me thinking about orbital dynamics.  I have been interested in [Lagrange points](https://en.wikipedia.org/wiki/Lagrange_point) since they seem kind of like magic, and also wanted to understand the ["Interplanetary Transport Network"](https://en.wikipedia.org/wiki/Interplanetary_Transport_Network).

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/3/33/Interplanetary_Superhighway.jpg" title="From wikipedia: Artist's concept of the Interplanetary Transport Network. The green ribbon represents one possible path from among the infinite number possible within the larger bounding tube. Constricted areas represent locations of Lagrange points." width="80%">}}


With those ideas in mind, I started trying to simulate gravity using [Observable Notebooks](https://observablehq.com/@pcarleton/runge-kutta-visualized?collection=@pcarleton/interplanetary-drivers-ed), starting with learning about [Runge-Kutta methods](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods) of numerical analysis after seeing another author's [n-body simulation](https://observablehq.com/@mcmcclur/gravitation-and-the-n-body-problem).

I learned a lot about this, and even ended up making [a Pico-8 game]({{<relref "ludum-dare" >}}) based on some of what I learned (that one was mostly based on how tricky it was to manually make a [Hohmann transfer orbit](https://observablehq.com/@pcarleton/hohmann-transfer-orbit?collection=@pcarleton/interplanetary-drivers-ed)).  After making and then polishing that game, I also wanted to see what an "ideal" transfer looked like, so I made [Hohmann Transfer Rendezvous](https://observablehq.com/@pcarleton/hohmann-transfer-rendezvous?collection=@pcarleton/interplanetary-drivers-ed).

Along the way, I was thinking through what I wanted to do with these simulations since I figured sharing them would be fun, and I stumbled across [a few substacks](https://itsnotrocketscience.substack.com/p/how-do-tides-work?s=r) (after googling "orbital mechanics substack"). One was by a name I recognized, and was thinking along similar lines [about creating tools for learning complex physics](https://roadtoreality.substack.com/p/the-dynamic-notebook?s=r).  I joined [their Discord](https://discord.gg/7MgKgc6), polished a demo on the [Vis-viva equation](https://observablehq.com/@pcarleton/the-vis-viva-equation?collection=@pcarleton/interplanetary-drivers-ed), and convinced myself that finding an audience for the tools I was building was a good next step.

I did eventually launch KSP, and I'll talk more about my audience in a standalone "PR strategy" post.

