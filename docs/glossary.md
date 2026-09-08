# Glossary

**Asset Hub**
: The teyrchain (1000) that holds **every fund** and manages assets — all **PEZ-20**
  tokens and **PEZ-721** NFTs — and runs staking and the validator election. Run by
  collators. Staking has been here since genesis: this network has never had a
  migration to perform, so text describing an "Asset Hub Migration" is describing
  upstream's history rather than this chain's.

**Bridge Hub**
: The teyrchain (1002) for cross-network bridging, including Ethereum. Specified and
  written; not seated at genesis.

**Collator**
: A block producer for a **teyrchain** (Asset Hub, People). Collators build teyrchain
  blocks and submit them with proofs to the relay chain's validators.

**Council**
: The parliament's standing collective, up to a hundred members, its roster written
  from the sitting Meclis rather than elected separately — so it holds no mandate of
  its own. An alternative arm on some origins, half of the slashing origin for
  staking scores, and any single member may freeze a suspicious staking-score
  submission pending review.

**Coretime**
: The teyrchain (1005) that allocates blockspace. Specified; not seated at genesis.

**Escrow**
: The relay-held mirror of the HEZ the Asset Hub carries. Not supply — the same HEZ,
  held here and represented there — and excluded from the relay's turnout figure so
  that governance is not distorted by its size.

**HEZ**
: The native **gas and security** token of the relay, the Asset Hub and People alike.
  Pays fees and is staked. **Inflationary** — 8% by default against a fixed
  200,000,000 base, capped at 10% in code. **HEZ does not halve.** The 48-month
  halving belongs to PEZ, and the two rules are opposite.

**Nominator**
: A holder who backs validators with staked HEZ to earn a share of rewards, without
  running infrastructure. Under TNPoS nomination ranks candidates **inside the stake
  stratum only**, which carries three of twenty-seven seats.

**NPoS / TNPoS**
: Nominated Proof-of-Stake. PezkuwiChain uses **TNPoS** (Trust-enhanced NPoS), in
  which a score decides *whether* a citizen may enter the validator pool and a
  uniform random draw decides *who sits*. Inside a stratum a higher score buys no
  advantage at all — trust is a **gate, not a ranking**.

**People Chain**
: The teyrchain (1004) holding the **citizen register, every office, the courts,
  trust and the validator pool** — identity and citizenship among them. It is also
  the only place the relay's `root` can be reached from. Run by collators.

**Perwerde**
: The education pezpallet (*perwerde* = education). Its points are the
  largest-weighted part of a trust score.

**PEZ**
: The **reward and budget** asset — an asset on the Asset Hub, five billion fixed,
  keyless, with no mint and no burn path. **Not a governance token: it carries no
  voting weight anywhere.** Its rewards pool is released monthly and halves every 48
  releases, split 75% to citizens and 25% to the state budget. Nothing is released
  until the register passes a hundred thousand citizens.

**PEZ-20**
: The **fungible** token standard (runtime-native, backed by `pallet-assets` on
  Asset Hub). The Pezkuwi equivalent of ERC-20 / TRC-20.

**PEZ-721**
: The **non-fungible** token standard (NFTs), backed by `pallet-nfts` on Asset Hub.
  The equivalent of ERC-721.

**PezTreasury**
: The pezpallet holding the keyless PEZ pot and running the monthly release. The
  government pot it feeds is spent by the Wezîrê Darayiyê against a budget the Meclis
  passed; nobody signs a release itself.

**Relay Chain**
: The central chain providing shared security via the validator committee. Native
  gas: HEZ. ~6-second block time. It has **no `root` governance track of its own**.

**Root**
: A seat rather than an office. Two things sit in it: a referendum of the People
  chain, and a sudo key held for the founding period, which retires once the civil
  path has been proved to work. Root can upgrade a runtime, so every "cannot reach
  this money" in these pages means "cannot reach it short of a runtime upgrade".

**Teyrchain**
: A system chain secured by the relay. What upstream calls a parachain.

**TYR**
: The smallest unit of HEZ. 1 HEZ = 10¹² TYR.

**Validator**
: A node seated (via TNPoS) in the active committee to produce and finalize
  relay-chain blocks and secure the network.

**Welati**
: The on-chain **governance** pezpallet (*welat* = country/nation), holding the roll,
  the offices, the elections and the referenda that citizens vote in.

**wHEZ**
: Wrapped HEZ — HEZ wrapped one-for-one as an Asset Hub asset (Asset ID **2**) so
  that pallets handling assets rather than the native balance can trade it. Not a
  second HEZ, and not how a teleport moves one.

**wUSDT**
: The custodial bridge's representation of USDT on the Asset Hub (Asset ID 1000).

**`@pezkuwi/*` / pezkuwi-sdk**
: The sovereign packages PezkuwiChain publishes (a fork of the Polkadot SDK).
  Build with these instead of `@polkadot/*`.
