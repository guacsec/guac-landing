---
title: "Why GUAC?"
section: single
type: page
---

## The current problem with software supply chain security

Software supply chain attacks are on the rise and it’s hard to know what your software is at risk for and how to protect it.
Many tools are available to help you generate software bills of materials (SBOMs), signed attestations, and vulnerability reports, but they stop there, leaving you to figure out how they all fit together.
GUAC provides an aggregated, queryable view across your whole software supply chain, not just one SBOM at a time.

## From data to knowledge

Consider the [DIKW pyramid](https://en.wikipedia.org/wiki/DIKW_pyramid).
You have *data* about your software supply chain in the form of SBOMs, vulnerability statements, and the like.
GUAC builds a graph of the relationships between the data in order to provide *information*.
With GUAC, you can ask questions of your supply chain relationships to get *knowledge*.
By ingesting local information and trusted third-party sources, GUAC gives you the ability to perform a comprehensive analysis.

## Use cases

GUAC is for developers, operations, and security practitioners who need to identify and address problems in their software supply chain, including proactively managing dependencies and responding to vulnerabilities.
GUAC provides supply chain observability with a graph view of the software supply chain and tools for performing queries to gain actionable insights.

Here are some common use cases for GUAC.
[Let us know](/community) yours.

### Developers

* Identify deprecated and unsupported dependencies
* Discover “version sprawl”, where several versions of the same dependency are included
* Locate and remediate vulnerable dependencies
* Identify risky upstreams based on security practices evaluated by OpenSSF Scorecard

### Operations engineers

* Locate and remediate vulnerable dependencies

### Security engineers

* Locate and remediate vulnerable dependencies
* Prevent known vulnerable packages and sources from being used in applications

### Open Source Program Offices

* Identify strategically important open source upstreams
* Identify open source upstreams that could benefit from security help based on OpenSSF Scorecard results

## Differentiation

GUAC has three key differentiating features from other tools in this space

* **Works on more than one SBOM at a time.** This allows observability into the entire software portfolio instead of application-by-application.
* **Aggregates additional data beyond the SBOM.** GUAC brings in data like dependencies and vulnerabilities from trusted third-party sources, enriching the supply chain graph.
* **Provides APIs and a visualization tool.** GUAC’s query and visualization tooling let the user get the answers to the questions they need to ask.
