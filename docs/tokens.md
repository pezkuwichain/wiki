# Tokens & Standards

PezkuwiChain has a **dual-token economy** and a small, familiar family of
**token standards**.

## The two native tokens

| Token | Role | Notes |
|-------|------|-------|
| **HEZ** | Native **gas & security** token | Pays transaction fees; staked to secure the network. Inflationary: **8% by default against a fixed 200,000,000 base, capped at 10% in code.** No halving — that belongs to PEZ. |
| **PEZ** | **Reward & budget** asset | **Not a governance token — it carries no voting weight.** Fixed at 5,000,000,000 forever, with no mint or burn path and a keyless admin account. 96.25% is the commons, released monthly and **halving every 48 releases**, split 75% to citizens and 25% to the state budget. **Nothing is released until the roll passes 100,000 citizens** — see [Treasuries](treasuries.md). |

On **Asset Hub**, the canonical representations at genesis are **PEZ (Asset ID 1)**,
**wHEZ (Asset ID 2, wrapped HEZ)** and **wUSDT (Asset ID 1000)**.

!!! note "wHEZ is not how HEZ moves between chains"
    HEZ is **native** on the relay, the Asset Hub and People alike, and moves between
    them by **teleport** against the escrow the relay holds. wHEZ is a separate
    convenience: HEZ wrapped one-for-one as an asset so that pallets handling assets
    rather than the native balance can trade it. Wrapping and teleporting are two
    different mechanisms, and neither creates supply.

!!! note "HEZ vs PEZ-20"
    Just as ETH itself is not an ERC-20 token, **HEZ — the native gas token — is
    not a PEZ-20 token.** It lives in the `Balances` pallet. PEZ-20 is the
    standard for *issued* assets registered on Asset Hub.

## Token standards: PEZ-20 & PEZ-721

PezkuwiChain defines token standards so that anyone coming from Ethereum
(ERC-20 / ERC-721), BNB Chain (BEP-20), or Tron (TRC-20) instantly understands
how tokens work here.

| Standard | What it is | Backed by |
|----------|------------|-----------|
| **PEZ-20** | Fungible tokens (currencies, stablecoins, LP tokens) | `pallet-assets` on Asset Hub |
| **PEZ-721** | Non-fungible tokens (NFTs, collectibles, certificates) | `pallet-nfts` on Asset Hub |

!!! warning "These are not smart-contract standards"
    Pezkuwi Asset Hub has **no EVM and no smart-contract layer.** PEZ-20 and
    PEZ-721 are **runtime-native** standards: a token is not a deployed contract
    with an address — it is a **registered asset with an on-chain ID** managed
    directly by the runtime. This makes tokens cheaper, faster, and impossible to
    brick with buggy contract code.

### PEZ-20 — fungible tokens

A PEZ-20 token is a fungible asset in the `Assets` pallet, identified by a numeric
**Asset ID** (the equivalent of an ERC-20 contract address).

| Concept | Ethereum (ERC-20) | Pezkuwi (PEZ-20) |
|---------|-------------------|------------------|
| Token identity | Contract address `0x…` | **Asset ID** (`u32`) |
| Where it lives | A deployed contract | The `Assets` pallet registry |
| Native coin | ETH is *not* an ERC-20 | HEZ is *not* a PEZ-20 (it's in `Balances`) |
| Metadata | `name`, `symbol`, `decimals` | `name`, `symbol`, `decimals` (on-chain) |

Typical PEZ-20 tokens you may see in wallets and on the exchange include **USDT
(PEZ-20)** — i.e. USDT issued on Pezkuwi Asset Hub, shown with a "PEZ-20" badge
the same way other chains show "USDT TRC-20" or "USDT ERC-20".

### PEZ-721 — non-fungible tokens

PEZ-721 covers NFTs, collectibles, and certificates, backed by `pallet-nfts`.
Collections and items each have on-chain IDs and metadata.

!!! info "Full standard reference"
    The complete, version-pinned standard (interfaces, required metadata, and the
    ERC↔PEZ mapping) is published in the SDK docs:
    **[Token Standards](https://docs.pezkuwichain.io/token-standards/)**.

## How "PEZ-20" appears in apps

Different apps follow their own existing convention for labeling networks:

- **PEX exchange** and the **mini app / pwap**: assets like USDT show a
  **"PEZ-20 (Pezkuwi Asset Hub)"** badge — the same pattern they use for
  TRC-20 / ERC-20.
- **Pezkuwi Wallet**: shows the chain name only (e.g. "Pezkuwi Asset Hub"),
  consistent with how it shows "Ethereum" rather than "ERC-20".
