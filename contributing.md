---
editors:
  - name: Robin Berjon
    email: robin@berjon.com
    url: https://berjon.com/
    github: darobin
    twitter: robinberjon
    mastodon: "@robin@mastodon.social"
    affiliation:
        name: Protocol Labs
        url: https://protocol.ai/
  - name: Juan Caballero
    email: bumblefudge@learningproof.xyz
    url: https://learningproof.xyz
    github: bumblefudge
    twitter: by_caballero
    mastodon: "@by_caballero@mastodon.social"
    affiliation:
        name: LearningProof XYZ
        url: https://learningproof.xyz
reviewers:
  - name: Rod Vagg
    github: rvagg
  - name: Volker Mischke
    github: vmx
---

# Multiformats Governance Process

The values in multiformats are investments of finite namespace towards
broadly-useful utilities, and many of the current entries are already
foundational low-level building blocks for both data and network layers and are
used in IPFS, IPLD, libp2p, and beyond. As a result, it is particularly
important that these values be managed in such a way that guarantees that they
are maximally reliable, interoperable, useful, and safe. This document captures
the process that is used to manage the multiformats specifications and the
registries that support them.

## Topics

- [Multiformats Governance Process](#multiformats-governance-process)
  - [Topics](#topics)
  - [Introduction](#introduction)
  - [Code of Conduct and Ways to Contribute](#code-of-conduct-and-ways-to-contribute)
  - [The Process](#the-process)
    - [Reporting Issues](#reporting-issues)
    - [Multiformats Protocol Specifications](#multiformats-protocol-specifications)
    - [Multiformats Protocol Refinements](#multiformats-protocol-refinements)
    - [Multiformats Registries](#multiformats-registries)
    - [Multiformats Registrations](#multiformats-registrations)
  - [Acknowledgements](#acknowledgements)

## Introduction

The expectation is that once a format specification and a critical mass of
entries in its registry both reach "stable" status, changes to the
protocol-and-format specifications themselves should be limited and are more
likely to be clarifications or bug fixes. This goes even more so once stable
specifications are submitted for standardization in standards bodies, at which
point registrations and changes of status to registrations will be the vast
majority of changes accepted. 

At all three stages in their lifecycle, however, the process is relatively
lightweight and based on pull request review (if accepted to a standardization
body, horizontal review may be solicited over email lists or communications
channels between opening an issue and closing the pull request). All decisions
are eventually made by the [Specs
Stewards](https://github.com/orgs/ipfs/teams/specs-stewards/members), which
correspond to the IETF concept of "Registrars" triaging and guiding issues
through the process, on the basis of recommendations from the format's
[captains](./README.md#project-directory), which correspond to Experts in the
IETF/IANA taxonomy defined in [RFC8126][].

Additions and updates to the registries are more involved. The reason for that
is that registration consumes subtractable resources (eg. prefix codes in a
finite namespace), and while workarounds can always be used to extend a
namespace, we prefer to leave this complexity out of specifications bearing
weight in production deployments, much less ones undergoing formal
standardization. For this, we use a separate template, which includes contact
information for a [Change Controller][] that should be as future-proofed as
possible (multiple entries are fine for this purpose as fallbacks).

Additionally, if we consider the long-term durability of content that relies on
multiformats, it is desirable to avoid an excessive proliferation of options as
that makes archiving them harder if you wish to guarantee long-term decodability
(where by long-term we mean centuries).

## Code of Conduct and Ways to Contribute

Please be aware that all interactions related to multiformats are subject to the
IPFS [Code of Conduct][]; some of this work may move to standards bodies in the
future and be bound as well by the relevant codes of conduct there.

If you're interested in proposing a new format (in addition to multihash,
multistream, and so on), [open an
issue](https://github.com/multiformats/multiformats/issues/new) in this
repository, explaining the name of the format, what it is for, and why you think
it should become one ~~of~~ the multiformats. Pointing to any existing
implementations would also be great, if there are any. Here, taking a glance at
the Registry  Governance sections of the [contributing
document](contributing.md) may help you contextualize the limits of sharing a
registration namespace with all the other formats, each of which slowly grows
over time.

If you want to implement a multiformat in a new language, open an issue in the
main repository for the relevant multiformat: for instance, if you want to write
`rust-multicodec`, then open an issue in the multiformats/multicodec repository.
This will allow others to know that you're working on it, and potentially join
in the effort.

And if you're just curious or bring experience to the table that might offer new
insights, Feel free to [review issues and open new
ones](https://github.com/multiformats/multiformats/issues).  Horizontal review
and outside perspectives are just as welcome as code contributions and hard
research.

## The Process

This process is intended to organize productive and friendly discussions around
the evolution and maintenance of multiformats, with an eye towards high
reliability including over long periods of time for registrations that proceed
to "stable" status.

This repository is the clearing house for high-level questions about how the
registries and the protocols they serve fit together, implementations, and
governance. If you are unsure where to start, an issue here is usually best.

### Reporting Issues

If you find bugs, mistakes, inconsistencies in the various Multiformats specs,
or contradictions and incompatibilities between them, please let us know by
filing an issue. No issue is too small.

Multiformats are foundational, which in turn makes security issues with
multiformats specs and implementations particularly important. If you find a
vulnerability that may affect live deployments – for example, expose a remote
execution exploit – please disclose it responsibly and send your report
privately to [security@ipfs.io](mailto:security@ipfs.io), please **DO NOT** file
a public issue.

We have issue templates for the following types of issue:
- request clarity on (or report possible bug in) documentation (here and per-project)
- propose a new multi- project (here)
- volunteer to translate docs or install instructions (per-project)
- bug report (per-project and per-installation)
- registration: `reserved` (per-project)
- registration: `draft` (per-project)
- registration: update `reserved` or `draft` to `final` (per-project)

### Multiformats Protocol Specifications

The process to make changes to multiformats specifications is to file an issue or
pull request and discuss the change accordingly.

When considering proposals for new protocols or major changes to an existing
one, we are looking for:

- A description of the problem this design proposal solves.
- Discussion of the tradeoffs involved.
- Review of other existing solutions.
- Links to relevant literature (RFCs, papers, etc.).
- Discussion of the proposed solution.

Please note that protocol design is hard, and meticulous, long-term work. You
may need to review existing literature and think through generalized use cases.
You need to be prepared to discuss corner cases in potentially frustrating
detail.

### Multiformats Protocol Refinements

Even though protocol specifications harden over time and become "stable", and
may even move to standards organizations, they are never permanent and never
completed. Improvements, errata, implementation reports, and various forms of
guidance can be collected here in between major versions even for more rigidly
versioned publication processes.

### Multiformats Registries

The primary function of multiformats is to support multiple value encodings
registered in an organized and interoperable way. In turn, this requires the
ability to register new encodings for each multiformat type. Encodings are
indicated using some form of flag (e.g. a prefix) and such the registries of
these flags can become exhausted (e.g. smaller corners of the group, like the
single-byte range), congested (if commonly-used encodings require abnormally
long flags), or "squatted" (i.e. reserved too early without proven adoption and
utility).

Essentially, registrations and re-registrations proceed through the following steps-- if all requirements are already met at time of initial registration, these can be collapsed.  Essentially, they are:
- "Reserved" entries can be inserted directly by protocol designers or Stewards to prevent interoperability or functional pitfalls
- "Reserved" entries can also be submitted on an [Experimental Use](https://www.rfc-editor.org/rfc/rfc8126.html#section-4.2) basis. Registrations at this level are essentially courtesies to other registrants and invitations to collaborate or provide feedback. These can be deprecated in favor of competing "Draft" or "Final" proposals for the same unique entry code.
- "Draft" entries can be submitted by mature projects that can reasonably document the requirements below and pass [Expert Review](https://www.rfc-editor.org/rfc/rfc8126.html#section-4.5)
- "Final" entries must document the complete requirements below and pass review on a [Specification Required](https://www.rfc-editor.org/rfc/rfc8126.html#section-4.6) basis.

### Multiformats Registrations

In order to ensure that our registries are as extensible as they need to be but
do not suffer from over-use, we have a set of criteria which are used to ensure
that only encodings that broadly benefit the community are registered.

In order to be accepted for registration as draft, an encoding MUST:

* Volunteer at least one person who will be available to answer questions and
  address issues through the registration period and for some time after the
  encoding is accepted. 
* Additionally, contact information for a change controller (not necessarily the
  same person as above, ideally an organization assuming long-term
  responsibility for systems using the multiformat) in case of updates to or
  disputes around an entry.
* Provide evidence that the encoding is supported in at least two production
  implementations.
* Describe a convincing use case for the deployment of this specific encoding.
* Produce a specification indicating how to process it at a level of detail that
  makes implementations testable. (References to an external specification is
  acceptable if it comes from a body with sufficient durability guarantees.)

And, for that registration to proceed to `final` designation, it must also
* Provide a comprehensive test suite sufficient to support independent
  interoperable implementations, or at least be comprised entirely of
  technologies that are already mature and have test suites.
* Produce a specification indicating how to process it at a level of detail that
  makes multiple independent implementations demonstrably interoperable.

If an encoding seems plausible but does not yet fulfil all requirements, it can
be registered with a `draft` status.  In exceptional cases, consensus of the
Stewards and Experts can excuse one of the above requirements. 

Encodings with a `draft` status should be revisited by [Specs
Stewards](https://github.com/orgs/ipfs/teams/specs-stewards/members) regularly.
If after some reasonable amount of time (enough to make progress, but ideally no
more than a year) a `draft` encoding has not resolved issues with its
registration, it will become `deprecated`. After an encoding is `deprecated` for
some time at the discretion of the Stewards and Experts, decided to be
sufficient for its use to be reasonably considered eliminated or historical, its
code becomes available for reuse (but remains listed under new entries as
`deprecated`). 

Accepted encodings that meet all of the requirements above (confirmed by the
Experts) will bee granted a status of `permanent` within a reasonable amount of
time by the Stewards.

## Acknowledgements

This document is an iteration of the [original contributing
document](https://github.com/multiformats/multiformats/commit/ac7a9569fe15c548151f1e9350b19600e308dd97#diff-b335630551682c19a781afebcf4d07bf978fb1f8ac04c6bf87428ed5106870f5).