---
title: "Graph for Understanding Artifact Composition"
section: single
type: page
---

<div style="width: 100%">
  <div style="float:right; width:30%; background: aquamarine; padding-right: 10px">
    <img src="/images/illustrations/undraw/undraw_image_viewer_re_7ejc.svg">
  </div>
  <div style="float:none">
<h2>Our vision</h2>

<p>
GUAC (Graph for Understanding Artifact Composition) aims to fill in the gaps by ingesting software metadata, like SBOMs, and mapping out relationships between software.
When you know how one piece of software affects another, you’ll be able to fully understand your software security position and act as needed.
</p>
  </div>
</div>

## The current problem with software supply chain security

Software supply chain attacks are on the rise and it’s hard to know what your software is at risk for and how to protect it.
Many tools are available to help you generate software bills of materials (SBOMs), signed attestations, and vulnerability reports, but they stop there, leaving you to figure out how they all fit together.
GUAC provides an aggregated, queryable view across your whole software supply chain, not just one SBOM at a time.

To see how Guidewire Software stays ahead of threats, [read the case study](/static/guidewire_guac_casestudy.pdf).

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

## What people are saying about GUAC

<figure class=testimonial><blockquote>With the growing number of software supply chain security (SSCS) data, tools that allow us to find relevant information are crucial. Guac, providing graph representation of software packages, dependencies, vulnerabilities, attestations, etc. is a great tool for use cases in this domain. With mechanisms to ingest and certify data from various sources and GraphQL API to later query those data, we see it as a good foundation for our current and future SSCS efforts. Being a true open source initiative with a welcoming community is just a plus.</blockquote><div class=author><img src=https://guac.sh/images/illustrations/faces/3.png alt><h5>Dejan Bosanac</h5><span>Engineer at Red Hat</span></div></figure><figure class=testimonial><blockquote>At Yahoo, we have found immense value and significant efficiency by utilizing the open source project GUAC. GUAC has allowed us to streamline our processes and increase efficiency in a way that was not possible before. It allows us to ingest large number of SBOMs and also provides an interface to visualize the current state of images & packages used at Yahoo in real time. We look forward to continuing to utilize GUAC and contribute to its growth in any way we can.</blockquote><div class=author><img src=https://guac.sh/images/illustrations/faces/3.png alt><h5>Hemil Kadakia</h5><span>Sr. Mgr. Software Dev Engineering, Paranoids, Yahoo.</span></div></figure><figure class=testimonial><blockquote>As the CTO of ClearAlpha, I can't recommend GUAC enough for companies looking to boost their software security. GUAC's innovative approach to software supply chain security helps uncover hidden gaps and threats as we’re downloading dependencies and building apps, making it a perfect fit for our “solve it earlier” mindset at ClearAlpha. It also lines up with our commitment to transparency, open-source principles, and continuous learning. GUAC works well in teams practicing the rugged software manifesto, focusing on strong coding practices, constant testing, and automated tools to enhance security. Plus, its ability to trace risks back to their source aligns with our proactive risk awareness goals, enabling companies to spot and tackle potential issues early on. GUAC is just a fantastic tool to help any organization improve their software security with principles we all should value. If you're a tech founder, you'll definitely want to have GUAC on your team!</blockquote><div class=author><img src=https://guac.sh/images/illustrations/faces/3.png alt><h5>Sean Terretta</h5><span>CTO at ClearAlpha</span></div></figure><figure class=testimonial><blockquote>GUAC came along as an open-source software at the right time helping us pivot away from building a bespoke solution and involving ourselves with the best minds behind the project. The value we see with GUAC is its flexibility and plugin architecture leading up to helping the users achieve compliance at different levels. The biggest benefit of GUAC has been producing it in the open with a widespread community behind it, from Google to Kusari and others. As the industry progresses, the threats to the software supply chain will become more complex, and relying on a tool backed by people with many years of experience in the area would make things easier for Guidewire to consume.</blockquote><div class=author><img src=https://guac.sh/images/illustrations/faces/3.png alt><h5>Anoop Gopalakrishnan</h5><span>Vice President Of Engineering at Guidewire Software</span></div></figure>