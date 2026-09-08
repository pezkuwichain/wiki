# Architecture

PezkuwiChain is a **multi-chain network**: a central relay chain that provides
shared security, plus specialized *teyrchains* (system chains) that each carry one
function of the state and nothing else. This is the same proven design used by
Polkadot, on top of which the sovereign `pezkuwi-sdk` is built — but here it is not
a scaling decision. It is a **separation-of-powers decision expressed as topology**:
the chain that holds the register is not the chain that holds the money, and neither
is the chain that produces blocks.

**Five chains are specified; two run from the first block.** The relay schedules
exactly two cores at genesis — Asset Hub and People, the two a state cannot run
without. Bridge Hub and Coretime are written and will be seated when there is
traffic for them to carry.

## The chains

```
            ┌───────────────────────────────────────────────┐
            │           PEZKUWICHAIN RELAY CHAIN            │
            │  Shared security · validator committee · HEZ  │
            │  escrow · no root track of its own · ~6 s     │
            └───────────────┬───────────────────────────────┘
                            │  (shared security)
     ┌──────────────────────┼──────────────┬──────────────────┐
     ▼                      ▼              ▼                  ▼
┌──────────────┐  ┌──────────────────┐  ┌────────────┐  ┌────────────┐
│  ASSET HUB   │  │  PEOPLE  (1004)  │  │ BRIDGE HUB │  │  CORETIME  │
│    (1000)    │  │ register · offices│  │   (1002)   │  │   (1005)   │
│ every fund   │  │ courts · trust    │  │ bridges to │  │ blockspace │
│ PEZ · wHEZ   │  │ validator pool    │  │ Ethereum   │  │ allocation │
│ wUSDT        │  │ governance (welati)│ │            │  │            │
│ staking      │  │                   │  │ specified, │  │ specified, │
│ elections    │  │ ── the one door ──┼─▶│ not seated │  │ not seated │
│              │  │    into root      │  │            │  │            │
└──────────────┘  └──────────────────┘  └────────────┘  └────────────┘
       running             running          at genesis      at genesis
```

There is **no separate governance chain.** Governance lives where the electorate
does: the citizen roll and the `welati` pezpallet are on the People chain, and HEZ
conviction voting is on the Asset Hub and the relay. A diagram showing a fourth
"Governance" box described a plan that was never built.

### Relay Chain (PezkuwiChain Mainnet)

The backbone. It runs the **validator set** that secures the whole network using
**TNPoS** (Trust-enhanced Nominated Proof-of-Stake), in which a score decides
*whether* a citizen may enter the validator pool and a uniform random draw decides
*who sits* — trust is a gate, not a ranking. The native gas token here is **HEZ**.
Block time is roughly **6 seconds**. The relay has **no `root` governance track of
its own**: root arrives from the People chain and nowhere else.

- Public RPC: `wss://rpc.pezkuwichain.io`

### Asset Hub

The home of **assets and value**. All issued fungible tokens (**PEZ-20**) and
NFTs (**PEZ-721**) live here, managed by the `pallet-assets` and `pallet-nfts`
runtime modules. Asset Hub is run by **collators** (block producers for the
teyrchain).

**Staking runs on Asset Hub** (via the async staking pallet), and has since genesis
— this network has no migration to perform. If you are nominating or checking
staking figures, Asset Hub is the source of truth. It also holds **every fund**,
including the treasury the five spender tracks pay from.

- Public RPC: `wss://asset-hub-rpc.pezkuwichain.io`

### People Chain

Handles **identity and citizenship** — on-chain identities and privacy-preserving
KYC. It is also run by collators. The People Chain keeps identity workloads off
the relay chain so they stay cheap and fast.

- Public RPC: `wss://people-rpc.pezkuwichain.io`

### Bridge Hub and Coretime

**Bridge Hub** (1002) is dedicated to cross-network bridging — moving messages and
assets between PezkuwiChain and external networks. **Coretime** (1005) allocates
blockspace. Both are written and specified; neither is seated at genesis, where the
relay schedules two cores.

### Governance is not a chain

Governance lives on the chains that hold the electorates: the citizen roll and the
`welati` pezpallet on **People**, HEZ conviction voting on the **Asset Hub** and the
relay. See [Governance](governance.md).

## Who runs the network?

| Role | Where | Job |
|------|-------|-----|
| **Validators** | Relay chain | Produce & finalize relay blocks, secure the network (TNPoS) |
| **Nominators** | Asset Hub | Back validators with staked HEZ, share rewards — ranking candidates inside the **stake stratum only** |
| **Collators** | Asset Hub, People | Produce teyrchain blocks, submit proofs to the relay chain |

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
