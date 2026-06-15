# Governance

PezkuwiChain governs itself **on-chain**. Token holders propose changes, the
community votes, and approved changes are enacted by the runtime automatically —
no central administrator required.

## The Welati pallet

Governance is powered by the **Welati** pallet (Kurdish for *country / nation*).
It manages **proposals** and **referenda**: how ideas are submitted, debated, voted
on, and enacted.

The **PEZ** token is the governance token — it carries voting weight and funds the
treasury.

## How a change happens (high level)

1. **Proposal** — someone submits a proposal (a parameter change, a treasury
   spend, a runtime upgrade, etc.).
2. **Referendum** — the proposal goes to a vote open to token holders.
3. **Voting** — holders vote for or against, with weight based on tokens (and,
   where applicable, conviction/lock-up).
4. **Enactment** — if it passes, the runtime enacts the change after a delay.

## The Treasury

The **PezTreasury** pallet holds community funds (launched with an initial supply
on the order of **5 billion PEZ**). Governance decides how treasury funds are
spent — for example funding development, grants, or ecosystem initiatives.

## Where to participate

The governance interface is the web app at **[app.pezkuwichain.io](https://app.pezkuwichain.io/)**
(also mirrored at **pex.mom**). There you can view live network stats —
validators, collators, nominators — and engage with governance.

!!! info
    Specific tracks, voting periods, conviction multipliers, and thresholds are
    runtime parameters and can change via governance itself. Check the live app
    and [SDK docs](https://docs.pezkuwichain.io/) for current values.
