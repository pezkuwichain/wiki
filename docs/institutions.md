# Institutions

Every office in PezkuwiChain is a **tikî** — an entry in the citizen register
attached to an account. Fifty-six exist. What matters is not the list but the four
ways one is obtained: **automatic** (citizenship itself), **elected**, **earned** (by
contribution, at published thresholds), and **appointed**. An office may never be
granted by the route that grants a community badge, and the runtime refuses it.

## The elected and appointed bodies

| Office | Seats | Chosen by | Term |
|---|---|---|---|
| **Serok** (President) | 1 | Every citizen | 4 years, at most 2 consecutive |
| **Meclis** (Parliament) | **201** | Every citizen, across 10 districts | 4 years — **first term halved** |
| **Serokê Meclisê** (Speaker) | 1 | Elected, from sitting members | The parliament's remaining mandate |
| **Dîwan** (Constitutional Court) | **11** | **6 by the Meclis, 5 by the Serok** | **9 years** |
| **Serokwezîran** (Prime Minister) | 1 | Serok nominates, **Meclis confirms** | Until dismissed |
| **Kabîne** (Cabinet) | 7 named + general | The Serokwezîran alone | — |

### Serok

To stand: an approved identity, a trust score of at least **250**, **1,000
endorsements** each from a citizen with trust of at least 40, and a **100 HEZ**
deposit. The election needs **50% turnout**, waived only after one failed attempt so
that a boycott delays rather than vetoes. A candidate wins outright above half the
valid votes; otherwise the top two go to a runoff whose campaign is one third the
length.

### Meclis

Trust of at least **100**, one hundred endorsements, **40% turnout**. The first
parliament sits for **half a term** — deliberately, so the legislature is staggered
against the presidency permanently and no single election ever renews the whole
state at once.

### Dîwan

Nine years, the longest term in the system and longer than any body that appoints to
it. **Six seats are elected by the Parliament, five appointed by the President;
neither can seat a majority.** The split is not written as "five" — it is derived as
*total minus elected*, so changing the size of the court cannot silently change the
balance between the two powers that fill it.

Elected members need trust of at least **275**. Appointed members must already hold
one of **fourteen** qualifying professional tikîs — jurist, judge, prosecutor,
engineer, cyber-security specialist, network operator, economist, accountant,
planner, electoral officer, statistician, auditor, scholar, cultural custodian. A
president may choose, but only from people the register already recognises as
qualified.

!!! note "There is no call to dismiss a member of the court"
    The absence is deliberate.

Two thirds of the court constitutes the **register authority**, which governs the
citizen register itself, administers the validator pool, and can strip an elected or
earned office.

## The civil service

Twenty-four professional offices, from judge and prosecutor to notary, registrar,
tax collector, ambassador and teacher. Any minister or the President may nominate;
**nobody may nominate themselves**; every nomination needs trust of at least **75**
and lapses in seven days.

**Five of the twenty-four cannot be seated by the President alone** — judge,
treasurer, cyber-security specialist, inspector and ambassador require parliamentary
confirmation. And the list of which five is amendable **only by the Parliament**: the
executive cannot shorten the list of offices it does not control.

## Trust, and why offices do not compound

Standing is a single number from zero to a thousand, from four measured parts:

| Part | Weight | Measures |
|---|---|---|
| **Perwerde** (education) | 30 | Points from completed, certified courses |
| **Referral** | 25 | Citizens vouched for, net of revocations |
| **Tikî** | 25 | Community and contribution badges held |
| **Staking** | 20 | Size and duration of stake |

The weights sum to one hundred and the runtime asserts it. Each part is divided by
what is **attainable** rather than by a number written beside it — the education
maximum is every rewarded course taken at full value, and the referral maximum is the
score a citizen reaches at the vouching ceiling the register's rules currently set —
so a weight that says twenty-five is twenty-five, and stays twenty-five if a
ninety-day referendum moves the ceiling. Zero stake is zero trust —
the staking part is a gate, not merely a weight. But capital is the smallest of the
four, and its own scale saturates: the tiers stop rewarding size above 750 HEZ, and
the largest remaining multiplier comes from holding for twelve months rather than
from holding more.

**Offices are excluded from the tikî component.** Otherwise power would compound: an
office would raise trust, trust would qualify for more offices, and the register
would drift toward whoever already held it.

See also **[Governance](governance.md)**, **[Treasuries](treasuries.md)** and the
**[whitepaper](https://pezkuwichain.io/whitepaper)**.
