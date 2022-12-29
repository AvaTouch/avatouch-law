---
layout: handbook-page-toc
title: Server Runtime Single-Engineer Group
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

## Server Runtime Single-Engineer Group

The Server Runtime SEG is a [Single-Engineer Group](/company/team/structure/#single-engineer-groups) within our [Incubation Engineering Department](/handbook/engineering/incubation/).

The goal of this SEG is to explore how we can increase customer usage and company revenue by providing an alternative to GitPod or Codespaces directly within GitLab. Although GitLab [integrates with GitPod](https://www.gitpod.io/blog/gitlab-integration/), there may be opportunities to provide convenience to customers by delivering a cloud hosted development environment natively within GitLab.com. We strive to provide an easy way for GitLab users to be able to run and test their code on the GitLab platform. It will enable a remote development experience where you can modify and run your code on any device with access to a browser.

## Issue Link

[https://gitlab.com/gitlab-org/gitlab/-/issues/329602](https://gitlab.com/gitlab-org/gitlab/-/issues/329602)

## Goals

The inital goal of the Server Runtime SEG is to build a custom server runtime / control plane that is not built on any existing technology. The custom runtime plane will be able to deploy server runtime environments (and IDEs) to a variety of targets including Kubernetes and Cloud VMs.

The goal is to build a custom control plane that can do the following:

- Can be installed in any Kubernetes Cluster
- Will offer “tight” integration with GitLab
- Can offer a multitude of IDE experiences such as VS Code, Jupyter Hub, Vim, etc.
- Can be run in our own Kubernetes cluster on GitLab.com as a free or paid offering
- Will support provisioning IDEs on Kubernetes and non-kubernetes environments
- Can run in headless mode, where you can connect your own local IDE or the GitLab Web IDE to the environment

The architecture for the Custom Server Runtime can be found [here](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/custom-server-runtime-playground/-/blob/main/Readme.md#architecture)

## Updates

The latest update for the Server Runtime SEG is here:

<figure class="video_container">
    <iframe width="600" height="340" src="https://www.youtube.com/embed?max-results=1&controls=1&showinfo=0&rel=0&listType=playlist&list=PL05JrBw4t0Kr6sicAh753uzvoPqrGZuLB" frameborder="0" allowfullscreen></iframe>
</figure>

A complete list of weekly updates can be found [here](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/meta/-/issues/1).

## References

### Relevant issues

- [Original Issue](https://gitlab.com/gitlab-org/gitlab/-/issues/329602)
- [Remote Development Strategy](https://gitlab.com/gitlab-org/gitlab/-/issues/377921)
- [Custom Server Runtime Playground Repository](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/custom-server-runtime-playground)

### Examples for Custom Server Runtime

- [Go Example](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/basic-go-example)
- [Opening Ports Example](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/basic-go-webserver)
- [Vim Example](https://gitlab.com/gitlab-org/incubation-engineering/server-runtime/shell-script-vim-example)