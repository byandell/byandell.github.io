---
layout: post
title: Streaming Data to Sovereignty
---

Water is the staff of life.
Water travels through mountains via streams and rivers, cleaning itself and the land, or maybe picking up contaminants along the way.
These noxious objects dirty the water and threaten the health of their ecosystem, including the people (plants, animals, climate, rocks and humans) who live there.
How are water and data connected to sovereignty?

Communities have the right to monitor water flowing through their lands.
They can learn from data collected by carefully placed (cloud-ready) sensors coupled with AI-driven analyses and visualization about water flow and contamination.
Novel partnerships develop among communities and AI companies, ideally with the community in charge.
That is, leading with community sovereignty places agency in the hands of those most connected and impacted by water, which is likely the best way to learn adaptations that help heal the planet.
Healing the planet requires creative AI solutions, which are already coming from communities such as the [Sicangu Climate Center](https://sicangucenter.org/), the [ESIIL Stars Program](https://esiil.org/esiil-stars) and the [Lakota AI Code Camp](https://lakota.aicode.camp/).

This is a story of how I am learning some ways that these data and tools evolve through the collaboration of talented people and their tools.

## Sicangu Climate Center

I became connected with the [Sicangu Climate Center (SCC)](https://sicangucenter.org/) through innovation summits and working groups organized through [ESIIL](https://esiil.org/).
See [Maka Sitomniya](/Maka-Sitomniya/) for some aspects of this work.

The SCC and the Rosebud Sioux Tribe are working on a variety of projects to understand and protect the water that flows through their lands.
Part of this involves pulling together disparate data sources to create a comprehensive picture of their ecosystem.
These data are public; however, their context and meaning depends on how community members learn from them.

Personal laptops can leverage APIs and large (NSF-, NSERC- or other agency- funded) servers to harness data and computation at scale. Such systems can be designed to respect sovereignty and community governance. A community (Tribe or collectives of Tribes) may choose to house data and locally and coordinate with AI servers to retain sovereignty and agency.

## Three Rivers

I attended the
[ESIIL Innovation Summit 2025](https://cu-esiil.github.io/Innovation-Summit-2025/)
and drifted into the
[Three Rivers ESIIL working group](https://cu-esiil.github.io/resilience-rare-hydrologic-events-management-innovation-summit-2025__15/).
This group was somewhat unique in that all of us were "methods" people,
with some having strong technical expertise in hydrology, earth science, and me in data science.

[Tyson Swetnam](https://www.tysonswetnam.com/)
demonstrated prompt engineering at the
using a natural language paragraph as an AI prompt.
I adapted this with the
[Draft AI Task using Claude and MCP](https://github.com/CU-ESIIL/resilience-rare-hydrologic-events-management-innovation-summit-2025__15/blob/main/documentation/group-notes.md#draft-ai-task-using-claude-and-mcp),
which became the section on
[AI Prompt Engineering](https://github.com/CU-ESIIL/resilience-rare-hydrologic-events-management-innovation-summit-2025__15/blob/main/docs/index.md#ai-prompt-engineering).
The prompt generated a bunch of tasks and code, and data,
but the data turned out to be simulated.
Still, it was an amazing demonstration to me of the potential of these tools.

## Of Mice and Men

This is about my long-term collaboration with Alan Attie's biochemistry lab on systems genetics comparing mice and human traits.
See what I wrote in this blog and developed in this repo:

- [Gravity and Antigravity](/2026-02-13-Gravity-and-Antigravity/)
- [sysgenAnalysis](https://github.com/byandell/sysgenAnalysis)

## ESIIL: Retraining Ourselves

Nate Quarderer has invited me to be a senior project advisor to the
[ESIIL Stars Program](https://esiil.org/esiil-stars)
this Spring and Summer.

I have been learning to build tools without writing code by hand. Instead I am building natural language prompts in sentences, paragraphs and reusable
[workflow prompts](https://github.com/AttieLab-Systems-Genetics/sysgenAnalysis/blob/main/inst/doc/walkthrough.md#workflow-prompt).
I hope to build on my collaborative learning (see previous section) as I advise students in the Stars program.

## Streaming Data to Sovereignty

It turns out that AI needs water, as do communities.
This raises important ethical issues that are intertwined with sovereignty and agency.

### Water Ethics, and Efficiency

Each year, tools get more efficient, needing less water to produce even more useful results.
[Tyson Swetnam (U AZ)](https://tysonswetnam.com/blog/posts/2025-01-14-gpt101/)
muses on the ethics of AI and where we might be going.

AI companies are trying to improve their efficiency, and their image.
This includes making machines and algorithms that use less water.
Also, there is an emerging effort to support the communities that are protecting and nourishing the water that weaves through their lands.

Here are some approaches to this challenge.
So range from zero-water data centers to rethinking how we train people to use data.  

- [Articles about AI](https://github.com/byandell/Documentation/blob/main/AI.md#articles-about-ai)
- [Tyson Swetnam](https://tysonswetnam.com/blog/posts/2025-01-14-gpt101/)
- [Microsoft](https://www.microsoft.com/en-us/microsoft-cloud/blog/2024/12/09/sustainable-by-design-next-generation-datacenters-consume-zero-water-for-cooling/)
- [Google](https://blog.google/company-news/outreach-and-initiatives/sustainability/our-commitment-to-climate-conscious-data-center-cooling/)
- [NVIDIA](https://blogs.nvidia.com/blog/ai-energy-innovation-climate-research/)

### Sovereignty, Agency and Privacy

LLMs offer challenges and opportunities. Unchecked, LLMs will harvest data and prompts fed to them to improve their algorithms. This can (hopefully) be managed through contracts. For instance, UW-Madison has contracts with Google and Microsoft so that they "won’t use your prompt data to train its large language models ... and AI tools". Part of this involves retaining each person's conversations (prompts, plans, walkthroughs,etc.) in a sovereign place (behind a firewall). Another aspect is ensuring the tools do not harvest from users' activity. This may require having servers in community as well as contracts for tools. See for instance [UW-Madison's Generative AI Services](https://it.wisc.edu/generative-ai-services-uw-madison/)
