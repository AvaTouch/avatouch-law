---
layout: handbook-page-toc
title: "App integrations"
---

<link rel="stylesheet" type="text/css" href="/stylesheets/biztech.css" />

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

GitLab has chosen to restrict the ability to install apps, and we have a process to approve or restrict certain apps for our workspace. In order to integrate a new app with existing applications in our [tech stack](https://gitlab.com/gitlab-com/www-gitlab-com/-/blob/master/data/tech_stack.yml) such as Slack, you need to create a [vendor approval issue](https://gitlab.com/gitlab-com/Finance-Division/procurement-team/procurement/-/issues/new?issuable_template=App_Integrations).

The process to determine if a review is needed is based on the vendor's inherent risk rating, which is determined by risk factors that we identified subject to GitLab. The steps included in the vendor approval issue are meant to gather the information so that the Risk and Field Security team can complete the scoring.

|  | High-risk | Moderate-risk | Low-risk  | 
| --- |  --- |  --- |  --- 
| **Seats/Licenses** | 1000+  == `3` | 101 - 999  == `2`| 1 - 100  == `1` 
| **Volume** | Over 20,000 records <br> or volume of data == `3` | 5,001 - 19,999  == `2`| Less than 5,000 == `1`
| **Contractor Access / Integration** | Corporate user account <br> (GitLab.com, GCP, etc.) <br>/ 10+ systems integrated == `3` | Read/write access to <br> specific data sets (limited push/pull) <br>/ 4-9 integrated systems == `2` | Receives a file of <br> sensitive information <br> (no access to GitLab systems) <br>/ 1-3 systems == `1`
| **Compliance Frameworks in-scope** | Two or more == `3`| One == `2` | Zero == `1`
| **Data Classification** | Red == `3`| Orange == `2` | Yellow == `1` <br> Green == `0`

    Risk Score          High : 36 +                  Moderate  : 9 - 35               Low : less than 8

### Adding an app to Slack

Once the [vendor approval issue](https://gitlab.com/gitlab-com/Finance-Division/procurement-team/procurement/-/issues/new?issuable_template=App_Integrations) has been approved by all parties, please request approval to add the app to Slack following the steps below:

1. Make sure the app hasn't been pre-approved by our team by clicking on Apps in the left sidebar and find Available Apps. To find pre-approved apps in the App Directory, click Pre-Approved below Categories in the left column.
1. If the app isn't pre-approved, you can click on Add to Slack.
1. Add a custom message with more context about your request and also link the vendor approval issue.
1. Click Submit. You'll receive a direct message from Slackbot when your request has been reviewed by the team.

**Please note that this is only required for new apps that have not been reviewed or approved.** If your request is to add a new  process or update an existing process for how an application works in slack, please refer to our [Business Technology Change Management](/handbook/business-technology/change-management/) process.

### Adding an app/plugin to other systems owned by Team Member Enablement/Business Technology

If you need to add an app/plugin that connects with other systems owned by IT (not Slack), please create an issue in the [Team Member Enablement Issue tracker](https://gitlab.com/gitlab-com/business-technology/team-member-enablement/issue-tracker/-/issues/new?issuable_template=App_Integration) and follow the steps outlined there. 


