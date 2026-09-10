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
| Decides | Citizenship, offices, the register, state spending, **and the emission rate** | Network administration — staking, leases, auctions — and the treasury of last resort |
| Counted by | The citizen roll — one person, one vote | Stake, with conviction |
| Token weight | None | HEZ |
| Lives on | People | The relay **and the Asset Hub** (the treasury's five spender tracks are there) |
| Pallet | `welati` + `referenda` with a citizen tally | `conviction-voting` + `referenda` |

!!! note "The emission rate is not the holders' to set"
    It is a parameter on the Asset Hub whose only administrator is the **Xezinedar**,
    an office on the People chain — nominated by the Serok, confirmed by the Meclis,
    removable only by the Dîwan, and bounded on both sides. Holders voting on their
    own dilution under-emit; an executive that can print pays its bills by printing.
    So it goes to an office that is neither.

Neither electorate votes in the other's ballot. They are **not equals**, and it is
better to say so: the relay chain has **no `root` governance track at all** — no
referendum there can dispatch as root, and no collective can. Root arrives from
exactly one place, a message from the People chain, converted by a single origin
converter that matches that chain and nothing else. The civil layer holds the door;
the reverse door does not exist.

!!! warning "What root can do"
    Root is a seat, not an office, and two things sit in it: the People chain's
    twenty-eight-day referendum, and a **sudo key held for the founding period**,
    which retires once the chain is proved end to end, the roll can carry the support
    floor below, and a referendum has actually decided something under it. Until then
    it is absolute. And because root can upgrade a runtime — where every rule lives,
    origin filters included — every "cannot reach" in this wiki means "cannot reach
    short of a runtime upgrade".

### Support is measured against the roll, or 100,000, whichever is larger

The support thresholds fall to two percent, and two percent of a young register is a
handful of people: the curves are written for a state with millions on the roll. So
the denominator has a floor. Reaching root takes **2,000 citizens voting aye** —
a necessary size rather than a sufficient one, since they must actually vote, not
merely exist. The floor **retires itself** once the register outgrows it, and from
then on the rule is simply two percent of the roll.

## Tracks on the People chain

| Track | Decision period | Confirm | For |
|---|---|---|---|
| `root` | 28 days | 24 h | Anything on this chain except the register's own rules |
| `welati_election` | 14 days | 12 h | Electoral machinery |
| `welati_admin` | 7 days | 3 h | Routine administration |
| `citizenship_admin` | 14 days | 6 h | The register's administration |
| `qeyd_rules` | **90 days** | 7 days | The rules of admission to the register |

The last row is deliberate. The parameters that decide who may vouch for a new
citizen, how many people one citizen may vouch for, and what suspends that right,
live in a parameter store whose **only** administrator is a referendum on the
ninety-day track. Not root, not the court, not the president — the exclusion is
literal, and the twenty-eight-day root track is an arm of nothing in this store. An
optional slow path is a fast path, so the short road was not built. Changing the
rules of admission takes three months of deliberation by the people already
admitted.

## The citizens' initiative

Citizens can open a referendum with no office involved. **One percent of the roll**,
recomputed live against the current register, backing a proposal within fourteen
days, opens it. Deposit ten HEZ; cooldown thirty days.

The threshold to *open* a question is measured against the **real** roll, not against
the floor above — so asking stays cheap while deciding gets expensive. That asymmetry
is deliberate.

## Who holds which power

Governance is not only referenda. Most authority sits with elected and appointed
offices, and each is bounded — see **[Institutions](institutions.md)** for how each
one is filled, and **[Treasuries](treasuries.md)** for who may move which fund.

## Where to participate

The governance interface is **[app.pezkuwichain.io](https://app.pezkuwichain.io/)**,
mirrored at **pex.mom**.

!!! info "Figures here are measured from the runtime"
    Every number on this page is read from the source. Tracks, periods and thresholds
    are runtime parameters and can be changed by governance itself; the canonical
    narrative is the **[whitepaper](https://pezkuwichain.io/whitepaper)**, and where
    a figure here and the code disagree, **the code is correct and this page is the
    defect**.
