# Multipath

A multipath is a path format defined abstractly as a recursive tuple of `(CODEC . REST)` where `CODEC` is a registered multicodec and `REST` is interpreted relative to `NAME`.

A multipath is usually represented either in it's "path" form:

```
/CODEC-NAME/REST
```

Or as it's "compact" form (where the codec's uvarint encoded code is concatenated with the codec-specific encoding of rest):

```
<CODEC-CODE>REST
```

## Recursive

We say that multipaths are recursive because they are designed to be composed. For example, given:

```
/ip4/127.0.0.1/tcp/1234
```

The specification for the `ip4` multipath is:

```
("ip4" ip &rest sub-path)
```

And the specification for the `tcp` multipath is:

```
("tcp" port &rest sub-path)
```

## Representation

There are two common representations for multipaths:

1. The "path" form: `/CODEC-NAME/REST...`
2. The "compact" form: `<CODEC-CODE>REST...`.

### Path Representation

The path form of a multipath is `/CODEC-NAME/REST...`, where `REST...` often
contains additional multipaths.

This form usually chosen when representing multipaths in text and user interfaces.

### Compact Representation

The compact form of a multipath `/CODEC-NAME/REST...`

```
<CODEC-CODE><encode(REST)>>
```

That is, we:

1. Encode `REST` with codec-specific encoding.
2. Prepend `CODEC`'s multicodec, encoded as a uvarint.

For example, the compact form of:

```
/ip4/127.0.0.1/tcp/1234
```

is

```
<ip4-multicodec>0x7f000001<tcp-multicodec>0xd204
```

Where `0x7f0000001` is the `127.0.0.1` encoded as a big-endien 32 bit integer and `0xd204` is 1234 encoded as a big endien 16 bit integer.

The benefit of the compact representation is, as implied by the name, compactness. When represented in the compact form, `/ip4/127.0.0.1/tcp/1234` is only 8 bytes.

This form is usually chosen when representing multipaths in network messages.

**Compatibility between the compact and path representations:**

The multicodec table has a codec for paths with the code `0x2f` which just so happens to be `/` when encoded in ASCII/UTF-8. This means that all multipaths in the path representation (`/NAME/REST...`) can be correctly stored and interpreted in the compact representation.

### S-expression

NOT IMPLEMENTED

A multipath may also be encoded as an S-expression where additional flexibility is required:

```cl
(ip4 "127.0.0.1"
  (or (tcp 1234 tls) (tcp 9999 noise))
  (p2p "QmPeerID"))
```

Unlike the path representation, an S-expression can express left associativity. In other words, it's possible to group elements to express "and", "or", etc.

TODO: Reserve ASCII `(` as a multicodec?

## Multi*

Multipath aims to combine all IPFS naming standards under one umbrella. Anything starting with a multicodec can be interpreted as a multipath.

### Multiaddr

Multiaddr is a subset of multipath for addressing endpoints. All multiaddrs (both in path form and in binary/compact form) are valid multipaths.

### IPFS Paths

An IPFS path is `/ipfs/CID/REST`. In it's compact form, this would be `<ipfs-ns-multicodec><cid><rest>`.

### CID

CIDs are valid compact multipaths. For example, `bafkreialvecov2dxhnymouzt3ng6f45miwuk2to3ugzef4ftz7azsoi53a` is actually `<cidv1-multicodec><raw-multicodec><sha2-256-multicodec><length><digest>`. As a path, this can be represented as:

```
/cidv1/raw/sha2-256/DIGEST
```

## History

Multipaths were born from the union of multicodec, multiaddrs, paths, and CIDs.
