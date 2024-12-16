---
layout: post
title: Shining Light on Data
---

I met Joe Cheng at
[rstudio:conf](https://github.com/rstudio/rstudio-conf)(2015)
in Orlando, FL,
thanks to funding from 
[Alan Attie](https://attielab.biochem.wisc.edu/)
concerning our joint work
on mouse models of diabetes, nutrition and obesity.
I had developed an 
[R shiny](https://shiny.posit.co/r/gallery/)
web app for our early genetics studies
([qtl2shiny](https://github.com/byandell-sysgen/qtl2shiny))
and wanted some advice on how reactivity worked and why
R and shiny were a good system to use for interactive web resources.
Joe Cheng shared with me the key ideas, which he has since refined in his 
[keynote for posit:conf(2022)](https://posit.co/keynotes/the-past-and-future-of-shiny/).
Through some clever tricks, he overcame the challenge of interacting
in real time with a web interface and a behind-the-scenes server.

As I recall, the key idea is to figure out what information needs to
be passed by the user on the web (largely via `input`s) to the server,
and what needs to come back from the server (largely via `output`s),
with additional `server` observations.
Further, he realized how to present the tools to developers like me
in an R package, without need (mostly) to code in other arcane languages. 
Other systems available at the time were usually developed in python with an
uncomfortable amount of java (or javascript--I can never keep them straight),
leading to many challenges of debugging and maintaining.
Now, in 2024, Joe and the team at Posit have provided
[python shiny](https://shiny.posit.co/py/gallery/),
opening up this great resource to a whole new audience.

I continue to work with Alan, whose biochemistry team has now evolved
to speak dry code as well as wet lab.
[Well, not
[DRY](https://www.getdbt.com/blog/guide-to-dry) code yet, but getting there.]
Over the past couple of years, I developed a shiny app for the founder strains
of our genetic studies.
The apps built on my
[foundr](https://github.com/byandell-sysgen/foundr)
package now enable Alan's team and their collaborators to query hundreds of
thousands of traits (measurements) across their founder panel.
However, once again, this turned out to be a very complicated app,
with about 20 modules that interconnected in a variety of ways.
While this app is published in various forms, my earlier `qtl2shiny` app
(also with about 20 modules) languishes, with sore need for updating and
a successful deployment to make it useful to others.
Coming hopefully in 2025.

My goal of late has been to share this reactive, interactive technology with
collaborators so that they can readily develop their own web apps.
Seems simple enough, and Posit and multiple individuals have provided lots of
examples, as well as a whole book on
[Mastering Shiny](https://mastering-shiny.org),
with chapter 19 on
[Shiny Modules](https://mastering-shiny.org/scaling-modules.html).
Still, this seemed daunting for biologists with modest R coding experience.
My first effort to meet this need involved returning to the classic
[Faithful](https://shiny.posit.co/r/gallery/start-simple/faithful/)
geyser example, the first most people see when they learn about shiny.
I decided to build out shiny modules based on this well-known example
so that learners could focus on the code logic and user interface.
The result was shared as the
[geyser](https://github.com/byandell/geyser) study,
complete with a 
[Quarto-based slide deck](https://connect.doit.wisc.edu/geyserShinyModules/slideDeck.html)
for exposition, containing steps to build one shiny module,
and then connect multiple modules (up to five or so).
Feedback welcome.

This Fall, I have been learning python for a different systems project,
on mapping environmental systems, overlaying soil, climate and other
measurements in a `data cube`. I am looking forwared to learning how
to deploy shiny and quarto apps based on python code in 2025.
I will probably start with a python version of the geyser example,
to nail down ideas for me and others.

It is fun to keep learning and sharing ideas.
I have come to realize, now 1.5 years into my retirement,
that I value connecting with other people around concepts and tools
that were important to me over my career.
Much of that time, I felt I had to "prove" myself in terms of math stat
theory (certainly to get tenure), while I was really drawn to ways to
play with data using computers.
That "play" is what got me into this journey anyway, dating back
to my early days more than half a century ago when I worked with
[Bland Ewing](/pages/ewing/)
on systems ethology.
I look forward to continuing that work in the not too distant future.