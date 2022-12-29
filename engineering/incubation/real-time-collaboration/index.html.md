---
layout: handbook-page-toc
title: Real-time Editing of Issue Descriptions (REID) Single-Engineer Group
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

## The Real-time Editing of Issue Descriptions (REID) Single-Engineer Group

The Real-time Editing of Issue Descriptions (REID) SEG is a [Single-Engineer Group](/company/team/structure/#single-engineer-groups) within our [Incubation Engineering Department](/handbook/engineering/incubation/).

This group is focused on Real-time collaborative editing of issue descriptions.

The goal is to have real-time collaborative editing of issue descriptions in order to turn issues into a fully real-time collaborative text-editing experience.

There are additional ideas within the [Real-time collaboration Epic](https://gitlab.com/groups/gitlab-org/-/epics/2345), however the goal of this SEG is the minimal functionality described above.

## Updates

<figure class="video_container">
    <iframe width="600" height="340" src="https://www.youtube.com/embed?max-results=1&controls=0&showinfo=0&rel=0&listType=playlist&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo" frameborder="0" allowfullscreen></iframe>
</figure>

| | Date | Topic | Description | Video |
|---|:----------:|-----------------------------------|-----|-----|
| 14 | 2022-12-21 | An ActionCable based Y.js WebSocket and BroadcastChannel provider | Editor bindings | [https://www.youtube.com/watch?v=g--9JLOMXeQ](https://www.youtube.com/watch?v=g--9JLOMXeQ) |
| 13 | 2022-12-12 | Rust available in gdk and base images | Adding Rust | [https://www.youtube.com/watch?v=xmj7SzYIo1o](https://www.youtube.com/watch?v=xmj7SzYIo1o) |
| 12 | 2022-11-17 | Adding Rust to GitLab Pt.2 | Adding Rust to gdk, CI, etc. | [https://www.youtube.com/watch?v=K_vidq8VdAs](https://www.youtube.com/watch?v=K_vidq8VdAs) |
| 11 | 2022-11-02 | Adding Rust to GitLab | Shipping a gem with a native extension is tricky and extends the scope of the project. | [https://www.youtube.com/watch?v=IQS81adVWWg](https://www.youtube.com/watch?v=IQS81adVWWg) |
| 10 | 2022-10-19 | Message protocol, Editor bindings, Awareness Pt. 2 | Two busy weeks, and lots of complexity. | [https://www.youtube.com/watch?v=wJnvhW4eBKQ](https://www.youtube.com/watch?v=wJnvhW4eBKQ) |
| 9 | 2022-10-06 | Real-time demo (y-rb usage) | Celebrate the first table `y-rb` multip-platform release with a sandbox demo. | [https://www.youtube.com/watch?v=1gfYfUMh3dU](https://www.youtube.com/watch?v=1gfYfUMh3dU) |
| 8 | 2022-09-16 | Change of plans | Awareness feature not to ship to current issue sidebar and y-rb multi-platform releases. | [https://www.youtube.com/watch?v=x47YnULTiro](https://www.youtube.com/watch?v=x47YnULTiro) |
| 7 | 2022-08-18 | Ruby+Rust | Awareness feature about to ship, and a little intro to how Ruby+Rust bindings work. | [https://www.youtube.com/watch?v=ng20jSo2TIs](https://www.youtube.com/watch?v=ng20jSo2TIs) |
| 6 | 2022-08-05 | Progress & Roadmap | Progress on the work to ship the Awareness widget, and an outlook for what is coming next. | [https://www.youtube.com/watch?v=ZSdpj_YxsCE](https://www.youtube.com/watch?v=ZSdpj_YxsCE) |
| 5 | 2022-07-22 | JTBD and Progress Update | JTBD (Jobs to be done) and Iteration on the Awareness UI | [https://www.youtube.com/watch?v=S0s-s45zVv8&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=2](https://www.youtube.com/watch?v=S0s-s45zVv8&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=2) |
| 4 | 2022-07-06 | Awareness UI/UX and a CRDT database | Where and how to add the presence indicators on the issue page. A database for CRDTs is usually not necessary, but can become interesting for cases where we need a simple way to fetch the initial document state. | [https://www.youtube.com/watch?v=B094U_DvL-s&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=3](https://www.youtube.com/watch?v=B094U_DvL-s&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=3) |
| 3 | 2022-06-22 | The Awareness feature | Technical challenges on rolling out real-time features at scale. Memory and resource concerns and how to mitigate them. | [https://www.youtube.com/watch?v=ZPH9tvcPDfc&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=4](https://www.youtube.com/watch?v=ZPH9tvcPDfc&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=4) |
| 2 | 2022-06-09 | Tech design & terminology | A proposal for real-time collboration at GitLab. The presented tech design aims to be a comprehensive guide and peer-reviewed document | [https://www.youtube.com/watch?v=crzCYkMk5XQ&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=5](https://www.youtube.com/watch?v=crzCYkMk5XQ&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo&index=5) |
| 1 | 2022-05-25 | First update | The y-rb Ruby gem and how we are going to use it to bring real-time collaboration to GitLab. | [https://www.youtube.com/watch?v=5mTS64Y-rX0&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo](https://www.youtube.com/watch?v=5mTS64Y-rX0&list=PL05JrBw4t0KpPmRsaVaDOoWyIp1iKacZo) |

## Vision

> Make real-time collaboration on GitLab work for everything.

## Mission

A user should never have to leave the GitLab application for tasks like pair programming, collaborating on isssues, merge requests, tech designs and RFCs.

## JTBD

### Foundation

GitLabs software stack enables real-time collaboration via [Websockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket), in particular [GraphQL subscriptions](https://graphql.org/blog/subscriptions-in-graphql-and-relay/). Real-time comes with certain complexities when users want to collaboratively edit text, in particular rich text. In order to allow multiple parties to edit the same *text* concurrently, we must ensure a conflict-free replication mode between all participating clients. There are several ways to achieve this, but we utilize [CRDTs](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type). CRDTs allow us to concurrently edit state from `1, 2, … n` clients and eventually end up with a consistent representation of the document on all clients.

Every participant in the editing process is a client (in comparison to [Operational Transformation](https://en.wikipedia.org/wiki/Operational_transformation)). The CRDT we picked ([YATA](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types)) has a popular frontend implementation [Y.js](https://github.com/yjs/yjs) and we have created bindings for its [Rust](https://www.rust-lang.org/) port [`y-crdt`](https://github.com/y-crdt/y-crdt). This allows our Ruby on Rails backend to just act as one more client.

#### The `y-rb` gem

**Current State:** Published to [RubyGems](https://rubygems.org/gems/y-rb).

This [Ruby](https://www.ruby-lang.org/en/) gem is developed under the `y-crdt` umbrella ([The y-crdt organization](https://github.com/y-crdt)) and brings basic and complex shared types (Array, Map, Text, XML) to Ruby. The encoded updates and state vectors are a 100% compatible with [Y.js](https://github.com/yjs/yjs) and therefore state can be synced between the JavaScript frontend and the Ruby backend in a seamless way. This allows us to e.g. add, update, or remove labels via the GitLab UI but also with background jobs (some bot adding a label concurrently).

- [Project](https://gitlab.com/gitlab-org/incubation-engineering/real-time-editing/yrb)

#### The `y-rb_redis` gem

**Current State:** Started

This [Ruby](https://www.ruby-lang.org/en/) gem is developed under the `y-crdt` umbrella ([The y-crdt organization](https://github.com/y-crdt)). It is a thin abstraction layer to allow persisting changesets to Redis. The updates produced by `y-crdt` documents are stored as easy to store and fetch elements in a list. This allows us to persist and restore documents efficiently.

- [Project](https://gitlab.com/gitlab-org/incubation-engineering/real-time-editing/yrb-redis)

#### The `y-rb_actioncable` gem

**Current State:** Started

The default ActionCable implementation has no delivery guarantees (we look for `at-least-once`), and no atomic broadcast mechanism. The order of messages sent should be the same when they are received.

### Awareness

**Current State:** Active development

Starting a collaborative editing session should be exactly the same as opening and editing an issue today. In case a second user starts to work on an issue, the backend will create a *collaborative editing session* users automatically and makes sure that all changes (deltas) are synced between all participating parties.

Awareness helps us to see who we are collaborating with and how. It helps us answering the following questions:
- Who is online and collaborating with me?
- Who is actively participating?

#### TODO

* UX: Create a session and awareness model that allows collaborators to "see" each other and their current state (present/away)
*

### Editor bindings

**Current State:** Started

To determine and replicate a change to the description field, we need to encode everything that a user does as a change event (delta). Y.js uses a binary encoded representation to optimize payloads, but essentially it is a list of operations. One example of how this looks like is the [Quill Delta Format](https://quilljs.com/docs/delta/).

The GitLab UI does not rely on a uniform text editor but instead offeres a mix of `textarea`, `tiptap/prosemirror`, `Web IDE`, …, multiple editor modes (Raw, WYSISWYG), and post-edit transforms (Markdown parser → references). We need to build a transform layer to broadcast changes made to a text field in a conflict-free format, and reversly, apply incoming changes seamlessly in the editor.

#### TODO

* Use the concept of [progressive enhancement](https://developer.mozilla.org/en-US/docs/Glossary/Progressive_Enhancement). Real-time is a feature of the editor, not the product.
* Move parser to frontend (WASM)
* Write a binding (transform) that allows to incrementally receive and apply updates in any text editing mode

## Product Development Group affinity

- [Code Review](https://about.gitlab.com/handbook/product/categories/#code-review-group)
- [Source Code](https://about.gitlab.com/handbook/product/categories/#source-code-group)
- [Editor](https://about.gitlab.com/handbook/product/categories/#editor-group)
- [Product Planning](https://about.gitlab.com/handbook/product/categories/#product-planning-group)
- [Project Management](https://about.gitlab.com/handbook/product/categories/#project-management-group)

## Links

- [Epic](https://gitlab.com/groups/gitlab-org/incubation-engineering/real-time-editing/-/epics?state=opened&page=1&sort=start_date_desc)
- [Issues](https://gitlab.com/gitlab-org/incubation-engineering/real-time-editing/real-time-editing-issue-descriptions/-/issues)

### Reading List

* [Hybrid Anxiety and Hybrid Optimism: The Near Future of Work](https://future.a16z.com/hybrid-anxiety-optimism-future-of-work/)
