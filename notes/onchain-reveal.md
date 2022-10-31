# Summary

Extending the interface
of [non-fungible tokens](https://github.com/ton-blockchain/TEPs/blob/master/text/0062-nft-standard.md) with onchain
reveal mechanics

[Example of implementation with tests](https://github.com/disintar/nft-reveal)

# Motivation

Suppose you are a collection that wants to fairly reveal closed NFTs (already distributed) boxes among its users. Many
collections implement this through externel messages with NFT content updates (changing the content with the backend).
This does not give transparency to the process, you can trick users into putting up rare NFTs yourself, and users will
feel indignant about the lack of honesty.

The standard describes implementation examples as well as standard interfaces for a transparent NFT content update
process.

The standard itself does not guarantee the integrity of the NFT distribution, but only gives an example of it using
standard interfaces. The final implementation always depends on the specific product.

Examples described in this standard, can be improved to mathematically generate NFT without using external messages to
populate the pool for reveal.

A single interface will help developers of games, marketplaces and other dApps to display such mechanics in their
products.

# Guide

TBD.

# Specification

TBD.

# Drawbacks

TBD.

# Rationale and alternatives

TBD.

# Prior art

TBD.

# Unresolved questions

TBD.

# Future possibilities

TBD.