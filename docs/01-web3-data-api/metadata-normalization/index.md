---
sidebar_position: 2
title: "Metadata Normalization"
slug: "metadata-normalization"
description: "When working with NFT Metadata, you have the option to receive either a normalized or non-normalized metadata from our NFT APIs."
---

Through our [NFT APIs](/web3-data-api/evm/nft-api), you have the option to receive either a [normalized or non-normalized NFT metadata](https://docs.moralis.io/reference/normalized-vs-non-normalized-metadata).

To use this feature, simply set `normalizedMetadata` parameter to `true`.

```javascript
import Moralis from "moralis";
import { EvmChain } from "@moralisweb3/evm-utils";

const chain = EvmChain.ETHEREUM;

const address = "0xb47e3cd837dDF8e4c57F05d70Ab865de6e193BBB";

const tokenId = "1";

await Moralis.start({
  apiKey: "<YOUR_API_KEY>",
  // ...and any other configuration
});

const response = await Moralis.EvmApi.nft.getNFTMetadata({
  address,
  chain,
  tokenId,
  normalizedMetadata: true,
});

console.log(response.toJSON());
```

This feature is available in the following NFT APIs:

- [Get NFTs by wallet](https://docs.moralis.io/reference/getwalletnfts)
- [Get NFTs by contract](https://docs.moralis.io/reference/getcontractnfts)
- [Get NFT owners by contract](https://docs.moralis.io/reference/getnftowners)
- [Get NFT metadata](https://docs.moralis.io/reference/getnftmetadata)
- [Get owners by token ID](https://docs.moralis.io/reference/getnfttokenidowners)