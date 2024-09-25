---
title: Finding Hacktoberfest projects with GUAC
layout: post
authors: 
  - Ben Cotton
date: 2024-09-26
tags:
  - guac-does-that
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/5KfbgL9TqPc?si=Yla_GiE2bdoRiaYD" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

It's almost October, which means [Hacktoberfest](https://hacktoberfest.com) is just around the corner.
The best way to ensure your supply chain is secure and well-maintained is to contribute upstream.
Hacktoberfest can be a forcing function to start your upstream contributions.
But how do you figure out which Hacktoberfest participants in your dependency graph?
Use GUAC!

GUAC uses information from your software bills of materials (SBOMs) and the [deps.dev](https://deps.dev) service to build a graph of your software dependencies.
Included in this information is the `HasSourceAt` node, which gives the location of the package's source code.
This is often a GitHub or GitLab repository.
Conveniently, both of these sites are official sites for Hacktoberfest.
Projects hosted on either of those platforms can opt in by adding the "hacktoberfest" topic.
Both GitHub and GitLab offer an API for searching for projects.
So all of the information you need exists, you just have to tie it together.

The GraphQL query to return all packages with a `HasSourceAt` node is straightforward:

~~~~
{
  HasSourceAt(hasSourceAtSpec: {}) { 
      source{
        type namespaces{
          namespace names{
            name } 
        }
      }
  }
}
~~~~

But what do you do with the output?
I wrote a [short Python script](https://github.com/guacsec/guac-data/tree/main/scripts/guactober) that gets data from your GUAC server with the query above.
It then pulls a list of Hacktoberfest projects from GitHub and GitLab.
Finally, it prints any of your dependencies that appear in the Hacktoberfest list.
In just a minute or two, you can have a list of projects to go work on.

The output for the [demo data](https://docs.guac.sh/setup-ingest-data/) includes seven projects as of this writing:

~~~~
Here are the Hacktoberfest projects in your GUAC data:
github.com/grpc/grpc-go
github.com/schollz/progressbar
github.com/gopherjs/gopherjs
github.com/google/go-github
github.com/containerd/containerd
github.com/grpc/grpc-go
github.com/containerd/containerd
~~~~

Of course, you're not limited to what's in this example script.
You could modify it to rank based on OpenSSF Scorecard scores, the number of times a dependency appears in the graph, or other factors you can think of.
The power of GUAC is the way it enriches your SBOMs.
It collects additional information to make searches like this possible.
If you do something interesting with this, we'd love to hear about it.
Let us know in Slack or at an upcoming community meeting.
The [community page](/community) has all the details.
If you want to contribute to GUAC as part of Hacktoberfest, [we're participating]({{< relref "2024-09-25-hacktoberfest.md" >}}).