---
title: Mixing license information into your GUAC
date: 2024-08-01
authors: ["Ben Cotton"]
include_footer: true
---

[GUAC v0.8.0](../2024-07-25-guac-v0.8.0), which was released last week, includes the addition of a new data source for GUAC users: license data from [ClearlyDefined](https://clearlydefined.io/about).
While GUAC previously supported reading license information from software bills of materials (SBOMs), adding support for ClearlyDefined represents a big step forward.
ClearlyDefined provides a vetted and accurate representation of license information for a given release of software.

Software licenses aren’t strictly a security concern, but they’re a key fact about your dependencies.
Full software supply chain observability includes knowing the licenses in your supply chain, which helps you ensure you’re following license terms and your organizational requirements.

## How GUAC uses ClearlyDefined

GUAC maintainer Parth Patel decided to implement ClearlyDefined support as a certifier instead of a collector in order to ensure GUAC re-runs the query.
GUAC certifiers run on a scheduled basis to capture up-to-date information that may have changed since the last run.
License data is always incomplete because developers are always shipping new software releases, so this regular query ensures GUAC captures new license information.
If you choose, you can also have GUAC query ClearlyDefined when you ingest a new SBOM, although this does slow down the ingestion process.

GUAC is a tool for giving the information you need to make decisions, not to make decisions for you.
As a result, GUAC does not try to guess which response is accurate if the information in the SBOM and the information from ClearlyDefined conflict.
Both result in the creation of a CertifyLegal node in the graph, so you can decide which is more trustworthy on a case-by-case basis.

Internally, GUAC uses [package URLs](https://github.com/package-url/purl-spec) (pURLs) to identify specific software package releases.
However, ClearlyDefined uses a scheme they call “coordinates”.
Part of implementing support in GUAC meant developing a library to convert pURLS to coordinates.
Working with the ClearlyDefined community, Parth was able to develop a reference for mapping between the two systems.
In a great example of cross-community collaboration, ClearlyDefined added [comprehensive documentation for coordinates](https://docs.clearlydefined.io/docs/resources/coordinates#purl-type-mapping) based on Parth’s work.

One note of caution: ClearlyDefined’s API does not currently support batched queries. As a result, processing large dependency graphs may take longer due to rate limiting. Issue [#1168](https://github.com/clearlydefined/service/issues/1168) is open to add batched queries.

## About ClearlyDefined

Started at Microsoft, ClearlyDefined is now an incubating project within the [Open Source Initiative](https://opensource.org/) (OSI).
ClearlyDefined provides a centralized, curated source of information about software licenses.
The community takes public contributions and evaluates them in an open manner, resulting in a trusted source of information.
In addition, ClearlyDefined’s harvester services automatically search for license information when the ClearlyDefined service receives a request it can’t answer.
This helps fill the gap in information when a software producer does not include license information in an SBOM.

## How you can help

If you have a use case that’s well-served by this new feature, we’d love to hear about it.
If you have a use case that isn’t well-served, we want to know that, too.
Let us know in a [GitHub issue](https://github.com/guacsec/guac/issues), on [Slack](https://openssf.slack.com/archives/C03U677QD46), or in one of our regular meetings.
See the [Community page](https://guac.sh/community/) for more information.
We also welcome your contribution of new features to help expand GUAC’s capabilities.

The ClearlyDefined project is looking for contributions to code and license information. See their [“Get involved” documentation](https://docs.clearlydefined.io/docs/get-involved) for more information.