---
layout: handbook-page-toc
title: Mobile DevOps Apps Single-Engineer Group
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

### [2022-12-12] Project-level Secure Files for Self-Managed, Apple App Store Integration, SaaS Runners for Self-Managed GitLab

In this update we take a quick look at the upcoming release of Project-level Secure Files for Self-Managed, an upcoming Apple App Store Integration, and an idea of SaaS Runners for Self-Managed GitLab.

<figure class="video_container">
  <iframe src="https://www.youtube.com/embed/ezRANY68mrI" frameborder="0" allowfullscreen="true"> </iframe>
</figure>

[https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/95](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/95)

### Recent Updates

| Date              | Topic | Video | Issue |
|-------------------|-------|-------|-------|
| November 23, 2022 | Apple App Store Integration | [https://youtu.be/ksdFcUN6NJA](https://youtu.be/ksdFcUN6NJA) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/95](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/95) |
| November 4, 2022 | Secure Files Runner Support | [https://youtu.be/UPJhZ_9Tdjs](https://youtu.be/UPJhZ_9Tdjs) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/93](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/93) |
| October 14, 2022 | Secure Files Metadata Processing| [https://youtu.be/mvQUFYIaVv4](https://youtu.be/mvQUFYIaVv4) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/91](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/91) |
| September 29, 2022 | Content Strategy | [https://youtu.be/yF1ipQS8dXI](https://youtu.be/yF1ipQS8dXI) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/90](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/90) |
| September 13, 2022 | Secure Files Parsers | [https://youtu.be/R4asgR4Q1Q4](https://youtu.be/R4asgR4Q1Q4) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/86](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/86) |
| August 25, 2022 | Mobile DevOps Project Settings | [https://youtu.be/mmeHhMQV-ck](https://youtu.be/mmeHhMQV-ck) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/85](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/85) |
| August 11, 2022 | Auto iOS | [https://youtu.be/cKdxDFCT91I](https://youtu.be/cKdxDFCT91I) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/79](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/79) |
| July 29, 2022 | Ngrok Pipeline Debugger | [https://youtu.be/VmUFpaJiD84](https://youtu.be/VmUFpaJiD84) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/77](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/77) |
| July 13, 2022 | Fastlane Match Demo | [https://youtu.be/IZmTrdkYToI](https://youtu.be/IZmTrdkYToI) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/73](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/73) |
| June 16, 2022 | Fastlane Match & User Research| [https://youtu.be/UgBneIivl_I](https://youtu.be/UgBneIivl_I) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/70](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/70) |
| May 31, 2022 | Project-level Secure Files Usage Dashboard | [https://youtu.be/z5icscEkULU](https://youtu.be/z5icscEkULU) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/67](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/67) |
| May 13, 2022 | Project-level Secure Files Demo | [https://youtu.be/O7FbJu3H2YM](https://youtu.be/O7FbJu3H2YM) | [https://gitlab.com/gitlab-org/gitlab/-/issues/362407](https://gitlab.com/gitlab-org/gitlab/-/issues/362407) |
| May 9, 2022 | Project-level Secure Files UI | [https://youtu.be/7mA_qm1xoFQ](https://youtu.be/7mA_qm1xoFQ) | [https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/66](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/66) |


[Subscribe to the issue for updates](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/7)


## Mission

Our goal is to improve the experience for Developers targeting mobile platforms by providing CI/CD capabilities and workflows that will enhance the experience of provisioning and deploying mobile apps to iOS and Android devices. Our current focus combines the [Product Direction - Mobile DevOps](https://about.gitlab.com/direction/mobile/mobile-devops/) and findings from our recent research.

## Our Hypothesis

Mobile software teams can see the same benefits as other software teams when adopting DevOps practices, but mobile teams are underserved in this area for a variety of reasons.

We believe that mobile teams are looking to adopt DevOps practices, but due to unfamiliar tooling and technical complexity, these initiatives can get time-consuming, expensive, and may not reach their full potential.

Our hypothesis is that we can improve the adoption of DevOps practices by mobile teams by providing opinionated tooling that is easy to use and doesn't require in-depth knowledge of tools unfamiliar to mobile developers like Docker, YAML, etc.

## Vision

Our current focus is around making the `build` > `test` > `release` process as simple as possible for mobile teams using GitLab by focusing on the following areas:

### Code Signing

Mobile Code Signing is one of the most confusing and error-prone parts of the Mobile DevOps process. We can eliminate much of the confusion and trial and error involved in getting pipelines set up by providing a system that makes it easy for developers to securely upload, visualize, and manage their code signing files.

[Adding binary file support to CI variables](https://gitlab.com/gitlab-org/gitlab/-/issues/346290) through a new capability called Secure Files. Secure Files is a generalized solution to the challenge mobile teams are faced with when trying to manage keystores and provisioning profiles in GitLab. By generalizing this solution, we can support other use cases while being able to provide additional enhancements for the mobile-specific use cases.

[Secure Files UX Proposal](https://gitlab.com/gitlab-org/gitlab/-/issues/347149) describes the progressive enhancements we will add to the UI to support the generalized and specific mobile use cases.

[Android Keystore Generation](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/34) is an idea we would like to explore to generate Android keystores on GitLab, which would eliminate some of the manual steps required today.

### App Store / Play Store Integration

With the Code Signing process simplified, the next big area of complexity we will improve is the release process for internal, beta, and public releases. For both iOS and Android platforms, credential certificates and API keys need to be generated and configured correctly for the release process to work. We will provide capabilities to simplify the setup and configuration of these integrations, as well as tools to test these integrations without having to run a pipeline.

[App Store Connect API Login](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/36)

[Play Store API Login](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/35)


### Improved Review Apps for Mobile

While have made some improvements with [Review Apps for Mobile](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/15) there is more that can be done to support a broader range of mobile apps and devices.

[Integrations with emulator services like AWS Device Farm and BrowserStack](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/42) will expand support for testing on a wide range of devices. Since these device farms operate differently than traditional web apps, we will create additional capabilities within Review Apps to support the specific mobile device integrations.

Additionally, with the popularity of cross-platform development tools, [Multiple Url support for Review Apps](https://gitlab.com/gitlab-org/gitlab/-/issues/276905) will deliver a nice addition for teams that want to keep the pipelines in sync across multiple platforms.

### Mobile CI Templates

As we build up the foundational components to the Mobile DevOps experience, we will also roll out additional CI templates focused on mobile use cases which will provide an [AutoDevOps-like](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/21) experience. In addition, leaning on [Fastlane](https://fastlane.tools/) will allow us to limit the complexity in the CI templates while still providing robust capabilities for mobile use cases.

## Competitive Landscape

There are several competitors in this space providing visual pipeline builders on top of their own CI/CD systems (Bitrise, Appcircle, Buddybuild, and Codemagic) and the more prominent players, including Visual Studio App Center, Firebase, and AWS Mobile Services.

## Who We Are

The Mobile DevOps SEG is a [Single-Engineer Group](https://about.gitlab.com/company/team/structure/#single-engineer-groups) within our [Incubation Engineering Department](https://about.gitlab.com/handbook/engineering/incubation/).

## How We Work

As we explore the opportunities and challenges in this space, we will share weekly demos. These demos will be recorded and shared in the [Weekly Demos issue](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues/7).

## Product Development Group Affinity

The Mobile DevOps SEG is primarily aligned with the [Verify](https://about.gitlab.com/handbook/product/categories/#verify-stage) stage, and more specifically the [Pipeline Authoring](https://about.gitlab.com/handbook/product/categories/#pipeline-authoring-group) and [Runner SaaS](https://about.gitlab.com/handbook/product/categories/#runner-saas-group). There is also some alignment with the [Integrations](https://about.gitlab.com/handbook/product/categories/#integrations-group) group.

## How To Contribute

#### GitLab Issues

Please feel free to create issues or participate in discussions in our [issue board](https://gitlab.com/gitlab-org/incubation-engineering/mobile-devops/readme/-/issues).

#### Slack

We can also be found in Slack at `#incubation-eng` (GitLab Internal)
