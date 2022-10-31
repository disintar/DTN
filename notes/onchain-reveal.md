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

### Collection side

NFT collection is extended by new GET method `get_reveal_data` that allow you to get information of remaining NFT content that will be revealed.

dApps can parse such info and display to user what can be inside the mystery box. 

Also dApps can detect can we reveal NFT or not right now (if there are 0 items left in collection - we can't reveal NFT)

Also collection is extended by new internal messages such: `nft_reveal_nft_request`, `nft_reveal_success_collection_response` that allows to interact with NFT which is in reveal process.
And `collection_add_reveal_batch` which allow to extend current remaining list of content that will be raffle to NFTs

### NFT side

NFT item is extended by new GET method `get_reveal_mode` which means the current reveal status of this item.
Based on this, the dApp can show the possibility or progress of reveal 

Also item is extended by new internal messages such: `nft_reveal_user_request` that allow user to ask NFT for reveal

# Specification

### TLB

```
nft_reveal_user_request#5fcc3d1a query_id:uint64 = InternalMsgBody;
nft_reveal_nft_request#5fcc3d1b query_id:uint64 index:uint256 = InternalMsgBody;
nft_reveal_success_collection_response#5fcc3d1c query_id:uint64 success:Bool new_content:(Maybe (Either Cell ^Cell))  = InternalMsgBody;

collection_add_reveal_batch#5fcc3d1d query_id:uint64 new_content_batch:Hashmap 64 Either Cell ^Cell = InternalMsgBody;
```

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