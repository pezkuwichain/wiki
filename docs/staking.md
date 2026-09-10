# Staking & Collators

PezkuwiChain is secured by **TNPoS** (Trust-enhanced Nominated Proof-of-Stake).
You can take part in three ways: **nominate** (easiest), **validate**, or run a
**collator**.

!!! important "Staking lives on Asset Hub"
    Nominate, check `staking.counterForNominators`, and read staking figures **on
    Asset Hub** (`wss://asset-hub-rpc.pezkuwichain.io`), not the relay chain. It has
    been there since genesis — this network has no migration to perform, and
    upstream text about an "Asset Hub Migration" does not describe it.

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

!!! warning "What nomination does and does not decide"
    TNPoS does not elect the committee by stake. It fills **nine strata of three
    seats each**, and inside a stratum a higher score buys **no advantage at all**:
    a score decides whether you may enter the pool, and a **uniform random draw**
    decides whether you sit. Nomination and Phragmen still rank candidates, but only
    inside the **stake stratum** — three seats of twenty-seven. Trust is a gate, not
    a ranking. See **[TNPoS](tnpos.md)**.

## Running a collator

Collators are the block producers for the **teyrchains** (Asset Hub, People
Chain). They collect transactions, build teyrchain blocks, and submit them with
proofs to the relay chain's validators.

- Collators are listed via `collatorSelection.invulnerables` (the configured,
  trusted collator set) on each teyrchain.
- At the network's current stage the collator set is intentionally small and
  curated across Asset Hub and the People Chain.

## Where staking rewards come from

Staking rewards come from **HEZ issuance**, and HEZ does **not** halve. Emission is
a flat share of a **fixed 200,000,000 base** — 8% by default, capped at 10% by a
constant no parameter can exceed — of which 15% goes to the treasury and the rest to
those securing the chain. Because the base is fixed rather than the total issuance,
the emission does not compound and the *effective* rate falls each year.

!!! danger "The halving belongs to PEZ, not HEZ"
    The 48-month halving is **PEZ's** rewards schedule — a fixed five billion
    released monthly to citizens and the state budget. The two tokens have opposite
    supply rules, and a sentence about "the halving" that does not name its token is
    wrong about one of them. See **[Tokens](tokens.md)**.

!!! info "Operator details"
    Exact bonding minimums, era lengths, unbonding periods, and node setup
    instructions are version-specific. Check the current on-chain constants and
    the [SDK docs](https://docs.pezkuwichain.io/) before committing real funds or
    infrastructure.
