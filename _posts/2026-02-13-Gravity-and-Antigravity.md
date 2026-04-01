---
layout: post
title: Gravity and Antigravity
---

We live in challenging times.
I find the need to balance the heavy with the light:
to be serious but have fun;
to be grounded but retain some levity.
Part of the balance involves living on this earth
and in this country right now,
while another part is exploring the world of thought and ideas
using the tools of automation, design, analysis and visualization.

Gravity is the force that holds us to the earth,
while antigravity, in theory, frees us from that grip.
[Antigravity](https://antigravity.com/)
is a tool to explore ideas using words, images and data
via code and prompts.
The balance of forces keeps us alive.
For me, the balance is between thinking and creating,
taking care of myself,
and connecting with others and the world around me.

- [My Process](#my-process)
- [Collaborating in Teams](#collaborating-in-teams)
  - [Sharing  Prompts instead of Code](#sharing-prompts-instead-of-code)
  - [Thinking Big](#thinking-big)
- [My Projects](#my-projects)
  - [Systems Genetics](#systems-genetics)
  - [Environmental Systems](#environmental-systems)
  - [Systems Ethology](#systems-ethology)
  - [Personal Photographs](#personal-photographs)

## My Process

My goal is to move away from creating digital tools (writing code) by hand,
and at the same time to organize my collection of digital works
in a way that is useful to me and others.
Automation for the design, analysis and visualization of data
are now available in novel ways that were not possible
during my formal career trajectory, or even six months ago.
I'm exploring new ways to create artful, data-rich stories that are
grounded in what I know--statistics and data science--using
an environment that supports fun, easy and productive collaboration.

Specifically, I am using [Antigravity](https://antigravity.com/)
as a creative environment with a variety of AI agents.
This enables me to construct "prompts" of various levels of complexity
to generate code, images, and other artifacts that help me
explore and communicate ideas. This becomse a high-level
conversation with the AI model
(so far, mainly [Gemini 3 Flash](https://gemini.google.com/share/128669714867))
in which I am learning to guide with words rather than grapple with code.
For more about AI agents see
[Artificial Intelligence (AI) References](https://github.com/byandell/Documentation/blob/main/AI.md).

Another aspect of collaboration involves other people.
I have started talking with long-time colleague
[Alan Attie](https://labs.wisc.edu/attie/)
about his work on the genetics of diabetes, obesity and nutrition.
We are exploring ways to use these new tools to help us
communicate his ideas more effectively.
Early days, but we are both learning about AI and about how to
communicate with each other using this new environment.
In other words, we are crafting an ecosystem in which we build
ideas that result in useful documents or interactive widgets
([Shiny](https://shiny.posit.co/) and [Quarto](https://quarto.org/)).

We each bring different strengths to the table,
and we are learning to leverage each other's skills.
For instance, Alan showed me how to record speech into a document
that is transcribed and then edited.
This would be useful for the big picture story,
or it might help in developing a detailed prompt.

## Collaborating in Teams

How is AI evolving the way people collaborate in teams?
[Most articles about AI](https://github.com/byandell/Documentation/blob/main/AI.md)
focus on its impact on isolation;
I prefer to think about the other side of the coin: collaboration.
My goal is to help guide and shape some of that collaboration within teams
shaped by AI.

It takes time to coordinate with an interdisciplinary team.
It is crucial to agree on the important goals and strategies to achieve those goals.
This high-level thinking gets translated into lower-level tactics
to accomplish the scaffolded goals and strategies.
All of this takes time and compromise, meaning there is no magic bullet AI solution.
However, AI conversations enable the translation of strategies into tactics
that can all be written in plain language.
In fact, we seem to be evolving to a point where computer code is merely
an artifact of these conversations.

### Sharing  Prompts instead of Code

Thinking with gravity about a project leads us to
abstract a goal into multiple steps.
One "meta" way to track these steps involves saving prompts
and/or walkthroughs iteratively to build a history of our process.
A few minutes extra work during an AI conversation
yields a shareable record,
helping us remember what we did and why.
I have used AI via Antigravity to build documentation in a variety of ways
toward a broader goal of learning how to develop tools for bigger strategic goals.
Here is one useful example.

Alan Attie began studying an experiment with Diana Esparza using a series of prompts
to transform a data table (XLSX file) into a set of plots (PNG files).
That Monday, they wanted to talk with me about interpretation,
and we drifted into discussion of how to document
their work by saving their prompts in a markdown file.
I guided them over 1.5 hours in organizing their work
into a powerpoint presentation (PPTX file) via a Quarto file.
using AI to not only do the work for them (write code, create plots, etc.),
but also to iteratively save the prompts in a markdown file (`prompts.md`),
getting AI to update the prompts file as we went.

On Wednesday, Diana had the data file and the prompts file from Alan —- nothing else.
She asked me to help her make it work for her.
We found that the prompts file had the absolute file address for the data table,
which we changed to a relative address (just `filename.xlsx`).
After that, it worked, locally creating the R code file, the plots and the powerpoint.
Over that hour, I blithely suggested this could be improved with a table of contents.
Diana proposed adding information and references about the subject matter.
She wrote prompts and, presto (with a few tweaks to improve viewing), the new powerpoint now had a TOC, descriptions, and references.
FINALLY, Diana asked AI to modify the prompts markdown file to include this last addition.

The point is that Diana learned how to reproduce earlier work, and to improve on it, using only the data and a prompts file. _The code and plot files were incidental artifacts._ We worked at a strategic level of collaboration toward a goal without getting mired in how-to detail.

Actually I did a fair amount of guiding, particularly in getting Alan and Diana to document their steps. That effort led to a demonstrably reproducible piece of work, which can be a model for future collaborations in this lab.
See
[prompts/powerpoint.md](https://github.com/byandell/Documentation/blob/main/prompts/powerpoint.md) among
[AI Prompt Examples: Powerpoint Presentation](https://github.com/byandell/Documentation/blob/main/AI_prompts.md#powerpoint-presentation) for details.

### Thinking Big

It will be useful to “think big” and “go big” with future use of agentic AI (what is that? read on).
We have started with “conversations' with AI, initially with an AI tools like Claude Code or Google Gemini on their own.
Now we build conversations in an integrated environment such as AntiGravity that enable “seeing” our code and data and “acting” on those resources to evolve them.
This allows us to speed up various useful tasks and gets us wanting more. What is next?

The bigger picture involves data, code-based tools, external resources (web-based APIs), and our detailed description(s) of what we know and what we want to understand. For instance,

- Data: How do we study ALL our DO1200 data, integrating them with other DO and founder data (and data from other organisms).
- Tools: How do we evolve tools we have developed for DO and founder mice, including those under development now, and connect with others out there (from Jax, GeneNetwork, Galaxy, Cytoscape, Broad).
- APIs: API tools provide code to get/put data at scale (DNA, SNP, protein databases, etc.).
- Questions: Most of our questions (and tools) have focuses on one QTL region (single QTL models), one trait, or one pathway. Yes, we gather information about many related things but filter down to summaries for single traits or loci. Yet our bigger concern is about whole-organism processes with many interrelated processes.
- Prompts and agentic guidance: Our questions are closely tied to the prompts we will want to develop. The essence of our conversations with AI should be captured concisely so that we learn from our experience and build up more complicated prompts from simpler ones. See for instance what I did so far with [sysgenAnalysis](https://github.com/byandell/sysgenAnalysis).

As hinted in the last point, we cannot just jump from the simple conversation to the whole gestalt.
Instead, we build up in stages, scaffolding that builds on what we are learning now.
Part of this will involve learning how to have multiple parallel, independent conversations, or so-called Agentic AI.
We get to this by learning more.

We should all take Tyson Swetnam’s self-paced online workshop
[Generative AI & Prompt Engineering](https://tyson-swetnam.github.io/intro-gpt/),
which should take 8-12 hours.

To get to big AI, we will need some monthly fee-based access to Google Gemini Pro and/or Claude Code ($100-200/person/month).
Claude Code is the current innovation leader, but Gemini has the advantage of a license with UW-Madison that protects AI conversations from being harvested to “improve” their models.
See more at
[Artificial Intelligence (AI) References](https://github.com/byandell/Documentation/blob/main/AI.md).

## My Projects

Here are some of my projects that I would like to evolve in coming months posed as questions. These all have presence on GitHub; while many involved coding, some are more writing projects.

- [Systems Genetics](#systems-genetics)
- [Environmental Systems](#environmental-systems)
- [Systems Ethology](#systems-ethology)
- [Personal Photographs](#personal-photographs)

### [Systems Genetics](https://github.com/byandell-sysgen)

How can we study broad and deep patterns in mouse (and eventually human) studies with theseextensive molecular measurements?
The central dogma of molecular biology has been expanded (see for instance [[Hazeltine (Forbes)](https://www.forbes.com/sites/williamhaseltine/2024/12/03/a-new-dogma-of-molecular-biology-a-paradigm-shift/)])
as we have extended molecular measurements to include DNA, RNA, proteins, lipids, metabolites and more.
I continue to collaborate with
[Alan Attie](https://labs.wisc.edu/attie/).
This will involve rethinking my
[sysgen](https://github.com/byandell-sysgen) coding projects along with projects of Attie team members,
as well as other _de novo_ approaches that emerge.
For instance, what about asking AI to look for patterns among _all_ Attie's data, pointing it to our tools but leaving open new directions?

My resources include

- [qtlshiny](https://github.com/byandell-sysgen/qtlshiny)
  - focused on small genomic region with useful SNP/SDP tools
  - needs to be updated in terms of reactivity and UX
  - would benefit from dynamic connections to other tools
- [founderShiny](https://github.com/byandell-sysgen/founderShiny)
  - mature platform
  - would benefit from dynamic connections to other tools (such as gene cards, etc.)
- various other QTL tools in various stages of integration

### [Environmental Systems](https://github.com/byandell-envsys)

How can we make it easier for communities to study their land and water using publicly available data?
Ready-made tools are often specialized and poorly interconnected. Development of new tools (largely in python) takes time if done by hand.
How can we better train young researchers to jump into this space to address their pressing projects, and in doing so, help them develop the skills to create the next generation of dynamic, interconnected tools?

My resources include

- [geyser](https://github.com/byandell/geyser)
  - Improve tutorial materials
- [landmapr](https://github.com/byandell-envsys/landmapr)
  - Needs tutorial for census and territory
  - Import translated modules from landmapy
- [landmapy](https://github.com/byandell-envsys/landmapy)
  - built around ESIIL/EarthLab
[Earth Data Analytics (EDA) course](https://github.com/byandell-envsys/EarthDataAnalytics)
  - turns their examples into function
  - would benefit from developing shiny examples
  - translate modules from landmapr
- ESIIL projects
  - [ESIIL GitHub pages](https://github.com/byandell/ESIIL) from
[EDA course](https://github.com/byandell-envsys/EarthDataAnalytics)
  - [ESIIL Stars Program](https://esiil.org/esiil-stars) with Nate Quarderer
  - [Maka Sitomniya](/Maka-Sitomniya/) and
    [Sicangu Climate Center](https://sicangucenter.org/)

### Systems Ethology

How can I articulate Bland Ewing's concepts about systems ethology to share with others?
[Bland Ewing](https://www.stat.wisc.edu/~yandell/ewing/)
developed the ideas for systems ethology (or quantitative population ethology as he called it) in the 1970s. These forgotten ideas still seem to be state-of-the-art, with some aspects being discovered independently in recent years.

My resources includes

- [Ewing Simulation](https://github.com/byandell/ewing)
  - need improvedShiny modules walking through sim
- Bland Ewing biography
  - [Quantitative Population Ethology](https://github.com/byandell/ewing)
  - [Bland Ewing Biography](https://drive.google.com/drive/u/1/folders/12bimDvEoG1EnssZT_Bn2HwdrAHt74guv) [Private]
  - [Bland Ewing: A Remembrance](https://mclements.net/Michelle/BlandEwing/) (Michelle McClements, niece)

### Personal Photographs

I have a collection of photographs that I would like to organize and share.
During my Watson Year (1974-75), I took 35mm slides across Europe and the Indian subcontinent.
During graduate years and beyond, I traveled to
Central America and other locales.
[See [My Chronology](/pages/reflect/#my-chronology).]
In addition, I have a collection of family photographs.
The challenge is how to organize these well,
including digitizing some early material.

_Updated on February 20 and March 16-30, 2026._
