---
layout: handbook-page-toc
title: AI Assist Single-Engineer Group
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

## About the AI Assist SEG

The AI Assist SEG is a [Single-Engineer Group](/company/team/structure/#single-engineer-groups) within our
[Incubation Engineering Department](/handbook/engineering/incubation/) and will work closely with our
[AI Assisted](https://about.gitlab.com/handbook/engineering/development/modelops/ai-assisted/) group.

The name "AI Assist" is quite broad and generic, and it could entail any kinds of assistance from GitLab using
Artificial Intelligence, let's call the latter AI features. There are plenty of ideas on AI features, and probably a few
could spawn off into separate SEGs.

On this page some concepts and ideas are explained, explored and elaborated. The goal of this page is to be
[transparent](/handbook/values/#transparency), welcome [collaboration](/handbook/values/#collaboration) and receive
early feedback to [iterate](/handbook/values/#iteration) on the strategy.

### Latest video
<figure class="video_container">
    <iframe width="600" height="340" src="https://www.youtube.com/embed?max-results=1&controls=1&showinfo=0&rel=0&listType=playlist&list=PL05JrBw4t0KoQ2a8sLO059BdU4F5c-jGE" frameborder="0" allowfullscreen></iframe>
</figure>

### Previous 5 videos

| Date       | Tl;DW;                                                                        | Video                                                                          |
|------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| 2022-12-01 | Last video on AI Assist as it matures to a feature                            | [https://youtu.be/aKj-SahGhz0](https://youtu.be/aKj-SahGhz0){:target="_blank"} |
| 2022-11-11 | All components released, almost ready for dogfooding on 2022-11-23            | [https://youtu.be/FvbAhcGxhFI](https://youtu.be/FvbAhcGxhFI){:target="_blank"} |
| 2022-11-02 | Add support for stop sequences, reduced number of calls to API by roughly 95% | [https://youtu.be/hhBIAC8-j7I](https://youtu.be/hhBIAC8-j7I){:target="_blank"} |
| 2022-10-25 | Authentication MR's 2/3 finished, 1 in review. Worked on FauxPilot            | [https://youtu.be/JNLkmZk0iB8](https://youtu.be/JNLkmZk0iB8){:target="_blank"} |
| 2022-10-13 | First release of VS Code extension, work on authentication                    | [https://youtu.be/VYl0dg8xyeE](https://youtu.be/VYl0dg8xyeE){:target="_blank"} |

## What is AI?
According to the Oxford dictionary, AI is:

> The theory and development of computer systems able to perform tasks normally requiring human intelligence, such as
> visual perception, speech recognition, decision-making, and translation between languages.

But it is also:
- A great buzzword: especially abbreviated to AI, for anyone trying to achieve a higher perceived value of whatever they
are trying to sell.
- A constantly challenged definition due to the [AI effect](https://en.wikipedia.org/wiki/AI_effect)

Some common subdomains of AI are:
- Machine learning
- Deep learning
- Neural networks
- Computer vision
- Natural language processing

Most applications focus on a narrow expertise/subset of human capabilities than general human intelligence.

## The AI in AI Assist
For AI Assist, we will consider the following to be AI: `machine / deep learning models with feedback loops for
continuous learning`. Especially the last part sets it up to be considered an AI as it will keep evolving and adapting
based on the feedback received.

Given the nature of the DevOps lifecycle, most of the input that we have consists of code (text with fewer typos 😄).
Components of AI such as computer vision are not likely to be touched in this SEG.

This SEG aims not to study or research AI but to put AI into practice where user feedback and iteration are most
important.

## AI features
The difference between an AI feature and a "normal" feature is the usage of a subdomain of AI e.g. Machine Learning, and
from a functional perspective, there is no difference. However, from a DevOps perspective, there is, as you not only
need to measure the effect that a feature has on your product but also the model itself. Multivariate testing is at the
core of what differentiates an AI feature.

Examples of AI features that currently do not exist in GitLab:

- Pipeline optimization (e.g. speed)
- Build optimization (e.g. Docker caching strategy)
- Code optimization (e.g. security practices)
- Prevention of duplicates (e.g. very similar modules, or Docker images that could be turned into a base image)
- Boilerplate generation (e.g. type which packages you want to use and get a boilerplate repo template)
- Coding guideline violation detection
- IDE plugin to detect issues that will pop up in the CI/CD pipeline

That begs the question, with which features do you start and why?

## Code optimization
The AI Assist SEG will focus on code optimization and in particular security practices for a number of reasons:
- It's very explorative and therefor a good fit for incubation engineering
- It extends on a subject that users are already exposed to, so we prevent resistance to a completely new concept
- Security is becoming increasingly important
- It allows integration with existing tools and therefor boosting their efficiency

## Mission
Our aim is to use machine learning models to analyze publicly available code across a range of common programming
languages to determine the most effective secure coding practices. We will identify when users write functions that
could benefit from our analysis and offer suggestions on how users can improve their code to guard against known
vulnerabilities and exploits.


## Hypothesis / underlying assumptions
With all the above AI features, there are a few assumptions that need to be validated.

1. Users want GitLab to (proactively) help them detect optimizations in their project
2. We are capable of providing meaningful suggestions
3. Users are willing to accept or provide feedback on our suggestions

## Strategy
Ultimately the AI part will be a self learning application. However, this takes a lot of time and is not in line with
iteration and efficiency. Besides, we first need to validate the underlying assumptions, so to keep it simple and
efficient, it's broken down into the following roadmap:
1. Build a PoC with off the shelf products. No new ML models will be involved at this point.
2. Integrate with the official GitLab IDE extensions for realtime suggestions
3. Start dogfooding the PoC
4. Determine shortcomings and explore options to improve

## GitLab Assist
For years developers have been exposed to code completion tools such as IntelliSense and recently there are developments
of incorporating AI in code completion. A few examples:
- [https://www.tabnine.com](https://www.tabnine.com) (Custom GPT-3 size model)
- [https://www.kite.com](https://www.kite.com) (GPT-2)
- [https://copilot.github.com](https://copilot.github.com) (OpenAI Codex, descendant of GPT-3)

A lot of these companies are using an implementation of GPT. For an overview of products using GPT please see:
[https://gpt3demo.com/map](https://gpt3demo.com/map).

These products are very illustrative of what most people would consider to be AI, they are fancy, helpful and
innovative. There are a few concerns:
- Most applications use GPT
- It takes tremendous amounts of data and compute to train a model
- Available public repositories with the correct licence are accessible to everyone (plain level playing field)
- Public repositories are imperfect, need to prevent the model to be biased towards less secure code
- It suggests but does not educate

The chances of code completion becoming a commodity are fair, it might be worthwhile to aim a level higher, full
boilerplate templates based on a short written description. E.g. "I would like to make a Python API for my user database
in MySQL" would give back a full boilerplate template including security best practices etc.

Alternatively, based on the roadmap described above, the learnings might lead to the creation of GitLab Assist
which will be similar to the core functionality of a code completion product but different because:
- It will educate why certain code is safer
- Adhere to company coding guidelines
- Be aware of licencing
- Incorporate all learnings from the roadmap


## Sub-projects

AI Assist SEG is also involved in the following projects:
- [FauxPilot](https://github.com/moyix/fauxpilot)
- [GitLab VS Code extension](https://gitlab.com/gitlab-org/gitlab-vscode-extension)
- [Dokter](https://gitlab.com/gitlab-org/incubation-engineering/ai-assist/dokter)


## External reads
- [https://nextbigwhat.com/ai-turning-meaningless-buzzword/](https://nextbigwhat.com/ai-turning-meaningless-buzzword/)
- [https://en.wikipedia.org/wiki/Artificial_intelligence](https://en.wikipedia.org/wiki/Artificial_intelligence)
- [https://en.wikipedia.org/wiki/AI_effect](https://en.wikipedia.org/wiki/AI_effect)
- [https://builtin.com/artificial-intelligence](https://builtin.com/artificial-intelligence)
- [https://en.wikipedia.org/wiki/Intelligent_code_completion](https://en.wikipedia.org/wiki/Intelligent_code_completion)
- [https://en.wikipedia.org/wiki/GPT-3](https://en.wikipedia.org/wiki/GPT-3)
