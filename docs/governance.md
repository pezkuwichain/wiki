# Governance

PezkuwiChain governs itself on-chain, and it does so through **two separate
electorates that count differently**. This is the most important thing to understand
about the system, and it is the thing most easily assumed wrong.

!!! warning "A token balance does not buy a vote"
    On the People chain — where citizenship, offices and the register are decided —
    a referendum is tallied against the **whole citizen roll**. One citizen, one
    vote. A wallet holding a billion HEZ has exactly the weight of a wallet holding
    none. **PEZ carries no voting weight anywhere.** It is the reward and budget
    asset, not a governance token.

## The two electorates

| | **People chain** | **Relay chain** |
|---|---|---|
| Decides | Citizenship, offices, the register, state spending | Network parameters, upgrades, the treasury of last resort |
| Counted by | The citizen roll — one person, one vote | Stake, with conviction |
| Token weight | None | HEZ |
| Pallet | `welati` + `referenda` with a citizen tally | `conviction-voting` + `referenda` |

Neither electorate votes in the other's house. The relay chain has **no `root`
governance track at all**: no referendum there can dispatch as root, and no
collective can. Root arrives from exactly one place — a message from the People
chain, converted by a single origin converter that matches that chain and nothing
else.

## Tracks on the People chain

| Track | Decision period | Confirm | For |
|---|---|---|---|
| `root` | 28 days | 24 h | Anything on this chain |
| `welati_election` | 14 days | 12 h | Electoral machinery |
| `welati_admin` | 7 days | 3 h | Routine administration |
| `citizenship_admin` | 14 days | 6 h | The register's administration |
| `qeyd_rules` | **90 days** | 7 days | The rules of admission to the register |

The last row is deliberate. The parameters that decide who may vouch for a new
citizen, how many people one citizen may vouch for, and what suspends that right,
live in a parameter store whose **only** administrator is a referendum on the
ninety-day track. Not root, not the court, not the president. Changing the rules of
admission takes three months of deliberation by the people already admitted.

## The citizens' initiative

Citizens can open a referendum with no office involved. **One percent of the roll**,
recomputed live against the current register, backing a proposal within fourteen
days, opens it. Deposit ten HEZ; cooldown thirty days.

## Who holds which power

Governance is not only referenda. Most authority sits with elected and appointed
offices, and each is bounded — see **[Institutions](institutions.md)** for how each
one is filled, and **[Treasuries](treasuries.md)** for who may move which fund.

## Where to participate

The governance interface is **[app.pezkuwichain.io](https://app.pezkuwichain.io/)**,
mirrored at **pex.mom**.

!!! info "Figures here are measured from the runtime"
    Every number on this page is taken from the source. Tracks, periods and
    thresholds are runtime parameters and can be changed by governance itself; the
    canonical narrative is the
    **[whitepaper](https://pezkuwichain.io/whitepaper)**, and the code is the final
    authority.
