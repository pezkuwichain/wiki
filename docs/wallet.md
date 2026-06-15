# Pezkuwi Wallet

**Pezkuwi Wallet** is the official mobile wallet (Android, on Google Play). It is
a non-custodial wallet — **you** hold the keys — built for the PezkuwiChain
multi-chain world.

## What it does

- Create or import accounts from a secret recovery phrase
- Hold **HEZ**, **PEZ**, and **PEZ-20** assets (e.g. USDT on Asset Hub)
- Send and receive across the **relay chain**, **Asset Hub**, and **People Chain**
- View balances live from the chain
- Connect to dApps via WalletConnect

## First-time setup

1. Install **Pezkuwi Wallet** from Google Play.
2. Choose **Create wallet** (new) or **Import** (existing phrase).
3. If creating new, **write down your recovery phrase offline** and confirm it.
4. Set a device PIN / biometric lock.

!!! danger "Your recovery phrase is everything"
    The 12/24-word phrase controls all your funds on every chain. Store it
    offline, never photograph it into cloud storage, and never enter it on any
    website. No one legitimate will ever ask for it.

## Sending tokens — pick the right chain

A token exists **on a specific chain**. When sending:

- HEZ on the **relay chain** → recipient receives on the relay chain,
- a PEZ-20 asset (e.g. USDT) on **Asset Hub** → recipient receives on Asset Hub.

The same address is used across chains, but the **balance is per chain**. If a
transfer "doesn't arrive," the usual cause is sending on a different chain than
expected, or sending to a node that wasn't fully synced — verify the chain and the
recipient address.

## Tips

- Keep a little **HEZ** for fees, even when mainly holding PEZ-20 assets.
- Double-check the **first and last characters** of any address you paste.
- For large amounts, send a small **test transfer** first.
