---
layout: handbook-page-toc
title: Support Engineer Resources
description: If you want to learn more about what support engineers do and how they do it, this is the place.
---

### A Day in the Life of a Support Engineer

As a Support Engineer at GitLab, the majority of your time will be focused on helping customers solve problems. This happens mostly through tickets, but can also happen through issues, screensharing calls, and emergencies.

### Getting Help

While working through various customer problems, you may need help. We have a wide and talented team that can help you at many levels:

- Managers: If your problem is related to process, or understanding direction, or cross-team collaboration, consider talking to your direct manager, or another manager whom may be working more directly on that problem. Managers in Support Engineering should be able to point you in the right direction and enable you to find the right help.
- Senior/Staff Support engineers: If your problem is debugging related, consider reaching out to a Senior+ Engineer. At the Senior+ level, engineers are expected to be acting as mentors, and technical experts. See our [Mentoring page for more information about how Senior+ Engineers are expected to help](/handbook/support/engineering/mentorship.html)

### Zendesk Instances

At GitLab, the Support Team currently manages 2 different [Zendesk Instances](/handbook/support/support-ops/documentation/zendesk_instances.html):

1. GitLab Support Instance:  [gitlab.zendesk.com](https://gitlab.zendesk.com)
1. GitLab US Federal Support Instance: [gitlab-federal-support.zendesk.com](https://gitlab-federal-support.zendesk.com)
  - Customer URL: [federal-support.gitlab.com](https://federal-support.gitlab.com), CNAME for full link (above).
  - Only Support Engineers who are US Citizens inside of the US have access.

### Ticketing Style Guide

We recommend reviewing the best practices and suggestions for [styling and responding to Zendesk tickets](/handbook/support/workflows/how-to-respond-to-tickets.html).

### What if I feel threatened or harassed while handling a Support request?

Just as Support team members are expected to adhere to GitLab's [Code of Conduct](/handbook/people-group/code-of-conduct), we also expect customers to treat the Support Team with the same level of respect. The [GitLab Community Code of Conduct](https://about.gitlab.com/community/contribute/code-of-conduct/) outlines the standards to which we hold the wider GitLab Community.

If you notice a threatening or hostile ticket, please tag the [Manager On-Call](/handbook/support/on-call/#manager-on-call) to respond with the following guidelines in our [Statement of Support](https://about.gitlab.com/support/general-policies/#please-dont-use-language-intended-to-threaten-or-harass).

### Support Team Contributions

We encourage all engineers to contribute to the product to help improve the customer experience directly. When working on merge requests (on the gitlab-org group) for code or for documentation, apply the
`Support Team Contributions` label so that we can track product contributions by support team
members.

Additionally, if the code change is specifically to improve the team's efficiency
(such as changes to admin for faster support), then add the `~"Support Efficiency"` label.

We also recommend using weight labels (frontend, backend, docs) to track the effort required for MRs.
While you can look at how others have labelled their MRs, the most important thing is that you are consistent in applying the labels to your own MRs
so that you can see which MRs required the most effort and your overall progress.
The number of MRs and their total weight are included in the [1:1 generator reports](https://gitlab.com/gitlab-com/support/toolbox/1-1-issue-generator).

An issue is created in the `support-team-meta` issue tracker at the
end of each week with a list of support team contributions merged in the past week. View the
[list of summary issues here](https://gitlab.com/gitlab-com/support/support-team-meta/issues?label_name%5B%5D=Support%20Team%20Contributions).

### Internal tools

- [Support Toolbox](https://gitlab.com/gitlab-com/support/toolbox) - Includes tools such as `json_stats` (analyze JSON logs), `strace_parser` (analyze `strace` output), `gitlabsos` (get all logs and other data from customers), etc.
- [Support Resources](https://gitlab.com/gitlab-com/support/support-resources/#support-resources) - Create test instances
- [GitLab Development Kit](https://gitlab.com/gitlab-org/gitlab-development-kit)
- [CustomersDot admin](https://customers.gitlab.com/admin/) - Where to manage Self-Managed licenses and where customers manage their subscriptions.
- [GitLab Regressions](https://regressions.gitlab.io/)

### External tools

- [ExplainShell](https://explainshell.com/) - Break down a terminal command

### Useful Browser Extensions

- Copy As Markdown - Used to copy the element in current page as markdown format ([Chrome](https://chrome.google.com/webstore/detail/copy-as-markdown/dgoenpnkphkichnohepecnmpmihnabdg?hl=en)/[Firefox](https://addons.mozilla.org/en-US/firefox/addon/copy-as-markdown/))
- Zendesk Download Router - Automatically routes Zendesk downloads into separate folders by ticket number ([Chrome](https://chrome.google.com/webstore/detail/zendesk-download-router/pgfhacdbkdeppdjgighdeejjfneifkml)/[Firefox](https://addons.mozilla.org/en-GB/firefox/addon/zendesk-download-router/)/[Opera](https://addons.opera.com/en-gb/extensions/details/zendesk-download-router/))
- GitLab Web Debugger - Aides in identifying the root cause of page load errors on GitLab.com and internal GitLab instances ([Chrome](https://gitlab.com/gitlab-com/gl-infra/gitlab-web-debugger))
- Zendesk Quicktab - Opens Zendesk tickets in a single browser tab ([Chrome](https://chrome.google.com/webstore/detail/zendesk-quicktab/imgmkpifcfhbfdklogcpdnkohifklebb))
- Note: Zendesk Quicktab was [removed from the Chrome marketplace in July 2020](https://support.tymeshift.com/hc/en-us/articles/360003993613-Install-Zendesk-Quicktab-Chrome-Extension) while ownership of the extension was in negotiations. Please read the [Zendesk support forum thread](https://support.zendesk.com/hc/en-us/community/posts/360001108948/comments/360012160754) for information on the current state of the extension and installing Zendesk Quicktab from the GitHub project.
- Calendly Meeting Scheduling Software - ad-hoc meetings, one-click booking ([Chrome](https://chrome.google.com/webstore/detail/calendly-meeting-scheduli/cbhilkcodigmigfbnphipnnmamjfkipp))
- GitLab Screenshare mode - allows to hide confidential information on your GitLab screen ([Chrome](https://gitlab.com/leipert-projects/gitlab-screenshare-mode#chrome)/[Firefox](https://gitlab.com/leipert-projects/gitlab-screenshare-mode#firefox))
