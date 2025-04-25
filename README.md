# Atomicals Command-line Tool

The command-line tool to fetch, deploy, mint, transfer, and manipulate Atomicals Digital Assets.

Visit the [Atomicals Guidebook](https://atomicals-community.github.io/atomicals-guide/) to get to know about Atomicals!

> Multiple templates are covered for setting up Fungible-tokens, NFT collections, Realm & Sub-realm, and Social-FI!
> Check them out at https://github.com/atomicals/atomicals-js/tree/main/templates.

**Table Of Contents**
<!-- TOC -->
* [Atomicals Command-line Tool](#atomicals-command-line-tool)
    * [Other Atomicals Tools](#other-atomicals-tools)
    * [Install](#install)
    * [Quick Start](#quick-start)
      * [0. Environment File (.env)](#0-environment-file-env)
      * [1. Wallet Setup](#1-wallet-setup)
      * [2. Explore the CLI](#2-explore-the-cli)
      * [Using as a JavaScript/TypeScript SDK](#using-as-a-javascripttypescript-sdk)
    * [For Developers/Contributors](#for-developerscontributors)
    * [Community](#community)
<!-- TOC -->

### Other Atomicals Tools

- Atomicals ElectrumX Indexer Server (https://github.com/atomicals/atomicals-electrumx)

---

### Install

The recommended way to use the CLI is via npm. You do **not** need to clone this repository to use the tool.

To install globally:

```bash
npm install -g atomicals-js
```

This will make the `atomicals` command available globally.

---

### Quick Start

Once installed, follow the steps below to set up your environment, wallet, and run commands.

#### 0. Environment File (.env)

The CLI expects a `.env` file to define your ElectrumX connection and wallet path.

Copy `.env.example` and adjust it to your needs:

```dotenv
ELECTRUMX_PROXY_BASE_URL=https://ep.your-atomicals-electrumx-host/proxy

# Optional wallet configuration
WALLET_PATH=./wallets
WALLET_FILE=wallet.json
# testnet or livenet or regtest
NETWORK=livenet

# Optionnal
CONCURRENCY=4
```

You can use the default settings or point to a custom wallet directory.

#### 1. Wallet Setup

The wallet stores your taproot keypair and address used for minting and receiving change.

To create a new wallet:

```bash
atomicals wallet-init
```

Example output:

```text
Wallet created at wallet.json
phrase: loud please install guilt shoe move decade matrix bleak venue swing whale
Primary address (P2TR): bc1p9lyej8qkpx42ms3rjlue598kxt8kpfyuw3jwuk8jtqvg4y6uqyeqav2y7r
Primary address WIF: L18PiBLxSBUjfAKswMXat7LarR3VA234NDD1esqmZTiLjdAUur5W
Primary address path: m/86'/0'/0'/0/0
Funding address (P2TR): bc1p8qf06ujs06tmujvvddvfe58j4dq5wgnw5n0r9y8qnyslpxp4xzzq6lvh0z
Funding address WIF: KxScnSty3zP2bJnZvmgthLdn3jponatSyauiwxpMEXXAeE2M9EMz
Funding address path: m/86'/0'/0'/1/0
Full Data: {
  "phrase": "loud please install guilt shoe move decade matrix bleak venue swing whale",
  "primary": {
    "address": "bc1p9lyej8qkpx42ms3rjlue598kxt8kpfyuw3jwuk8jtqvg4y6uqyeqav2y7r",
    "path": "m/86'/0'/0'/0/0",
    "WIF": "L18PiBLxSBUjfAKswMXat7LarR3VA234NDD1esqmZTiLjdAUur5W"
  },
  "funding": {
    "address": "bc1p8qf06ujs06tmujvvddvfe58j4dq5wgnw5n0r9y8qnyslpxp4xzzq6lvh0z",
    "path": "m/86'/0'/0'/1/0",
    "WIF": "KxScnSty3zP2bJnZvmgthLdn3jponatSyauiwxpMEXXAeE2M9EMz"
  },
  "imported": {}
}
```

Default configuration:

```dotenv
WALLET_PATH=.
WALLET_FILE=wallet.json
```

You can also use:

```dotenv
WALLET_PATH=./wallets
WALLET_FILE=wallet.json
```

Ensure your `.env` file reflects your wallet setup.

#### 2. Explore the CLI

Get the full list of available commands:

```bash
atomicals --help
```

Run any supported command, such as:

```bash
atomicals mint ...
```

For a detailled description of possible commands look into [./docs/help.md](./docs/help.md)

You can also use the [Atomicals CLI Navigator](https://chatgpt.com/g/g-680762ae4fcc8191a319d1193c6626a6-atomicals-cli-navigator) to help you navigate through this cli. 

#### Using as a JavaScript/TypeScript SDK

You can also use `atomicals-js` as a module in your Node.js or TypeScript project.

Install it as a dependency:

```bash
npm install atomicals-js
```

Then use it in code:

```ts
import { Atomicals, createMnemonicPhrase, ElectrumApi } from 'atomicals-js';

const mnemonic = createMnemonicPhrase();
console.log("Mnemonic:", mnemonic);

const api = new ElectrumApi({ baseUrl: 'https://ep.wizz.cash/proxy' });
const atomicals = new Atomicals(api);

const result = await atomicals.walletCreate();
console.log(result);
```

Types are included and automatically supported by modern IDEs.

### For Developers/Contributors

If you plan to contribute to the project or need to build it locally:

1. Clone the repository:

```bash
git clone https://github.com/atomicals/atomicals-js.git
cd atomicals-js
```

2. Install dependencies and build:

```bash
yarn install
npm run postinstall:dev  # Applies local patches if needed
yarn run build
```

3. Use the CLI locally:

```bash
yarn cli --help
```

Only contributors or developers should work directly from source. Most users should prefer the npm-based installation.

## Community 

Atomicals was recently TakeOver by the Community (CTO), if you want to join us: 
- [@AtomicalsFDN](https://x.com/atomicalsfdn?s=21)
- [Telegram: @AtomicalsCommunity](https://t.me/AtomicalsCommunity)
- [atomicals.space](https://atomicals.space)

### General warnings

Stay SAFE, interact ONLY with Official accounts and please NEVER SEND YOUR PRIVATE KEYS! 

This package is experimental and bugs can happen, don't put your savings into this cli wallet. 
