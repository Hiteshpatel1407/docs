---
title: "How to get SPL token price"
slug: "../how-to-get-spl-token-price"
description: "This tutorial will guide you through the process of using the Moralis API to get the price of a SPL token."
sidebar_label: "Get SPL token price"
---

## Step 1: Setup Moralis

Read the article [Setting Up Moralis: Getting Started](/web3-data-api/solana/get-your-api-key) and make sure to finish all the steps. Only after that you can go ahead to complete this guide.

## Step 2: Get SPL token price

In order to get SPL token price, Moralis provides you the [getTokenPrice](/web3-data-api/solana/reference/get-sol-token-price) API endpoint to do so.

Here you'll need two parameters: `address` and `network`.

Once you have obtained both the `address` and `network`, you can copy the following code:

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs groupId="programming-language">
  <TabItem value="javascript" label="index.js (JavaScript)" default>

```javascript index.js
const Moralis = require("moralis").default;
const { SolNetwork } = require("@moralisweb3/common-sol-utils");

const runApp = async () => {
  await Moralis.start({
    apiKey: "YOUR_API_KEY",
    // ...and any other configuration
  });

  const address = "4k3Dyjzvzp8eMZWUXbBCjEvwSkkk59S5iCNLY3QrkX6R";

  const network = SolNetwork.MAINNET;

  const response = await Moralis.SolApi.token.getTokenPrice({
    address,
    network,
  });

  console.log(response.toJSON());
};

runApp();
```

</TabItem>
<TabItem value="typescript" label="index.ts (TypeScript)">

```typescript index.ts
import Moralis from "moralis";
import { SolNetwork } from "@moralisweb3/common-sol-utils";

const runApp = async () => {
  await Moralis.start({
    apiKey: "YOUR_API_KEY",
    // ...and any other configuration
  });

  const address = "4k3Dyjzvzp8eMZWUXbBCjEvwSkkk59S5iCNLY3QrkX6R";

  const network = SolNetwork.MAINNET;

  const response = await Moralis.SolApi.token.getTokenPrice({
    address,
    network,
  });

  console.log(response.toJSON());
};

runApp();
```

</TabItem>
<TabItem value="python" label="index.py (Python)">

```python index.py
from moralis import sol_api

api_key = "YOUR_API_KEY"
params = {
    "address": "4k3Dyjzvzp8eMZWUXbBCjEvwSkkk59S5iCNLY3QrkX6R",
    "network": "mainnet",
}

result = sol_api.token.get_token_price(
    api_key=api_key,
    params=params,
)

print(result)
```

</TabItem>
</Tabs>

## Step 3: Run the script

import RunTheScript from '/docs/partials/\_run-the-script.mdx';

<RunTheScript />

In your terminal, you should see the following JSON response:

```json
{
  "usdPrice": 0.2435,
  "exchangeName": "Raydium",
  "exchangeAddress": "675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8",
  "nativePrice": {
    "value": "20995847",
    "symbol": "WSOL",
    "name": "Wrapped Solana",
    "decimals": 9
  }
}
```

Congratulations 🥳 You just got the price of a SPL token with just a few lines of code using the Moralis Solana API!

## API Reference

If you want to know more details on the endpoint and optional parameters, check out:

- [getTokenPrice](/web3-data-api/solana/reference/get-sol-token-price)

## YouTube Tutorial

https://www.youtube.com/watch?v=re7nQsbP-po

## Support

If you face any trouble following the tutorial, feel free to reach out to our community engineers in our [Discord](https://moralis.io/discord) or [Forum](https://forum.moralis.io) to get 24/7 developer support.
