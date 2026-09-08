# FAQ

### What is the difference between HEZ and PEZ?

**HEZ** is the native **gas and security** token — you pay fees with it and it is
staked to secure the network. **PEZ** is the **governance** token used for voting
and the treasury. See [Tokens & Standards](tokens.md).

### Is PEZ-20 a smart contract, like an ERC-20?

No. PezkuwiChain Asset Hub has **no EVM or smart-contract layer**. A PEZ-20 token
is a **runtime-native asset** with an on-chain numeric ID, not a deployed
contract. It behaves like an ERC-20 conceptually but is cheaper, faster, and can't
be bricked by buggy contract code.

### Why does USDT show "PEZ-20"?

It tells you the **network the token lives on** — Pezkuwi Asset Hub — exactly like
"USDT TRC-20" (Tron) or "USDT ERC-20" (Ethereum). Same token, different network.

### I sent tokens and they didn't arrive. What happened?

The most common causes:

1. **Wrong chain** — the token was sent on a different chain than the recipient
   expected (e.g. relay vs Asset Hub). Balances are tracked per chain.
2. **The transaction never entered a block** — e.g. submitted to a node that was
   not fully synced. In that case the funds were never actually spent; check the
   sending account on a synced node/explorer.

Always verify the **chain** and the **full recipient address**, and send a small
test transfer first for large amounts.

### Where do I stake / nominate?

On **Asset Hub** (`wss://asset-hub-rpc.pezkuwichain.io`) — where it has been since
genesis, not after a migration. See [Staking](staking.md).

### How do I vote on proposals?

Through the governance app at **[app.pezkuwichain.io](https://app.pezkuwichain.io/)**,
backed by the Welati governance pallet. See [Governance](governance.md).

### Is PEX really fee-free?

PEX is run **non-profit / cost-recovery**: **0% maker, ~0.01% taker**. Fees exist
only to cover operating costs, not to make a profit.

### Which libraries do I use to build on PezkuwiChain?

The sovereign **`@pezkuwi/*`** packages (the equivalent of `@polkadot/*`). The
full reference is in the [SDK docs](https://docs.pezkuwichain.io/).

### Who can edit this wiki?

Anyone — via the ✏️ edit button, which opens a pull request on the
[`pezkuwichain/wiki`](https://github.com/pezkuwichain/wiki) repository. Changes are
reviewed before going live.
