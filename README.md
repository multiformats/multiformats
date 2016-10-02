# multiformats

[![](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square)](http://ipn.io)
[![](https://img.shields.io/badge/project-multiformats-blue.svg?style=flat-square)](http://github.com/multiformats/multiformats)
[![](https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square)](http://webchat.freenode.net/?channels=%23ipfs)

> The main repository for discussing multiformats

Currently, we have the following multiformat protocols:

| Repo | Captain | Status |
|------|---------|--------|
| [multiaddr](https://github.com/multiformats/multiaddr)| @jbenet | stable |
| [multicodec](https://github.com/multiformats/multicodec)| @jbenet | stable |
| [multihash](https://github.com/multiformats/multihash)| @jbenet | stable |
| [multistream](https://github.com/multiformats/multistream)| @diasdavid | WIP |
| [multibase](https://github.com/multiformats/multibase) | @jbenet | WIP |
| [multigram](https://github.com/ipfs/specs/pull/123) | | WIP |
| [multikey](https://github.com/ipfs/specs/issues/58) | | WIP |

See the project directory, below, for implementations and other related repositories.

![](img/multiformats.001.jpg)
![](img/multiformats.002.jpg)

## Table of Contents

- [Background](#background)
  - [An Example: Multihash](#an-example-multihash)
  - [A note on the word Multiformats](#a-note-on-the-word-multiformats)
- [Project Directory](#project-directory)
  - [Protocols](#protocols)
  - [Protocols in Progress](#protocols-in-progress)
  - [Implementations](#implementations)
    - [Go Implementations](#go-implementations)
    - [JavaScript Implementations](#javascript-implementations)
    - [Other Implementations](#other-implementations)
  - [Other Repositories](#other-repositories)
- [Contribute](#contribute)
- [License](#license)

## Background

Every choice in computing has a tradeoff. This includes formats, algorithms, encodings, and so on. And even with a great deal of planning, decisions may lead to breaking changes down the road, or to solutions which are no longer optimal. Allowing systems to evolve and grow is important.

Multiformats is a collection of protocols which aim to future-proof systems, today. They do this mainly by allowing data to be self-describable. This allows interoperability, protocol agility, and helps us avoid lock in. Currently, our protocols (both works in progress and implemented) cover the following areas:

- [multiaddr](https://github.com/multiformats/multiaddr): network addresses
- [multibase](https://github.com/multiformats/multibase): base encodings
- [multicodec](https://github.com/multiformats/multicodec): serialization codes
- [multihash](https://github.com/multiformats/multihash): cryptographic hashes
- [multikey](https://github.com/ipfs/specs/issues/58): cryptographic keys and artifacts
- [multistream](https://github.com/multiformats/multistream): stream wire protocols

The self-describing aspects of the protocols have a few stipulations:

- they must be in the value (not passed in out of band, in function calls, implicit choices, or documentation);
- they must be compact and have a binary-packed representation (as opposed to a sparser encoding) or they will hinder performance;
- they must have a human readable representation.

Several of the multiformats are stable, and we're working on the others. We are trying to prioritize their usage as soon as possible. What they offer -- protocol interoperability and future-proofing --  would have real-world consequences.

Towards that end, we are encouraging implementations of these protocols; if you know of any, please link them here (or add them to the organization!).

### An Example: Multihash

Multihash is a simple, easy to understand multiformat that shows how the multiformats can be used. Let's take a look at some standard hash functions:

TODO @RichardLitt fill out.

### A note on the word Multiformats

Multiformats is the name for the organization, but it can also be used to refer to protocols; for instance, in the sentence "Use one of the multiformats". Formats is interchangeable with protocols, here. We try to capitalize Multiformats when it refers to the organization, on GitHub.

## Project Directory

Below, a list of all of the projects in the Multiformats organization is listed.

**Captains** are the active leads for each project. Their responsibilities are to make sure that issues and pull requests are attended to in a timely manner, and general upkeep. If you have questions about a repository, or need feedback, please contact them as appropriate.

### Implementations

As well as specifications, we also have some implementations in the organization

#### Multiaddr Implementations

| Repo | Captain |
|------|-------------------|
| [go-multiaddr](https://github.com/multiformats/go-multiaddr)| @whyrusleeping |
| [go-multiaddr-net](https://github.com/multiformats/go-multiaddr-net)| @whyrusleeping |
| [js-multiaddr](https://github.com/multiformats/js-multiaddr)| @diasdavid |
| [rust-multiaddr](https://github.com/multiformats/rust-multiaddr)| @dignifiedquire | |
| [SwiftMultiaddr](https://github.com/multiformats/SwiftMultiaddr)| @NeoTeo | |

#### Multihash Implementations

| Repo | Captain |
|------|-------------------|
| [c-multihash](https://github.com/multiformats/c-multihash) | @Kubuxu | _Only parsing and encoding, and not hashing._ |
| [ex_multihash](https://github.com/multiformats/ex_multihash)| @zabirauf | |
| [go-multihash](https://github.com/multiformats/go-multihash)| @Kubuxu |
| [js-multihash](https://github.com/multiformats/js-multihash)| @diasdavid |
| [js-multihashing](https://github.com/multiformats/js-multihashing)| @diasdavid |
| [php-multihash](https://github.com/multiformats/php-multihash)| @Fil | |
| [rust-multihash](https://github.com/multiformats/rust-multihash)| @dignifiedquire | |
| [scala-multihash](https://github.com/multiformats/scala-multihash)| @parkan | |
| [SwiftMultihash](https://github.com/multiformats/SwiftMultihash)| @NeoTeo | |
| [MultiHash.Net (fork)](https://github.com/multiformats/MultiHash.Net)| @MCGPPeters | |

#### Other Implementations

| Repo | Captain | Note |
|------|---------|------|
| [go-multicodec](https://github.com/multiformats/go-multicodec)| @jbenet |
| [go-multigram](https://github.com/multiformats/go-multigram)| @lgierth |
| [go-multistream](https://github.com/multiformats/go-multistream)| @whyrusleeping |
| [js-multistream](https://github.com/multiformats/js-multistream-select)| @diasdavid |

### Other Repositories

| Repo | Captain | Note |
|------|---------|------|
| [multiformats](https://github.com/multiformats/multiformats)| @RichardLitt | This repository |
| [specs](https://github.com/multiformats/specs)| @nicola | Specification work regarding multihash, multiaddr, and others. _WIP._ |
| [unsigned-varint](https://github.com/multiformats/unsigned-varint) | @jbenet | unsigned varint in use in multiformat specs. _WIP._ |

## Contribute

Please contribute! [Dive into the issues](https://github.com/multiformats/multiformats/issues)!

Check out our [contributing document](contributing.md) for more information on how we work, and about contributing in general. Please be aware that all interactions related to multiformats are subject to the IPFS [Code of Conduct](https://github.com/ipfs/community/blob/master/code-of-conduct.md).

Small note: If editing the README, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

This repository is mainly documents. All of these are licensed under the [CC-BY-SA 3.0](https://ipfs.io/ipfs/QmVreNvKsQmQZ83T86cWSjPu2vR3yZHGPm5jnxFuunEB9u) license, copyright Protocol Labs Inc.
