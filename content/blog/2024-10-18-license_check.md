---
title: Finding software licenses with GUAC
layout: post
authors: 
  - Ben Cotton
date: 2024-10-18
tags:
  - guac-does-that
---
<iframe width="560" height="315" src="https://www.youtube.com/embed/BMGeksS16Kc?si=vYDpnFWsKU_GkuT8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Licenses are the foundation of open source software.
They grant the permissions that we rely on to use, inspect, and modify code.
But software licenses can also place obligations on you.
This is why it's important to know what licenses exist in your dependency graph.

GUAC records the license information provided in your software bills of materials (SBOMs) into a `CertifyLegal` node.
That information isn't always complete, though, so GUAC augments with information from [deps.dev](https://deps.dev) and [ClearlyDefined](https://clearlydefined.io).
This gives you a lot of information to work with.
For example: you can find packages where ClearlyDefined's scan yields a different set of licenses than what the project reports.

To start, you can use a GraphQL query to return all packages and source locations with a `CertifyLegal` node:

~~~
{
  CertifyLegal(certifyLegalSpec: {}) {
    discoveredLicense
    declaredLicense
    subject {
      ... on Package {
        namespaces {
          namespace names{
            name
          }
        }
      }
      ... on Source {
        namespaces {
          namespace names{
            name
          }
        }
      }
    }
  }
}
~~~

But what do you do with the output?
I wrote a [short Python script](https://github.com/guacsec/guac-data/tree/main/scripts/license_check) that gets data from your GUAC server with the query above.
It then looks for packages and sources where the declared and discovered license strings don't match.
Because this can be a long list (the [demo data](https://docs.guac.sh/setup-ingest-data/) returns hundreds of results), you can also write the output to a CSV file.

This script is a simple demo.
It does not account for trivial differences.
It also doesn't try to make sense of the practical impact of license combinations.
You can see, though, how you can quickly write your own script to find out the answer to your own questions.

The power of GUAC is the way it enriches your SBOMs.
It collects additional information to make searches like this possible.
If you do something interesting with this, we'd love to hear about it.
Let us know in Slack or at an upcoming community meeting.
The [community page](/community) has all the details.