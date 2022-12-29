---
layout: handbook-page-toc
title: "Developer Evangelism Team Workflow"
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}


## Team Workflow

Welcome to the Developer Evangelism team workflow page. Learn how the team works and how to work with the team. We primarily use the [Developer Evangelism Meta issue tracker](https://gitlab.com/gitlab-com/marketing/community-relations/dev-evangelism/meta/-/issues). We own the team label `dev-evangelism` and all of our other labels which are located at the [gitlab-com](https://gitlab.com/gitlab-com) group level. You can add the labels as necessary to any issue under this group for our team to track.

### How to work with the Developer Evangelism Team

Opening an issue is the best way to get a conversation started. The `dev-evangelism` label is at the `gitlab-com` group level, which means it can be added to any issue or merge request in the group's structure.

The `dev-evangelism` label is required, other labels are optional. The [DE-Bot](/handbook/marketing/community-relations/developer-evangelism/projects/#developer-evangelism-bot) or a team member will do the triage and add the necessary labels. To reduce noise in the comments, please add the `DE-Type::Consulting` and the relevant `Consulting` team labels yourself.

You can use the [request an evangelist issue template](https://gitlab.com/gitlab-com/marketing/community-relations/dev-evangelism/meta/-/issues/new?issuable_template=developer-evangelist-request) to submit a request. It provides a guide to collect the required information to triage the request.

### Labels

The Developer Evangelism team workflow is supported by labels, which help determine the type of issue, its status, and other relevant information. The team's primary label is `dev-evangelism`. All issues the team owns, are a part of, or needs to be aware of, should be tagged with `dev-evangelism`. Other Labels are listed below:

#### General labels

| **CFP Labels** | **Description** |
| ---------- | ----------- |
| `DE-DueSoon` | This is used to monitor DE issues that are due soon |
| `DE-Peer-Review` | Feedback is needed on the issue from DE team members |
| `DE-Ops` | Used to label issues related to the Developer Evangelism `Ops in DevOps` theme |
| `DE-Dev` | Used to label issues related to the Developer Evangelism `Dev in DevOps` theme |
| `DE-k8s` | Used to label issues related to the Developer Evangelism `Kubernetes` theme |

### Issue management

The team creates issues for iteration, team discussions, and other issues for internal processes. These issues are tracked using the following labels:

| **Process Labels** | **Description** |
| -------------- | ----------- |
| `DE-Process::Open` | Process related issues that are still being discussed or worked |
| `DE-Process::Pending` | Process related issues on hold due to an external factor |
| `DE-Process::Done` | Completed Process issues |
| `DE-Process::FYI` | Issues that require no action from the team, but need to be aware of |

#### Workflow

| Label | Use |
|-------|-----|
|`DE-Status::ToDo` | Issues that are planned for the future |
|`DE-Status::Doing` | Issues the team is currently working on |
|`DE-Status::Done` | Issues that have been completed |
|`DE-Status::OnHold` | Issues that are for whatever resume pending |
|`DE-Status::Cancelled` | Issues that have been cancelled, either by the team or the requestor in the case of a consulting request |
|`DE-Status::FYI` | Issues the team needs to be aware of but no action is required |

The default flow is from ToDo -> Doing -> (OnHold) -> Done. Issues with FYI don't go through any workflow, as they are owned by another team and will go through a different workflow.

#### Issue Types

These labels help identify the type of activity documented in an issue. These are useful for the team to understand where time is spent and assign appropriate DRIs.

| Label | Use |
|-------|-----|
| `DE-Type::Content` | Issues for Content creation, this can be any type of content |
| `DE-Type::Evangelist` | Issues for the Evangelist program |
| `DE-Type::Process` | Issues for operational activities of the team, mostly owned by the Developer Evangelism Program Manager |
| `DE-Type::Response` | Issues for Community Response activities |
| `DE-Type::Consulting` | Issues requested by other teams, more details below |

#### Consulting Labels

Requests from other teams for the Developer Evangelism to own, participate or collaborate on activities are classified as consulting, and these requests are usually labeled based on the team requesting. These are teams in the company that the Developer Evangelism team collaborate with often, here are their labels:

- `DE-Consulting::Alliances`
- `DE-Consulting::CorpComms`
- `DE-Consulting::CorpEvents`
- `DE-Consulting::Community`
- `DE-Consulting::Engineering`
- `DE-Consulting::FieldMktg`
- `DE-Consulting::GrowthMktg`
- `DE-Consulting::Product`
- `DE-Consulting::Sales`

These labels are required where an issue has `DE-Issue-Type::External` and `DE-Type::Consulting`, aside the team label `dev-evangelism` and `DE-Status` scoped label. If your team is not listed, you can still submit a request and it will be triaged appropriately

Issues created for Consulting count against team quarterly budgets, you can learn more in the [Request budgets section below](/handbook/marketing/community-relations/developer-evangelism/workflow/#request-budgets).

#### Bot Labels

These labels are automatically assigned by the [DE-Bot](/handbook/marketing/community-relations/developer-evangelism/projects/#developer-evangelism-bot) for triaging purposes.


| Label | Use |
|-------|-----|
| `DE-Bot::Auto` | Issue is automatically created by DE-Bot and will be closed after a period, usually 2 weeks from creation |
| `DE-Bot::Hold` | Issue is currently on hold and should not be triaged by teh DE-Bot except where it has been in the Hold status for too long. |
| `DE-Bot::Skip` | The DE-Bot should not perform any action on issues with this label
| `DE-Bot::Triage` | Issue has been silent for a while and needs to be triaged |
| `DE-Due::AddDate` | An Issue needs a due date |
| `DE-Due::N/A` | Due date is not needed because the team doesn't own the issue or a due date is not applicable |
| `DE-Due::Past` | Issue is past its due date |
| `DE-Due::Soon` | Issue is due soon |


#### Other Labels

| Label | Use |
|-------|-----|
| `DE-Release-Evangelism` | Release Evangelism issues, often autocreated and closed by the DE-Bot |
| `DE-Issue-Type::External` | Issues created by Other teams |
| `DE-Issue-Type::Internal` | Issues created & owned by the DevEvangelism team

#### CFP Labels

These labels are used to track workflow of the CFP submissions. 

| Label | Use |
|-------|-----|
| `CFP` | Identifies CFP labels, this is needed |
| `CFP::Upcoming` | Identifies CFPs that will be open soon |
| `CFP::Open` | Identifies Open CFPs |
| `CFP::Closed` | Identifies Closed CFPs |
| `CFP::Cancelled` | Identifies Cancelled CFPs |
| `CFP::Submitted` | Identifies that submissions were made for the CFP |
| `CFP::Accepted` | Identifies if any submission was accepted for a CFP |
| `CFP-EDU` | Identifies CFPs that are relevant to the Education team |
| `CFP-OSS` | Identifies CFPs that are relevane to the Open Source teams |
| `CFP-Submitted::{0..7}` | This is used to note the number of submissions that were made for metrics purposes |
| `CFP-Accepted::{0..7}` | This is used to note the number of acceptances for metrics purposes | 


### CFP Workflow

The CFP workflow is based on the [CFP labels](#cfp-labels) explained above. 

```plantuml
start
: CFP, CFP::Upcoming;
: CFP, CFP::Open;
if (CFP submissions) then (yes)
    : CFP, CFP::Submitted, CFP-Submitted::{0..7};

    if (CFP is Accepted) then (yes)
        : CFP, CFP::Accepted, CFP-Accepted::{0..7};
    else (no)
        : CFP, CFP::Closed;
    endif;
elseif (No submissions) then (missed)
    : CFP, CFP::Closed;
else  (cancelled)
    : CFP, CFP::Cancelled;
endif
stop
```

Example CFP workflow using [quick actions](https://docs.gitlab.com/ee/user/project/quick_actions.html):

1. Planning to submit, or when you have submitted already: 
    1. Create a new [CFP issue](https://gitlab.com/gitlab-com/marketing/community-relations/dev-evangelism/meta/-/issues/new?issuable_template=cfp). 
    2. The issue template already sets the `~"CFP" ~"CFP::Open"` labels.
    3. Set the due date to the CFP submission due date. 
2. Submitted 1 talk:
    1. Change the label to `~CFP-Submitted ~CFP-Submitted::1`
    2. In case you have submitted multiple talks, adjust the `~CFP-Submitted::` scoped label to reflect the correct number. 
    3. Update the `submissions` section in the issue. Comment on the issue for visibility. 

```
/label ~CFP-Submitted ~CFP-Submitted::1 
```

3. After the CFP closed, set the `CFP::Closed` label and update the due date to the CFP notification date listed in the issue.

```
/due <cfo notification date>
```

4. CFP notifications come in, and at least 1 talk was accepted.
    1. Change the label to `~CFP-Accepted ~CFP-Accepted::1`
    2. In case you have multiple talks accepted, adjust the `~CFP-Accepted::` scoped label.
    3. Comment on the issue with the talk titles for visibility. 
    4. Set the due date to the event date, and ensure all speakers are assigned.  

```
/label ~CFP-Accepted ~CFP-Accepted::1
```

5. When the event is done, update the issue with feedback and results.
    1. Add talk videos to the [YouTube playlist](/handbook/marketing/community-relations/developer-evangelism/#youtube-playlist), if existing.
    2. Mark the issue as `DE-Status::Done` and close it.

```
/label ~DE-Status::Done
/close
```

If no talks were accepted, only close the issue shown above.

If the CFP closed without submission, add the `CFP::Closed` label. In case the CFP was planned to submit, and decisions were made otherwise, add the `CFP::Cancelled` label. 


### Boards

[Team General Issue Board](https://gitlab.com/groups/gitlab-com/-/boards/1565342?&label_name[]=dev-evangelism){:.btn .btn-purple-inv .btn-lg}
[Team Activity Type Issue Board](https://gitlab.com/groups/gitlab-com/-/boards/3811304?label_name[]=dev-evangelism){:.btn .btn-purple-inv .btn-lg}
[CFP Issue Board](https://gitlab.com/groups/gitlab-com/-/boards/1616902?label_name[]=CFP){:.btn .btn-purple-inv .btn-lg}


### Request budgets

In order to prevent burnout, prioritize requests appropriately, and ensure we successfully deliver on the requests to which we commit, our team has created budgets for our internal stakeholders. These budgets encourage team members to prioritize their requests, ensuring our team addresses the highest priority needs for GitLab. 

These request types fall into the following categories: 
1. Event requests
1. CFP requests
1. Content requests 

Ongoing activities including team-driven content creation and speaking oppportunities that supports our goals and OKRs, release support, and social media monitoring, including Hacker News, do not count towards any team budgets. 

#### Event requests

Event requests include both event attendance (ex: attending client meetings, event staffing, attending dinners or social events, monitoring events for news) and speaking engagements at events such as demos and presentations. 

#### CFP (Call for Proposals) requests

CFP requests include asking a Developer Evangelist to submit a proposal for an event or media opportunity or support a fellow team member in submitting to an open CFP. 

See [Requesting a Developer Evangelist to submit a CFP](/handbook/marketing/community-relations/developer-evangelism/cfps/) to request a Developer Evangelist to submit to a CFP for a corporate, field, or partner event.

#### Content requests

Content requests include blog post, podcasts, media interviews, or any request that involves engaging a Developer Evangelist in a media opportunity. 

#### Scoring requests 

| Request Type | New / Existing Content | Budget score |
| ------------ | ---------------------- | ------------ |
| Event        | New                    | 3            |
| Event        | Existing / No content  | 1            |
| CFP          | New                    | 2            |
| CFP          | Existing               | 1            |
| Content      | New                    | 2            |
| Content      | Existing               | 1            |

Each team listed below is allocated 15 points per quarter for requests: 

| Team                       | Team Label  |
|----------------------------|------------------|
| Corporate Events           | `DE-Consulting::CorpEvents`  |
| Corporate Communications   | `DE-Consulting::CorpComms`   |
| Community Relations        | `DE-Consulting::Community`   |
| Growth Marketing           | `DE-Consulting::GrowthMktg`  |
| Field Marketing / ABM      | `DE-Consulting::FieldMktg`   |
| Sales / SDRs               | `DE-Consulting::Sales`       |
| Alliances                  | `DE-Consulting::Alliances`  |
| Product                    | `DE-Consulting::Product`     |
| Engineering                | `DE-Consulting::Engineering` |



If your team is not listed above, we will handle your request based on our availablity.  


#### Managing requests

This process covers any content request, Webcast, Interview, Meetup, etc. The process involves the following:

- Requestors should assign a label that identifies their team and a weight correlating with their budget score to allow us to track each team's budget consumption. 
- A member of the Developer Evangelism team will triage the issue and provide all necessary details and directions
- The necessary labels are applied to the issue as actions are taken on the request
- Once the request is complete, the issue is assigned back to the requestor to provide the necessary metrics generated as a result of the before it is closed.

## DE-Bot   

TBD

### Triage Rules

TBD

### Bot Automations

TBD

## Metrics

TBD


