# The chains

PezkuwiChain is a relay chain with system chains attached to it. The relay provides
shared security and finality; each system chain carries one function and nothing
else. This is not a scaling decision — it is a **separation-of-powers decision
expressed as topology**: the chain that holds the register is not the chain that
holds the money, and neither is the chain that produces blocks.

| Chain | Para id | Carries |
|---|---|---|
| **Pezkuwichain** (relay) | — | Consensus, finality, the validator session, cross-chain routing, the HEZ escrow |
| **Asset Hub** | 1000 | Every fund. PEZ, wHEZ, wUSDT. Staking and validator elections. |
| **People** | 1004 | The citizen register, every office, the courts, trust, the validator pool |
| **Bridge Hub** | 1002 | Bridges to other consensus systems, including Ethereum |
| **Coretime** | 1005 | Blockspace allocation |

The relay schedules exactly **two cores** at genesis — one for the Asset Hub and one
for People, the two chains a state cannot run without.

## Zagros

**Zagros** is the staging network: the same runtimes at an earlier stage, used to
validate a release before mainnet carries it. It adds two chains mainnet does not
have — a **Collectives** chain (1001) and a **Glutton** load-test chain (1300) — and
its Asset Hub carries development pallets that mainnet's does not.

## The one door into the relay's root

The relay has **no `root` governance track**. Root arrives from exactly one place: a
message from the People chain, carried as a superuser instruction, converted by a
single origin converter that matches that chain's identifier and nothing else.

The consensus layer is subordinate to the civil layer, structurally, and no amount of
stake on the relay can reverse the direction.

## Cross-chain movement

HEZ **teleports** between the relay and its system chains — the relay holds what
leaves rather than burning it, so the Asset Hub's balance is a mirror rather than new
supply. Bridged and foreign assets move by **reserve transfer**. PEZ, wHEZ and wUSDT
are local assets of the Asset Hub and do not leave it by either route.

See also **[Architecture](architecture.md)**, **[Treasuries](treasuries.md)** and the
**[whitepaper](https://pezkuwichain.io/whitepaper)**.
