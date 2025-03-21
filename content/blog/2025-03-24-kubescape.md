---
title: GUAC now supports runtime Kubernetes SBOMs using Kubescape
layout: post
authors:
  - Jeff Mendoza
  - Ben Hirschberg
date: 2025-03-24
tags:
  - community
  - events
  - guac-does-that
---

With the release of [GUAC
v0.14.0](https://github.com/guacsec/guac/releases/tag/v0.14.0), GUAC includes a
Kubescape collector that can be run inside your Kubernetes cluster to watch for
new scan results from Kubescape and ingest those results into the GUAC supply
chain graph.

[Kubescape](https://kubescape.io/) is an open-source Kubernetes security
platform that provides comprehensive security coverage, from left to right
across the entire development and deployment lifecycle. It offers hardening,
posture management, and runtime security capabilities to ensure robust
protection for Kubernetes environments.

When Kubescape is [installed](https://kubescape.io/docs/install-operator/) as
an [Operator](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
in your Kubernetes cluster, it can continuously scan all running containers for
contents and vulnerabilities. These scan results can be accessed as Kubernetes
API server custom resources. Additionally, Kubescape can filter the SBOM scan
results based on [relevancy](https://kubescape.io/docs/operator/relevancy/)
based on eBPF observation.

With GUAC being the prime system resource for collating and correlating data
from across your supply chain, it only made sense to enable GUAC to incorporate
these Kubescape results. GUAC’s new ability to analyze both build-time and
run-time SBOMs in a single GraphQL API enables exciting new insights. We will
explore some of those in our Kubecon EU session "[Why Don’t We Have Both? Track
Build- and Run-time Information for Security With Kubescape and
GUAC](https://kccnceu2025.sched.com/event/1tx7x/why-dont-we-have-both-track-build-and-run-time-information-for-security-with-kubescape-and-guac-jeff-mendoza-kusari-ben-hirschberg-armo)". Please
join us there or look out for the recording.
