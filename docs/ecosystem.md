# Ecosystem

The apps and services built on and around PezkuwiChain.

## Core apps

| App | What it is | Link |
|-----|------------|------|
| **Pezkuwi Wallet** | Official non-custodial mobile wallet (Android) | Google Play |
| **Pezkuwi Extension** | Browser wallet (Chrome / Firefox) for accounts & signing | Chrome Web Store · [GitHub](https://github.com/pezkuwichain/pezkuwi-extension) |
| **PEX Exchange** | Non-profit exchange for HEZ / PEZ / USDT | [pex.network](https://pex.network/) |
| **Governance app** | Live network stats + on-chain governance | [app.pezkuwichain.io](https://app.pezkuwichain.io/) |
| **Telegram Mini App** | Wallet & DeFi features inside Telegram | via the official Pezkuwi bot |
| **bereketli** | B2B / merchant-facing services | [bereketli.pezkiwi.app](https://bereketli.pezkiwi.app/) |

### Pezkuwi Extension

The **Pezkuwi browser extension** is the desktop counterpart to the mobile wallet.
It manages your accounts and signs transactions for dApps in **Chrome** and
**Firefox** — the Pezkuwi-native equivalent of the polkadot.js extension. Install
it from the **Chrome Web Store**, then connect to apps like the
[governance app](https://app.pezkuwichain.io/) or [PEX](https://pex.network/).

!!! danger "Only install the official extension"
    Browser wallet extensions can see what you sign. Install only the official
    Pezkuwi extension from the Chrome Web Store, and treat its account password and
    your recovery phrase the same way you would in any wallet — never share them.

## Infrastructure & developer resources

| Resource | Purpose | Link |
|----------|---------|------|
| **SDK documentation** | Runtime, pallets, and `@pezkuwi/*` API reference | [docs.pezkuwichain.io](https://docs.pezkuwichain.io/) |
| **Relay RPC** | Connect to the relay chain | `wss://rpc.pezkuwichain.io` |
| **Asset Hub RPC** | Connect to Asset Hub | `wss://asset-hub-rpc.pezkuwichain.io` |
| **People Chain RPC** | Connect to the People Chain | `wss://people-rpc.pezkuwichain.io` |
| **GitHub** | Source code & SDK | [github.com/pezkuwichain](https://github.com/pezkuwichain) |

## How the pieces fit together

- The **wallet** and **mini app** let people hold and move tokens.
- **PEX** provides liquidity and trading.
- The **governance app** surfaces the live state of the network (validators,
  collators, nominators) and lets the community govern it.
- **bereketli** brings PezkuwiChain to businesses and merchants.
- Everything is built on the chains described in [Architecture](architecture.md),
  using the tokens and standards in [Tokens & Standards](tokens.md).

!!! note
    This list grows as the ecosystem does. If an app is missing, propose an edit
    via the ✏️ button.
