---
layout: handbook-page-toc
title: "AppSec's Engagement Plan and Ways to Measure Usage of Secure Code Warrior"
---

# Engagement Goal, Plan, and, Ways to Measure Usage of Secure Code Warrior

## Engagement Goal

Developer = Backend + Frontend Engineers. See [Org Chart](https://comp-calculator.gitlab.net/org_chart) for more information on the number and types of developers at GitLab.

- 90% of developers being onboarded create an account in Secure Code Warrior
- 80% of developers complete relevant training within 3 months of starting
- 25% of developers participate in the semi-annual tournament
- 50% of developer accounts are spending at least an hour in the platform each month

### Later:
- 75% of developers in high risk teams ("high risk" is defined as teams or groups that see the most amount of vulnerabilities reported in their part of the application in a given year) have completed one course, per year, in SCW

## Engagement Plan

- Integrating Secure Code Warrior into [new hire onboarding template](https://gitlab.com/gitlab-com/people-group/people-operations/employment-templates/-/blob/main/.gitlab/issue_templates/onboarding_tasks/department_development.md ) as a checklist item that needs to be finished within the first 3 months of starting at GitLab
   - An Access Request (AR) would be created automatically requesting the new hire access to Secure Code Warrior and the request would ping the `@gitlab-com/gl-security/appsec` DL on the AR issue. The AppSec person on triage rotation picks up the AR.
- Monthly Slack announcements calling out the top 3 vulnerabilities seen in our last Security Release, announcement to be made by the AppSec Primary for that release (see [Release Managers](https://about.gitlab.com/community/release-managers/)), and, how developers can learn to identify and fix them
- Integrating Secure Code Warrior with GitLab CI would greatly help drive continuous engagement
- Kick-off tournament open to all Development engineers at GitLab. Prizes would be given for the top 3 players of the tournament.

## How to measure what, when, and, why?
**[Trailing, 3 months]** _Integrating Secure Code Warrior into new hire onboarding template as a checklist item that needs to be finished within the first 3 months of starting at GitLab_
- Measure the number of new hires that sign up on Secure Code Warrior
   - Measure monthly
- Measure the number of new hires that finish the SCW onboarding course within 3 months
   - Measure monthly
- Measure how many left the course midway
   - Measure monthly
- For the users who signed up, measure how many hours they spent in the platform
   - Measure monthly
- For the users who signed up, measure how many activities they did in the platform
   - Measure monthly

**[Trailing, 1 month]** _Those who sign in to Secure Code Warrior are able to use it successfully_
- Across all users, measure how many hours they spent in the platform
   - Measure daily, review monthly
- Across all users, measure how many activities they did in the platform
   - Measure daily, review monthly

**[Leading & Trailing]** _Monthly Slack announcements calling out top 3 vulns seen in our last Security Release and how developers can learn to identify and fix them_
- How many people are reacting to the Slack announcement?
   - Measure when we make the Slack announcement
- Are the number of new people signing up on the platform increasing after the Slack announcement?
   - Measure when we make the Slack announcement
- Is the existing user engagement increasing after the Slack announcement?
   - Measure when we make the Slack announcement
- Are developers doing the same challenges from vulnerability areas identified in the Slack message? If not, does the Slack announcement need to be tweaked to encourage more engagement?
   - Measure when we make the Slack announcement

**[Trailing, 1 month]** _Integrating Secure Code Warrior with GitLab CI would greatly help drive continuous engagement_
- How many developers are clicking on the training link on the security issue created by SCW?
   - Measure monthly
- Those clicking on the link, are they completing the training on SCW?
   - Measure monthly
- What feedback are we getting from developers on this integration?
   - Measure monthly
- How should we capture and improve on this feedback?
   - Measure monthly

**[Trailing, 6 months]** _Semi-annual tournaments for all developers at GitLab_
- How many developers are signing up for the semi-annual tournament?
   - Measure semi-annually (during the tournament)
- How engaged are the developers on the platform?
   - Measure semi-annually (during the tournament)
- What feedback are we getting from developers on the tournament?
   - Measure semi-annually (during the tournament)
- How should we capture and improve on this feedback?
   - Measure semi-annually (during the tournament)
