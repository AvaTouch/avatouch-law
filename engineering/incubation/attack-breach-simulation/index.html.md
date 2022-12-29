---
layout: handbook-page-toc
title: Breach and Attack Simulation (BAS) Single-Engineer Group
---

## On this page
{:.no_toc .hidden-md .hidden-lg}

- TOC
{:toc .hidden-md .hidden-lg}

## Breach and Attack Simulation (BAS) Single-Engineer Group

The Breach and Attack Simulation (BAS) SEG is a [Single-Engineer Group](/company/team/structure/#single-engineer-groups) within our [Incubation Engineering Department](/handbook/engineering/incubation/).

### Product Development Group affinity

* [Composition Analysis group in the Secure stage](https://about.gitlab.com/handbook/product/categories/#composition-analysis-group) is charged with Dependency Scanning and [Operational] Container Scanning which both lend themselves to the reconnaissance.
* [Dynamic Analysis group in the Secure stage](https://about.gitlab.com/handbook/product/categories/#dynamic-analysis-group) owns API Security and DAST which can be expanded upon by emulating attacker behavior.
* [Threat Insights group in the Govern stage](https://about.gitlab.com/handbook/product/categories/#threat-insights-group) handles Vulnerability Management, Dependency Management, and Software Bill of Materials which all are great segues into targeted BAS scanning.
* [Vulnerability Research group in the Secure stage](https://about.gitlab.com/handbook/product/categories/#vulnerability-research-group) will provide benchmarking of our own scanners which can be augmented by extended coverage. The GitLab Advisory Database can be used as a source of threat intelligence for lining up vulnerabilities to target for emulation.

### Background

The complexity of public cloud networks means that a user may have ingress and egress points that are not adequately protected.  Using AI/ML, this SEG aims to determine what are the most vulnerable parts of a customers network, and suggest remedies to resolve.

The full Attack and Breach feature set involves the following steps:

* Recon
  * User defined? 
  * Automated tools such as [Flan Scan](https://github.com/cloudflare/flan)?
  * Are we interested in internal network devices or only ingress/egress assets?
* External Penetration
* Privilege Escalation & Persistence
* Command & Control
* Internal Penetration/Lateral Movement
* Collection & Data Exfiltration
* Destruction (Simulated)

This involves multiple entry point testing which can be simlated by building up a graph of all:

* People
* Computers
* Networks
* Devices
* software installed
* Libraries

Data sets:

*  Authenticated datasets (audit keys for AWS/GCP to build out network maps, extract DNS records etc)
* Certificate Transparency logs
* URL collection/datasets
* Subdomain brute forcing

The first iteration where can immediately add value is to provide our users with asset discovery/attack surface & inventories. 

Companies doing BAS:

* [Attack IQ](https://attackiq.com/)
* [XM Cyber](https://www.xmcyber.com/)
* [SafeBreach](https://safebreach.com)
* [Mandiant](https://www.mandiant.com/advantage/security-validation)

Companies doing Asset Discovery/Attack Surface Management AKA (Cyber Asset Attack Surface Management (CAASM):

* [SecurityTrails](https://securitytrails.com/)
* [Assetnote](https://assetnote.io)
* [Axonius](https://www.axonius.com/platform/cyber-asset-attack-surface-management-caasm)
* [Cortex](https://www.paloaltonetworks.com/cortex/cortex-xpanse/attack-surface-management)
* [Coalfire](https://www.coalfire.com/solutions/threat-and-vulnerability-management/attack-surface-management) 
* [Qualys](https://www.qualys.com/apps/continuous-monitoring/)


