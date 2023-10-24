# multiformats

[![](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square)](http://ipn.io)
[![](https://img.shields.io/badge/project-multiformats-blue.svg?style=flat-square)](https://github.com/multiformats/multiformats)
[![](https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square)](https://webchat.freenode.net/?channels=%23ipfs)
[![](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

> The main repository for discussing multiformats

Multiformats is a set of self-describing protocol values. 
These values are foundational in that they are low-level building blocks for both data and network layers of the composable protocols making up IPFS, IPLD, libp2p, and many other decentralized data systems. 
This repository's issues and pull requests are currently the primary venue for the coordination between the various registries making up the group, each of which is separately being hardened as specifications and public, formal registries over time.  
See [contributing.md][./contributing.md] for more details on governance and process.

## Current Registries

Currently, we have the following formats, each of which corresponds to a specification and a registry. 
More formats are being discussed and may be added over time, but the following are the mature ones to date:

| Repo | Maintainer | Specification |
|------|---------|--------|------|
| [multiaddr](https://github.com/multiformats/multiaddr)| stable | [WIP](https://github.com/multiformats/multiaddr/tree/doc/internet-draft) |
| [multibase](https://github.com/multiformats/multibase) | stable | [W3C CCG](https://github.com/w3c-ccg/multibase) |
| [multicodec](https://github.com/multiformats/multicodec)| stable | TBD |
| [multihash](https://github.com/multiformats/multihash)| stable | [W3C CCG](https://github.com/w3c-ccg/multihash) |


See the project directory, below, for implementations and other related repositories.

![](img/multiformats.001.jpg)
![](img/multiformats.002.jpg)

## Table of Contents

- [Current Registries](#current-registries)
- [Table of Contents](#table-of-contents)
- [Background](#background)
  - [A note on the word Multiformats](#a-note-on-the-word-multiformats)
- [Project Directory](#project-directory)
  - [Implementations](#implementations)
- [Maintainers](#maintainers)
- [Contribute](#contribute)
- [License](#license)

## Background

Every choice in computing has a tradeoff. 
This includes formats, algorithms, encodings, and so on. 
And even with a great deal of planning, decisions may lead to breaking changes down the road, or to solutions which are no longer optimal. 
Allowing systems to evolve and grow is important.

Multiformats is a collection of protocols which aim to future-proof systems, today. 
They do this mainly by allowing data to be self-describable. 
This allows interoperability, protocol agility, and helps us avoid various forms of lock-in.
Currently, these interlocking protocols (both works in progress and implemented) cover the following areas:

- [multiaddr](https://github.com/multiformats/multiaddr): network addresses
- [multibase](https://github.com/multiformats/multibase): base encodings
- [multicodec](https://github.com/multiformats/multicodec): serialization codes
- [multihash](https://github.com/multiformats/multihash): cryptographic hashes
- [multikey](https://github.com/ipfs/specs/issues/58): cryptographic keys and artifacts

Several of the multiformats are stable, and work on the others is ongoing.
Implementers and refiners of the drafts of any one of these registries or their tooling are welcome to [contribute](./contributing.md), without needing to understand deeply or track progress on the others. 
Across these otherwise different use-cases and mechanisms, the self-describing aspects of the protocols have a few design goals in common:

- the "prefixes" use to self-describe a value must be inline with the value (not passed out-of-band, in function calls, implicit choices, or documentation);
- they must be compact and have a binary-packed representation (as opposed to a sparser encoding) or they will hinder performance;
- they must have a human-readable representation.

### A note on the word Multiformats

`Multiformats` is the name for the community (and the "organization" in GitHub's access control model), but `multiformats` can also be used to refer to protocols; for instance, in the sentence "Use one of the multiformats". 
Formats is interchangeable with protocols, here, as each format is designed in tandem with one or more protocols which handle those self-describing values centrally. 
We try to capitalize Multiformats when it refers to the organization.

## Project Directory

Below, a list of all of the projects in the Multiformats organization is listed.

**Maintainers** are the active leads for each project, even if the specification is still under construction. 
Their responsibilities are to make sure that issues and pull requests are attended to in a timely manner, and general upkeep. 
If you have questions about a repository, or need feedback, please contact them as appropriate. 
If any of the specifications defining these formats are formalized in a standards body, these maintainers may continue on as Registrars of the table of entries which can keep growing after stabilizing the syntax and tooling interfaces.

### Implementations

There are no official or maintained implementations of the entire set of multiformats specifications and registries.
The readme file of each multiformat specification repository includes a list of known implementations, some of which are hosted in this GitHub organization.

## Maintainers

Maintainers of the each multiformats specification are listed in the appropriate repositories. 
The external standardization of multiformats specifications and registries is currently managed and coordinated by [@bumblefudge](https://github.com/bumblefudge) of [learningProof UG](https://learningproof.xyz).

## Contribute

Check out our [contributing document](contributing.md) for more information on how we work, and about contributing in general.

## License

This repository is only for documents. 
All of these are licensed under the [CC-BY-SA 3.0](https://ipfs.io/ipfs/QmVreNvKsQmQZ83T86cWSjPu2vR3yZHGPm5jnxFuunEB9u) license © 2016 Protocol Labs Inc. Any code is under a [MIT](LICENSE) © 2016 Protocol Labs Inc.

[Code of Conduct]: https://github.com/ipfs/community/blob/master/code-of-conduct.md