# Atomicals CLI Utility - Help Guide

## Introduction

This command-line utility (`yarn cli ...`) allows you to interact directly with the Atomicals Protocol on Bitcoin.

**Disclaimer**: You are interacting DIRECTLY with the Bitcoin network. Every command can have real financial consequences. **There are no reversals on Bitcoin.** Always use the `--help` option with a command *before* executing it if you are unsure about its effects. Familiarize yourself with the command's arguments and options first.

## General Usage

```bash
yarn cli <command> [options] <arguments...>
```

*   Replace `<command>` with the specific command you want to run.
*   `[options]` are optional flags (e.g., `--satsbyte 10`, `--rbf`).
*   `<arguments...>` are required inputs for the command (e.g., file paths, addresses, IDs).

General Options (Available for most commands):

*   `-V, --version`: Show the CLI version.
*   `-h, --help`: Display detailed help for the specific command or the general help if no command is specified.

## Getting Detailed Help for Commands

This document provides an overview. To see all available options, arguments, and specific details for any command, run:

```bash
yarn cli <command> --help
```

Example:

```bash
yarn cli mint-nft --help
```

----------------------------------------------------------
---

## Command Overview

Commands are grouped by their primary function:

### Wallet Management

Manage your local wallets (creation, import, balance checks).

*   `balances [options]`: Get balances and atomicals stored at internal wallets. (Alias for `wallets`)
*   `wallets [options]`: Get balances and atomicals stored at internal wallets. (More detailed than `balances`)
*   `wallet-create`: Create a new 12-word mnemonic phrase and associated addresses.
*   `wallet-decode [options] <phrase>`: Decode a mnemonic phrase to derive addresses/keys.
*   `wallet-init [options]`: Initialize a new `wallet.json` file, optionally from a phrase.
*   `wallet-import <wif> <alias>`: Import an existing private key (WIF format) into your wallet file.

### Address Information

Query information about specific Bitcoin addresses.

*   `address [options] <address>`: Get balances and Atomicals stored at a specific address.
*   `address-history <address>`: List the transaction history for an address.
*   `address-utxos <address>`: List all UTXOs (Unspent Transaction Outputs) owned by an address.
*   `address-script <addressOrAlias>`: Encode an address or wallet alias into its Bitcoin script hex.
*   `script-address <script>`: Decode a Bitcoin script hex into its address.

### Atomical Information & Querying

Get details about specific Atomicals or search/list Atomicals.

*   `get [options] <atomicalAliasOrId>`: Get the current status and basic details of an Atomical.
*   `location [options] <atomicalAliasOrId>`: Get the UTXO location(s) of an Atomical.
*   `state [options] <atomicalAliasOrId>`: Get the full current state of an Atomical.
*   `state-history [options] <atomicalAliasOrId>`: Get the historical state changes of an Atomical.
*   `events [options] <atomicalAliasOrId>`: Get the event history for an Atomical.
*   `tx-history [options] <atomicalAliasOrId>`: Get the transaction history involving an Atomical.
*   `list [options]`: List a feed of recently minted Atomicals globally.
*   `address-atomicals <address>`: List all Atomicals owned by a specific address.
*   `at-location <location>`: Get Atomicals located at a specific UTXO (`txid:index`).
*   `global [options]`: Get global status information about the Atomicals index.
*   `server-version`: Get the connected ElectrumX server version info.

### Token (FT / DFT) Management

Commands related to Fungible Tokens (FT) and Decentralized Fungible Tokens (DFT).

*   **Info/Query:**
    *   `get-ticker [options] <ticker>`: Get details for an Atomical by its Ticker symbol.
    *   `ftinfo <atomicalAliasOrId>`: Get FT-specific information for a token Atomical.
    *   `summary-tickers [options]`: Show a summary of owned FTs by ticker in your wallet.
    *   `find-tickers [options]`: Search for existing Tickers.
*   **Minting:**
    *   `mint-ft [options] <ticker> <supply> <file>`: Mint a new Fungible Token (Direct Issuance).
    *   `init-dft-fixed [options] <ticker> <mintbitworkc>`: Initialize a Decentralized FT with fixed mint parameters.
    *   `init-dft-perpetual [options] <ticker>`: Initialize a Decentralized FT with perpetual/phased mint parameters.
    *   `mint-dft [options] <ticker>`: Mint tokens for an existing Decentralized FT (DFT).
*   **Operations:**
    *   `split [options] <locationId>`: Separate FT Atomicals within a single UTXO.
    *   `custom-color [options] <locationId>`: (Advanced) Custom color operation for FTs in a single UTXO.

### Container Management

Commands for managing Container Atomicals (namespaces for collections).

*   **Info/Query:**
    *   `get-container [options] <container>`: Get details for an Atomical by its Container name.
    *   `get-container-items [options] <container> <limit> <offset>`: List items within a specific Container.
    *   `get-container-item [options] <container> <itemId>`: Get details of a specific item within a Container.
    *   `validate-container-item [options] <containerName> <itemName> <manifestFile>`: Validate a potential item against a Container's rules.
    *   `summary-containers [options]`: Show a summary of owned Containers in your wallet.
    *   `find-containers [options]`: Search for existing Containers.
*   **Minting:**
    *   `mint-container [options] <container>`: Mint a new Container NFT.
*   **Modification:**
    *   `set-container-data [options] <containerName> <jsonFilename>`: Update the data associated with a Container.
*   **DMINT (Decentralized Minting for Containers):**
    *   `prepare-dmint-items <folder> <outputFolderName>`: Prepare item manifest files from a folder (for older dmint style).
    *   `prepare-dmint <folder> <mintHeight> <bitworkc>`: Prepare the dmint config and item manifest from a folder of images (likely preferred).
    *   `enable-dmint [options] <container> <jsonFilename>`: Enable DMINT rules on a Container using a config file.
    *   `mint-item [options] <containerName> <itemName> <manifestFile>`: Mint an item NFT belonging to a DMINT-enabled Container.

### Realm & Subrealm Management

Commands for managing Realm (+realm) and Subrealm (+subrealm.realm) NFTs.

*   **Info/Query:**
    *   `resolve [options] <realm_or_subrealm>`: Resolve a Realm/Subrealm name to its Atomical details (Alias for `get-realm`).
    *   `get-realm [options] <realm_or_subrealm>`: Resolve a Realm/Subrealm name to its Atomical details.
    *   `realm-info [options] <atomicalIdAlias>`: Get Realm/Subrealm specific information for an Atomical.
    *   `summary-realms [options]`: Show a summary of owned Realms in your wallet.
    *   `summary-subrealms [options]`: Show a summary of owned Subrealms in your wallet.
    *   `find-realms [options]`: Search for existing Realms.
    *   `pending-subrealms [options]`: Display pending Subrealm mint requests and optionally pay for them.
*   **Minting:**
    *   `mint-realm [options] <realm>`: Mint a new top-level Realm NFT.
    *   `mint-subrealm [options] <realm>`: Mint a new Subrealm NFT (under an existing Realm).
*   **Management:**
    *   `enable-subrealms [options] <realmOrSubRealm> <file>`: Set/update the minting rules for Subrealms under a Realm/Subrealm.
    *   `disable-subrealms [options] <realmOrSubRealm>`: Remove the Subrealm minting rules for a Realm/Subrealm.

### General NFT Minting

General-purpose NFT creation.

*   `mint-nft [options] <file>`: Mint a standard NFT Atomical from one or more files.
*   `mint-nft-json [options] <jsonFile>`: Mint an NFT Atomical using only JSON data.

### Atomical Modification & Interaction

Update state, emit events, or manage relationships.

*   `set [options] <atomicalIdAlias> <jsonFilename>`: Set or update the data payload of an existing Atomical.
*   `set-relation [options] <atomicalId> <relationName> <relationValues...>`: Add or update a relationship tag on an Atomical.
*   `emit [options] <atomicalIdAlias> <data...>`: Emit an immutable event associated with an Atomical.
*   `delete [options] <atomicalIdAlias> <filesWithDeleteKeys>`: Delete specific keys from an Atomical's data payload.
*   `seal [options] <atomicalIdAlias>`: **PERMANENTLY** seal an NFT Atomical, making it immutable and **untransferable forever**. Use with extreme caution.

### Transfer Operations

Move Atomicals or regular Satoshis between addresses.

*   `transfer-nft [options] <atomicalId> <address>`: Transfer a single NFT Atomical to a new address.
*   `transfer-ft [options] <atomicalId>`: Transfer FT Atomicals (requires interactive prompts for amounts/destinations). Use `transfer-builder` for scripted/complex FT transfers.
*   `transfer-builder [options]`: Advanced/scriptable transfer tool, primarily for FTs but can handle complex scenarios.
*   `transfer-utxos [options]`: Transfer regular Bitcoin UTXOs (non-Atomicals) to other addresses.

### Data Storage

Store arbitrary immutable data on-chain.

*   `store-file [options] <filepath> <givenFileName>`: Store a file on-chain as immutable data (not an NFT/FT).
*   `download [options] <locationIdOrTxId>`: Download the file/data content associated with an Atomical or location.

### Utility & Advanced Operations

Less common or specialized commands.

*   `splat [options] <locationId>`: Extract a specific NFT Atomical from a UTXO containing multiple Atomicals.
*   `merge-atomicals [options]`: Merge multiple Atomical UTXOs together (primarily for testing/consolidation).
*   `await-utxo <address> <amount>`: Wait for a UTXO of a specific amount to appear at an address.
*   `dump`: Dump internal server state (Debugging).
*   `diff`: (Purpose unclear from docs - use `diff --help`).

### Bitcoin Transaction Utilities

Low-level Bitcoin transaction tools.

*   `decodetx [options]`: Decode a raw Bitcoin transaction hex.
*   `broadcast [options]`: Broadcast a raw Bitcoin transaction hex to the network.
*   `outpoint-compact <hex>`: Decode a full `txid:index` hex outpoint to its compact ID form.
*   `compact-outpoint <compactId>`: Encode a compact location ID to its full `txid:index` hex form.

---

Remember to use `yarn cli <command> --help` for specifics on any command!

