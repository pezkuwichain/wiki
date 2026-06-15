# Architecture

PezkuwiChain is a **multi-chain network**: a central relay chain that provides
shared security, plus specialized *system parachains* that each handle one job
well. This is the same proven design used by Polkadot, on top of which the
sovereign `pezkuwi-sdk` is built.

## The chains

```
            ┌──────────────────────────────────────────────┐
            │            PEZKUWICHAIN RELAY CHAIN           │
            │   Shared security · validator set · HEZ gas   │
            │              Block time: ~6 seconds           │
            └───────────────┬──────────────────────────────┘
                            │  (shared security)
        ┌───────────────────┼───────────────────┬───────────────────┐
        ▼                   ▼                   ▼                   ▼
┌───────────────┐  ┌───────────────┐  ┌───────────────┐  ┌───────────────┐
│   ASSET HUB   │  │ PEOPLE CHAIN  │  │  GOVERNANCE   │  │  BRIDGE HUB    │
│ tokens (PEZ-  │  │ identity &    │  │  proposals &  │  │ cross-network  │
│ 20/721),      │  │ citizenship   │  │  referenda    │  │ bridging       │
│ staking,      │  │ (KYC)         │  │  (Welati)     │  │                │
│ collators     │  │               │  │               │  │                │
└───────────────┘  └───────────────┘  └───────────────┘  └───────────────┘
```

### Relay Chain (PezkuwiChain Mainnet)

The backbone. It runs the **validator set** that secures the whole network using
**TNPoS** (Trust-enhanced Nominated Proof-of-Stake), an NPoS variant that factors
on-chain reputation into validator selection. The native gas token here is
**HEZ**. Block time is roughly **6 seconds**.

- Public RPC: `wss://rpc.pezkuwichain.io`

### Asset Hub

The home of **assets and value**. All issued fungible tokens (**PEZ-20**) and
NFTs (**PEZ-721**) live here, managed by the `pallet-assets` and `pallet-nfts`
runtime modules. Asset Hub is run by **collators** (block producers for the
parachain).

Following the network's **Asset Hub Migration (AHM)**, **NPoS staking now runs on
Asset Hub** (via the async staking pallet) rather than on the relay chain. If you
are nominating or checking staking figures, Asset Hub is the source of truth.

- Public RPC: `wss://asset-hub-rpc.pezkuwichain.io`

### People Chain

Handles **identity and citizenship** — on-chain identities and privacy-preserving
KYC. It is also run by collators. The People Chain keeps identity workloads off
the relay chain so they stay cheap and fast.

### Governance

Where the network governs itself: **proposals, referenda, and voting**, powered by
the **Welati** governance pallet. See [Governance](governance.md).

### Bridge Hub

Dedicated to **cross-network bridging** — moving messages and assets between
PezkuwiChain and external networks.

## Who runs the network?

| Role | Where | Job |
|------|-------|-----|
| **Validators** | Relay chain | Produce & finalize relay blocks, secure the network (TNPoS) |
| **Nominators** | Asset Hub (post-AHM) | Back validators with staked HEZ, share rewards |
| **Collators** | Asset Hub, People Chain | Produce parachain blocks, submit proofs to the relay chain |

See [Staking & Collators](staking.md) for how to participate.

## Why a fork of the Polkadot SDK?

PezkuwiChain reuses the most audited multi-chain framework in the industry, but
publishes its own sovereign packages (`@pezkuwi/*`) and chain spec. This gives the
network independence (its own tokens, governance, branding, and roadmap) without
re-inventing low-level consensus and networking.

!!! info "Developer note"
    Application code targeting PezkuwiChain should use the `@pezkuwi/*` libraries,
    not the upstream `@polkadot/*` packages. The full mapping and API reference
    live in the [SDK docs](https://docs.pezkuwichain.io/).
