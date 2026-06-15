# Getting Started

This page gets you from "I just heard about PezkuwiChain" to "I have an account
and can move tokens."

## 1. Get a wallet

The easiest way in is the **[Pezkuwi Wallet](wallet.md)** mobile app (Android,
available on Google Play). Wallets let you:

- create or import an account (a 12/24-word secret phrase),
- hold **HEZ**, **PEZ**, and **PEZ-20** assets,
- send and receive across the relay chain, Asset Hub, and People Chain.

!!! danger "Protect your secret phrase"
    Your recovery phrase **is** your account. Anyone who has it controls your
    funds. Write it down offline, never type it into a website, and never share
    it — no admin or "support" will ever ask for it.

## 2. Understand the addresses

A single account works across all PezkuwiChain chains, but balances are tracked
**per chain**. The same address can hold:

- HEZ on the **relay chain**,
- PEZ-20 assets (and staking) on **Asset Hub**,
- identity on the **People Chain**.

When you send tokens, make sure you're sending **on the right chain** — sending an
Asset Hub token expects an Asset Hub balance, etc. The wallet handles most of this
for you.

## 3. Do something useful

| Goal | Where to go |
|------|-------------|
| Send / receive tokens | [Pezkuwi Wallet](wallet.md) |
| Trade HEZ / PEZ / USDT | [PEX Exchange](exchange.md) |
| Earn staking rewards | [Staking & Collators](staking.md) |
| Vote on proposals | [Governance](governance.md) |
| Explore all apps | [Ecosystem](ecosystem.md) |

## 4. Connect to the network (developers)

Public RPC endpoints:

| Chain | Endpoint |
|-------|----------|
| Relay chain | `wss://rpc.pezkuwichain.io` |
| Asset Hub | `wss://asset-hub-rpc.pezkuwichain.io` |

Build with the `@pezkuwi/*` libraries (the sovereign equivalent of `@polkadot/*`).
See the **[SDK documentation](https://docs.pezkuwichain.io/)** for the API
reference and runtime/pallet details.
