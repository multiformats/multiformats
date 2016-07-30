# multiformats

> "Never going to change" considered harmful.
> -- @lgierth

## Multiformats

This is the home repository for the multiformats effort, which produces these protocols:

- [multihash](//github.com/multiformats/multihash)
- [multiaddr](//github.com/multiformats/multiaddr)
- [multicodec](//github.com/multiformats/multicodec)
- [multistream](//github.com/multiformats/multistream)
- multibase (WIP)
- multigram (WIP)
- multikey (WIP)

## Stub Explanation

While we write out a proper readme, here's some quick explanation slides:

![](img/multiformats.001.jpg)
![](img/multiformats.002.jpg)

---

### Example: Multihash

![](img/multihash.001.jpg)

#### Consider these 4 different hashes of same input

![](img/multihash.002.jpg)

#### Same length: 256 bits

![](img/multihash.003.jpg)

#### Different hash functions

![](img/multihash.004.jpg)

#### Idea: self-describe the values to distinguish

![](img/multihash.005.jpg)

#### Multihash: fn code + length prefix

![](img/multihash.006.jpg)

#### Multihash: a pretty good multiformat

![](img/multihash.007.jpg)

#### Multihash: has a bunch of implementations already

![](img/multihash.008.jpg)

---

### Example: Multiaddr

Basic example of multiaddr

![](img/multiaddr.001.jpg)
