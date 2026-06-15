# Glossary

**AHM (Asset Hub Migration)**
: The migration that moved NPoS staking from the relay chain to **Asset Hub**.
  Since AHM, staking data and operations live on Asset Hub.

**Asset Hub**
: The system parachain that manages assets — all **PEZ-20** tokens and **PEZ-721**
  NFTs — and, post-AHM, **staking**. Run by collators.

**Bridge Hub**
: The system parachain dedicated to cross-network bridging.

**Collator**
: A block producer for a **parachain** (Asset Hub, People Chain). Collators build
  parachain blocks and submit them with proofs to the relay chain's validators.

**HEZ**
: The native **gas and security** token. Pays fees and is staked. Inflationary
  with a 48-month synthetic halving on rewards.

**Nominator**
: A token holder who backs validators with staked HEZ to earn a share of rewards,
  without running infrastructure.

**NPoS / TNPoS**
: Nominated Proof-of-Stake. PezkuwiChain uses **TNPoS** (Trust-enhanced NPoS),
  which factors on-chain reputation into validator selection.

**People Chain**
: The system parachain handling **identity and citizenship** (including
  privacy-preserving KYC). Run by collators.

**PEZ**
: The **governance** token. Carries voting weight and funds the treasury.

**PEZ-20**
: The **fungible** token standard (runtime-native, backed by `pallet-assets` on
  Asset Hub). The Pezkuwi equivalent of ERC-20 / TRC-20.

**PEZ-721**
: The **non-fungible** token standard (NFTs), backed by `pallet-nfts` on Asset Hub.
  The equivalent of ERC-721.

**PezTreasury**
: The on-chain treasury pallet holding community PEZ funds, governed by Welati.

**Perwerde**
: The education-platform pallet (*perwerde* = education).

**Relay Chain**
: The central chain providing shared security via the validator set. Native gas:
  HEZ. ~6-second block time.

**Validator**
: A node elected (via TNPoS) into the active set to produce and finalize relay-chain
  blocks and secure the network.

**Welati**
: The on-chain **governance** pallet (*welat* = country/nation), managing proposals
  and referenda.

**wHEZ**
: Wrapped HEZ — the Asset Hub representation of HEZ (Asset ID 2 at genesis).

**`@pezkuwi/*` / pezkuwi-sdk**
: The sovereign packages PezkuwiChain publishes (a fork of the Polkadot SDK).
  Build with these instead of `@polkadot/*`.
