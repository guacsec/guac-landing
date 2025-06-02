---
title: "Contributing to GUAC"
section: single
type: page
---

Interested in making a contribution to GUAC?
This is the place to start!
Here are a few things you need to know.

If you're looking for an issue to get started on, check the ["good first issue"](https://github.com/search?q=user%3Aguacsec+label%3A%22good+first+issue%22++&type=Issues&ref=advsearch&l=&l=&state=open) and ["help wanted"](https://github.com/search?q=user%3Aguacsec+label%3A%22help+wanted%22++&type=Issues&ref=advsearch&l=&l=&state=open) tags in GitHub.

## Code of Conduct

GUAC is an OpenSSF Incubating Project.
The [OpenSSF Code of Conduct](https://openssf.org/community/code-of-conduct/) applies to all interactions in the GUAC community.

## Developer Certificate of Origin

We require all commits in a pull request to contain a `Signed-off-by` line which can be added by using the `-s` flag of `git commit`.
This is to enforce [a Developer Certificate of Origin (DCO)](https://wiki.linuxfoundation.org/dco).

## Contributor ladder

This contributor ladder outlines different contributor roles within the project, along with
responsibilities and privileges that come with them.

Since GUAC is a complex project, there are 5 software topic areas of interest:

- Ingestion: ingest software security metadata. Needs to write parsers for
  documents, maintain ingestion logic, write new collectors, etc.
- API: define the GraphQL/REST interface used between ingestion pipeline and
  backend, and between backend and GUAC-based applications and front-ends.
- Backends: define efficient code to interface with database backends (Neo4j,
  etc.).
- Front-end: GUAC visualisation libraries, Javascript, CSS
- Clients: GUAC CLI, CI Checks, Policy Engines, IDE Plugins, etc.

In addition, there are 2 non-code topic areas:

- Documentation: Maintaining docs and examples
    - Repositories:
        - [guacsec/guac-docs](https://github.com/guacsec/guac-docs)
        - [guacsec/guac-data](https://github.com/guacsec/guac-data)
- Web and marketing: Maintain GUAC’s public presence
    - Repositories:
        - [guacsec/guac-landing](https://github.com/guacsec/guac-landing)
        - (eventual social media accounts)

The contribution ladder is summarized in the table below.
All software and non-code topic areas use this latter.

| Role | Responsibilities | Requirements | Privileges | GitHub access level
| ---- | ---------------- | ------------ | ---------- | -------------------
| [Community Participant](#community-participant) | Follow [OpenSSF Code of Conduct](https://openssf.org/community/code-of-conduct/) | N/A | N/A | Read (default)
| [Reviewer](#reviewer) | Review contributions from other members | Prove technical expertise in at least one GUAC topic area | Can approve PRs | Write
| [Owner](#owner) | Set direction and priorities for topic area. Approval of contributions | Deep technical expertise in topic area. Proven record of reviews and authorship. | Invitation to owner&maintainers only channels | Write
| [Maintainer](#maintainer) | Set direction and priorities of project. Participate in weekly syncs | Expertise in 3 out of the 5 topic areas | (almost) complete repository access | Maintain

### Ladder levels

Each level of the ladder is also described in more details below.

#### Community Participant

Each new contributor to GUAC starts at this level.
There is no longer a formal requirement to
[register desire to contribute in issue #1](https://github.com/guacsec/guac/issues/1).

There are no requirements and no privileges.
Every community participant can create issues, fork the repository, create PRs, add comments to issues and PRs.

#### Reviewer

Once a community participant has demonstrated expertise in one GUAC topic area, owners and/or maintainers can propose graduating the community participant to the Reviewer role, upon a maintainer majority vote.

A reviewer will be responsible of reviewing contributions from other contributors that touch the corresponding topic area.
They should ensure that the PRs are adequately tested, follow the guidelines for the specific topic area.

#### Owner

A reviewer with significant review history and proven record of authorship in a specific GUAC topic area can be promoted to Owner status, upon a maintainer majority vote.

The Owner is in full control over the specific topic area.
They are expected to set direction and priorities, resolve technical trade-offs, prioritize between adding new features and handling technical debt.
As such, they must show a deep understanding of technical problems involved in this area.

Owners are invited to the GUAC owners and maintainers Slack channel.

Owners will be added to `CODEOWNERS` file, so they will be notified of PRs that touch their area of interest.

#### Maintainer

An owner that gains a deep understanding of GUAC architecture and design and can prove this by being an OWNER in at least 3 topic areas (including both software and non-code topic areas) will be promoted to maintainer, after a n-1 approval vote from the other maintainers, according to
the processes specified in [the governance document](https://github.com/guacsec/guac/blob/main/GOVERNANCE.md).

A maintainer has almost full access to the repository and is invited to all maintainer meetings, where they can contribute input that will set direction and priorities of the entire project.
They must have ability to commit to participating to at least the weekly maintainer sync meetings (currently 2 meetings totaling up to 2 hours every week).

A maintainer might be required to work with GUAC clients, thus they might be required to sign NDAs.

The [GUAC governance document](https://github.com/guacsec/guac/blob/main/GOVERNANCE.md) also details the role of technical advisory member, which is offered to members of the community that
have provided valuable input.
The technical advisory members have a consulting role and are the only role without an activity requirement.

### Moving up and down the ladder

To request being moved up the ladder, or to step down voluntarily, file an issue in the [governance repo](https://github.com/guacsec/governance).

#### Promotion

If you are requesting promotion, please include links to significant contributions in support of your request.
See [governance#15](https://github.com/guacsec/governance/issues/15) as an example.
The requirements for each level are given in the preceding sections.

#### Inactivity, Stepping down

Each role in the contribution ladder requires maintaining active contributions at the corresponding level.
Inactivity is harmful to the project, so maintainers can decide to remove privileges from inactive contributors, after a majority vote.
Inactivity is defined as periods longer than 3 months during which no contribution is being done.

Contributors also have the option of stepping down voluntarily, by contacting the maintainers when circumstances affect future contribution potential.
For highly active contributors that completely step away from the project, we will create an emeritus process.

GUAC contributors are happy to help you advance along the contributor ladder!


### Non-ladder levels

We recognize that the community contributor ladder is not for everyone and there are community participants that are active and want to play a bigger role without necessarily wanting to go deep into a certain area.

#### Triage team

The [guac-triage team](https://github.com/orgs/guacsec/teams/guac-triage) provides a way for community participants who are active to help out with triage activity without being part of a specific domain of the project contributor ladder.

This is meant to allow general community participants to play an active role in areas such as community engagement, project upkeep and other areas which may not part of the contributor ladder.

The triage team will have "triage" access to all repos in the guacsec organization and is meant to create a lightweight process to enable community participants to play more active roles.

#### Moving in and out of the triage team

##### Becoming part of the triage team

A maintainer sponsor is required to become part of the triage team. Any maintainer can spnosor a community participant to be part of the triage team.

This can be done by proposing a change in the [Triage team list](#triage-team-list) section.

##### Stepping down

If you are a member of the triage team and no longer want to be part of it, please open up a PR against this file to remove your name from the [Triage team list](#triage-team-list) section.

## Contacts

### Reviewers list

| Reviewer | Area | Vote |
|-|-|-|
| [dejanb](https://github.com/dejanb) | Ingestion | [issues/1885](https://github.com/guacsec/guac/issues/1885) |
| [mdeicas](https://github.com/mdeicas) | API | [issues/1885](https://github.com/guacsec/guac/issues/1885) |
| [robert-cronin](https://github.com/robert-cronin) | CLI | [issues/2361](https://github.com/guacsec/guac/issues/2361) |
| [robert-cronin](https://github.com/robert-cronin) | Ingestion | [issues/2361](https://github.com/guacsec/guac/issues/2361) |
| [nathannaveen](https://github.com/nathannaveen) | CLI | [issues/2361](https://github.com/guacsec/guac/issues/2361) |
| [funnelfiasco](https://github.com/funnelfiasco) | Front-end | [governance#57](https://github.com/guacsec/governance/issues/57)

### Owners list

| Owner | Area | Vote |
|-|-|-|
| [mrizzi](https://github.com/mrizzi) | [Backends (ent)](https://github.com/guacsec/guac/tree/4012842fab5d738f9bebf03f0cb44fc7ce39438b/pkg/assembler/backends/ent) | [issues/1310](https://github.com/guacsec/guac/issues/1310) |
| [funnelfiasco](https://github.com/funnelfiasco) | Web & Marketing | [governance#15](https://github.com/guacsec/governance/issues/15)
| [funnelfiasco](https://github.com/funnelfiasco) | Docs | [issues/2361](https://github.com/guacsec/guac/issues/2361)


### Maintainers

See the [MAINTAINERS file](https://github.com/guacsec/guac/blob/main/MAINTAINERS) for a list of current maintainers.

### Triage team list

| Member | Sponsor |
|-|-|
| [funnelfiasco](https://github.com/funnelfiasco) | [lumjjb](https://github.com/lumjjb) |

