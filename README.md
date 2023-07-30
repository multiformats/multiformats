# multiformats

[![](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square)](http://ipn.io)
[![](https://img.shields.io/badge/project-multiformats-blue.svg?style=flat-square)](https://github.com/multiformats/multiformats)
[![](https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square)](https://webchat.freenode.net/?channels=%23ipfs)
[![](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

> The main repository for discussing multiformats

Currently, we have the following formats. More formats are being discussed and worked on.

| Repo | Captain | Status | IETF |
|------|---------|--------|------|
| [multiaddr](https://github.com/multiformats/multiaddr)| @lgierth | stable | [WIP](https://github.com/multiformats/multiaddr/tree/doc/internet-draft) |
| [multibase](https://github.com/multiformats/multibase) | @jbenet | stable | [W3C DVCG](https://github.com/w3c-dvcg/multibase) |
| [multicodec](https://github.com/multiformats/multicodec)| @jbenet | stable | TODO |
| [multihash](https://github.com/multiformats/multihash)| @jbenet | stable | [W3C DVCG](https://github.com/w3c-dvcg/multihash) |
| [multistream](https://github.com/multiformats/multistream)| @diasdavid | stable | TODO |
| [multigram](https://github.com/ipfs/specs/pull/123) | | WIP | TODO |
| [multikey](https://github.com/ipfs/specs/issues/58) | | WIP | TODO |

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
- [multigram](https://github.com/multiformats/multigram): protocol negotiation and multiplexing over datagrams
- [multihash](https://github.com/multiformats/multihash): cryptographic hashes
- [multikey](https://github.com/ipfs/specs/issues/58): cryptographic keys and artifacts
- [multistream](https://github.com/multiformats/multistream): stream wire protocols
- [multistream-select](https://github.com/multiformats/multistream-select): Friendly protocol multiplexing.

The self-describing aspects of the protocols have a few stipulations:

- they must be in the value (not passed in out of band, in function calls, implicit choices, or documentation);
- they must be compact and have a binary-packed representation (as opposed to a sparser encoding) or they will hinder performance;
- they must have a human readable representation.

Several of the multiformats are stable, and we're working on the others. We are trying to prioritize their usage as soon as possible. What they offer -- protocol interoperability and future-proofing --  would have real-world consequences.

Towards that end, we are encouraging implementations of these protocols; if you know of any, please link them here (or add them to the organization!).

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
| [cs-multiaddress](https://github.com/multiformats/cs-multiaddress) | @tabrath |
| [go-multiaddr](https://github.com/multiformats/go-multiaddr)| @whyrusleeping |
| [go-multiaddr-net](https://github.com/multiformats/go-multiaddr-net)| @whyrusleeping |
| [go-multiaddr-dns](https://github.com/multiformats/go-multiaddr-dns)| @lgierth |
| [java-multiaddr](https://github.com/multiformats/java-multiaddr)| @ianopolous |
| [js-multiaddr](https://github.com/multiformats/js-multiaddr)| @diasdavid |
| [rust-multiaddr](https://github.com/multiformats/rust-multiaddr)| @dignifiedquire |
| [SwiftMultiaddr](https://github.com/multiformats/SwiftMultiaddr)| @NeoTeo |
| [py-multiaddr](https://github.com/multiformats/py-multiaddr) |  |
| [multiformat](https://github.com/erwin-kok/multiformat) | @erwin-kok |

#### Multihash Implementations

| Repo | Captain | Note |
|------|---------|------|
| [c-multihash](https://github.com/multiformats/c-multihash) | @Kubuxu | _Only parsing and encoding, and not hashing._ |
| [c-multihashing](https://github.com/multiformats/c-multihashing) | @Kubuxu | |
| [cs-multihash](https://github.com/multiformats/cs-multihash) | @tabrath | |
| [clj-multihash](https://github.com/multiformats/clj-multihash) | @greglook | |
| [ex_multihash](https://github.com/multiformats/ex_multihash)| @zabirauf | |
| [go-multihash](https://github.com/multiformats/go-multihash)| @Kubuxu | |
| [haskell-multihash](https://github.com/multiformats/haskell-multihash) | @LukeHoersten | |
| [java-multihash](https://github.com/multiformats/java-multihash) | @ianopolous | |
| [hash-overlay (Java 9)](https://github.com/comodal/hash-overlay) | @jamespedwards42 | |
| [js-multihash](https://github.com/multiformats/js-multihash)| @diasdavid | |
| [js-multihashing-async](https://github.com/multiformats/js-multihashing-async) | @dignifiedquire | |
| [js-multihashing](https://github.com/multiformats/js-multihashing)| @diasdavid | |
| [MultiHash.Net (fork)](https://github.com/multiformats/MultiHash.Net) | @MCGPPeters | |
| [php-multihash](https://github.com/multiformats/php-multihash)| @Fil | |
| [ruby-multihash](https://github.com/multiformats/ruby-multihash)| @kyledrake | |
| [rust-multihash](https://github.com/multiformats/rust-multihash)| @dignifiedquire | |
| [scala-multihash](https://github.com/multiformats/scala-multihash)| @parkan | |
| [SwiftMultihash](https://github.com/multiformats/SwiftMultihash)| @NeoTeo | |
| [multiformat](https://github.com/erwin-kok/multiformat) | @erwin-kok |

#### Multicodec Implementations

| Repo | Captain | Note |
|------|---------|------|
| [clj-multicodec](https://github.com/multiformats/clj-multicodec) | @greglook | |
| [go-multicodec-packed](https://github.com/multiformats/go-multicodec-packed) | @whyrusleeping | |
| [go-multicodec](https://github.com/multiformats/go-multicodec)| @jbenet | |
| [js-multicodec](https://github.com/multiformats/js-multicodec) | @diasdavid | |
| [multiformat](https://github.com/erwin-kok/multiformat) | @erwin-kok |

#### Other Implementations

| Repo | Captain | Note |
|------|---------|------|
| [cs-multibase](https://github.com/multiformats/cs-multibase) | @tabrath | |
| [go-multibase](https://github.com/multiformats/go-multibase) | @whyrusleeping | |
| [go-multigram](https://github.com/multiformats/go-multigram)| @lgierth | |
| [go-multistream](https://github.com/multiformats/go-multistream)| @whyrusleeping | |
| [java-multibase](https://github.com/multiformats/java-multibase) | @ianopolous | |
| [js-multibase](https://github.com/multiformats/js-multibase) | @diasdavid | |
| [js-multistream-select](https://github.com/multiformats/js-multistream-select) | @diasdavid | |
| [multiformat](https://github.com/erwin-kok/multiformat) | @erwin-kok |

### Other Repositories

| Repo | Captain | Note |
|------|---------|------|
| [clj-varint](https://github.com/multiformats/clj-varint) | @ekroon | |
| [ma-pipe](https://github.com/multiformats/ma-pipe) | @jbenet | |
| [multiformats](https://github.com/multiformats/multiformats)| @RichardLitt | This repository |
| [specs](https://github.com/multiformats/specs)| @nicola | Specification work regarding multihash, multiaddr, and others. _WIP._ |
| [unsigned-varint](https://github.com/multiformats/unsigned-varint) | @jbenet | unsigned varint in use in multiformat specs. _WIP._ |
| [clj-varint](https://github.com/multiformats/clj-varint) | @ekroon | Simple wrapper around Bazel VarInt code.
| [website](https://github.com/multiformats/website) | @victorbjelkholm | The multiformats website |

## Maintainers

- [@daviddias](https://github.com/daviddias)

## Contribute

Please contribute! [Dive into the issues](https://github.com/multiformats/multiformats/issues)!

Check out our [contributing document](contributing.md) for more information on how we work, and about contributing in general. Please be aware that all interactions related to multiformats are subject to the IPFS [Code of Conduct](https://github.com/ipfs/community/blob/master/code-of-conduct.md).

If you're interested in proposing a new format (in addition to multihash, multistream, and so on), [open an issue](https://github.com/multiformats/multiformats/issues/new) in this repository, explaining the name of the format, what it is for, and why you think it should become one of the multiformats. Pointing to any existing implementations would also be great, if there are any. If you want to implement a multiformat in a new language, open an issue in the main repository for the relevant multiformat: for instance, if you want to write rust-multicodec, open an issue in the multiformats/multicodec repository. This will allow others to know that you're working on it, and potentially join in the effort.

Small note: If editing the README, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

This repository is only for documents. All of these are licensed under the [CC-BY-SA 3.0](https://ipfs.io/ipfs/QmVreNvKsQmQZ83T86cWSjPu2vR3yZHGPm5jnxFuunEB9u) license © 2016 Protocol Labs Inc. Any code is under a [MIT](LICENSE) © 2016 Protocol Labs Inc.

