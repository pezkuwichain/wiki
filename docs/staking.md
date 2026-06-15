# Staking & Collators

PezkuwiChain is secured by **TNPoS** (Trust-enhanced Nominated Proof-of-Stake).
You can take part in three ways: **nominate** (easiest), **validate**, or run a
**collator**.

!!! important "Staking lives on Asset Hub now"
    After the **Asset Hub Migration (AHM)**, NPoS staking moved from the relay
    chain to **Asset Hub**. Nominate, check `staking.counterForNominators`, and
    read staking figures **on Asset Hub** (`wss://asset-hub-rpc.pezkuwichain.io`),
    not the relay chain.

## Nominating (recommended for most users)

Nominators back one or more validators with their staked **HEZ** and earn a share
of the rewards those validators produce. You don't run any infrastructure.

In broad strokes:

1. Hold HEZ in your account.
2. **Bond** an amount for staking.
3. **Nominate** a set of validators you trust.
4. Earn rewards each era; **unbond** later (subject to an unbonding period) to
   free your funds.

!!! tip
    Spread your nomination across several reliable validators rather than one.
    Rewards depend on the validators you pick actually being elected and staying
    online.

## Validating

Validators run a node, are elected into the active set via TNPoS, and produce and
finalize relay-chain blocks. They put up their own stake and attract nominations.
Misbehavior (e.g. going offline or equivocating) can be **slashed**, so validating
is an operational commitment.

Because TNPoS is *trust-enhanced*, on-chain reputation is a factor in selection —
not just raw stake.

## Running a collator

Collators are the block producers for the **parachains** (Asset Hub, People
Chain). They collect transactions, build parachain blocks, and submit them with
proofs to the relay chain's validators.

- Collators are listed via `collatorSelection.invulnerables` (the configured,
  trusted collator set) on each parachain.
- At the network's current stage the collator set is intentionally small and
  curated across Asset Hub and the People Chain.

## Rewards & the halving

Staking rewards come from HEZ issuance, which follows a **48-month synthetic
halving** schedule — the reward rate steps down over time, similar in spirit to
Bitcoin's halving, to balance early-network security incentives with long-term
scarcity.

!!! info "Operator details"
    Exact bonding minimums, era lengths, unbonding periods, and node setup
    instructions are version-specific. Check the current on-chain constants and
    the [SDK docs](https://docs.pezkuwichain.io/) before committing real funds or
    infrastructure.
