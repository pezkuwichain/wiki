# Treasuries

Every fund sits on the **Asset Hub**. Every authority to draw from one sits on the
**People chain**. A payment is a cross-chain message from an office to a vault, and
the vault's own configuration names the single chain it will listen to.

The consequence is worth stating plainly: **an officeholder cannot reach the money by
holding a key.** They reach it by holding an office, and the office is an entry in a
register that citizens elect.

## Who may move what

| Fund | Token | Who may propose | Who decides | How it pays |
|---|---|---|---|---|
| **Treasury** | HEZ | Network governance, five spender tiers from 250 to 1,000,000 | The referendum on that track | Within 30 days |
| **Airdrop pot** | HEZ | The **Serokwezîran** | The **Serok** — plus the **Xezinedar** above 1,000,000, with a 7-day delay | Within 30 days |
| **Presale pot** | HEZ | The **Wezîrê Darayiyê** | The **Meclis**, simple majority | Within 365 days, after the lock |
| **Government pot** | PEZ | The **Wezîrê Darayiyê**, bounded by the approved budget | The Meclis, when it passed the budget | Immediate |
| **Incentive pot** | PEZ | No proposal — a citizen claims | The trust score, arithmetically | Immediate |

## What the vaults refuse

Four of the five name **exactly one chain** they accept instruction from: the People
chain. Not the relay. Not root. Not a key. The airdrop pot, the presale pot and both
PEZ pots are configured with an origin that matches the People chain's location and
has **no root arm at all**.

!!! warning "The chain's superuser cannot pay itself"
    The relay's root can halt the chain, upgrade the runtime, and reject a proposed
    spend — but it cannot spend the airdrop, the presale, or either PEZ pot. To move
    that money it would have to become the People chain, and the People chain is a
    register of elected offices.

The HEZ treasury is the exception, and is documented as such: root can spend it
without limit. It is the fund of last resort, and the one place where the network's
own governance rather than the state's holds the purse.

## A payment, end to end

The airdrop path shows the whole shape:

1. The **Serokwezîran** proposes an amount and a beneficiary.
2. The **Serok** approves. Above one million HEZ the **Xezinedar** must also sign,
   and the payment cannot execute for **seven days** after the last signature — a
   cooling period proportional to the size.
3. **Anyone** may then execute. Execution is permissionless because every
   discretionary decision has already been made and recorded; what remains is
   arithmetic, and arithmetic should not wait on a signature.
4. The People chain sends a message naming the pot, the beneficiary and the amount.
   The pot's origin check confirms the sender.
5. The beneficiary collects within the payout window.

Every step emits an event. The proposal names its proposer, the approval names its
approver, and the amount is on the wire in the clear.

## The budget

The government pot is not spent proposal by proposal. The Meclis passes a budget,
which credits an approved figure; the Wezîrê Darayiyê then spends against that figure
and cannot exceed it — enforced by a bound rather than by an audit after the fact.

## The citizens' share

The incentive pot is distributed per epoch, weighted by trust: a citizen's share is
their trust score over the network's total active trust, times the epoch's pool. Ten
percent of each epoch is reserved for role-badge holders, and unclaimed rewards are
clawed back after a week so the pool cannot silently drain into abandoned accounts.

**No office signs a citizen's reward.** It is claimed, and the arithmetic is the
authority.

## Where the PEZ comes from

The rewards pool is released by arithmetic, monthly, halving every **48 releases**
(about four years). The first period releases half the pool across forty-eight
months. Each release is derived from the release index rather than accumulated, so no
drift is possible and no missed release can be double-paid. Every release splits
**75% to the incentive pot** and **25% to the government pot**. Nobody signs it; it
happens on block initialisation.

See also **[Institutions](institutions.md)**, **[Tokens](tokens.md)** and the
**[whitepaper](https://pezkuwichain.io/whitepaper)**.
