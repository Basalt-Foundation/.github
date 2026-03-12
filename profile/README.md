# Basalt Foundation

High-performance Layer 1 blockchain built on .NET 9 with Native AOT compilation.

## Key Numbers

| | |
|---|---|
| **~2,000 TPS** | Throughput on 4-validator devnet |
| **4000ms** | Deterministic finality (BasaltBFT) |
| **2,891 tests** | Across 16 test projects, 0 failures |
| **43 projects** | Mono-repo: core, SDK, explorer, DEX, bridge |

## Architecture

Seven independent layers — each production-hardened and fully tested:

| Layer | Components |
|-------|------------|
| **Cryptography** | BLAKE3, Ed25519, BLS12-381, Keccak-256, Groth16 |
| **Consensus** | BasaltBFT, pipelined 3-phase commit, BLS aggregation, stake-weighted leader selection, slashing |
| **Execution** | BasaltVM, C# Native AOT, sandboxed contracts, gas metering, Caldera Fusion DEX |
| **Storage** | Merkle Patricia Trie, RocksDB, Flat State DB (O(1) cache), Sparse Merkle Tree |
| **Network** | TCP transport, Kademlia DHT, Episub gossip, peer reputation |
| **Compliance** | ZK-first (Groth16 proofs), attestation fallback, SchemaRegistry, IssuerRegistry, audit trail |
| **Confidentiality** | Pedersen commitments, Groth16 range proofs, X25519 private channels, selective disclosure |

## What Makes Basalt Different

- **ZK Compliance** — Transactions carry ephemeral Groth16 proofs. Validators verify compliance in constant time. Nothing is stored on-chain.
- **C# Smart Contracts** — Write contracts in idiomatic C# with `StorageMap`, `StorageValue`, and `StorageList`. 12 Roslyn analyzers catch reentrancy, overflows, non-determinism, and missing policy enforcement at compile time.
- **Policy Hooks** — Modular transfer policy enforcement on all token standards: sanctions screening, holding limits, lockup periods, jurisdiction whitelist/blacklist. Deploy policies as independent contracts, register on any token.
- **Caldera Fusion DEX** — Protocol-native hybrid AMM + order book exchange with batch auction settlement, concentrated liquidity, encrypted intents, dynamic fees, TWAP oracle, solver network, and MEV elimination.
- **Confidential Transactions** — Pedersen commitments on BLS12-381 hide amounts while proving balance validity. 192-byte range proofs verified in ~5ms.
- **EVM Bridge** — Bidirectional bridge to Ethereum and Polygon with M-of-N Ed25519 multisig relayer and Merkle proof verification.
- **Token Standards** — BST-20 (fungible), BST-721 (NFT), BST-1155 (multi-token), BST-3525 (SFT), BST-4626 (vault), BST-DID (W3C DID), BST-VC (verifiable credentials). All standards support composable policy hooks.
- **EIP-1559 Fees** — Dynamic base fee with proposer tips and base fee burn.
- **On-Chain Governance** — Stake-weighted quadratic voting, single-hop delegation, timelock, executable proposals.

## Repositories

| Repository | Description |
|------------|-------------|
| [basalt](https://github.com/Basalt-Foundation/basalt) | Core blockchain — consensus, networking, execution, storage, compliance, confidentiality, APIs, SDK, explorer, and tools |
| [basalt-docs](https://github.com/Basalt-Foundation/basalt-docs) | Technical documentation and specifications |
| [basalt-contracts](https://github.com/Basalt-Foundation/basalt-contracts) | Solidity bridge contracts for EVM interoperability |
| [basalt-website](https://basalt.foundation) | Marketing website ([basalt.foundation](https://basalt.foundation/)) |

## Quick Start

```bash
# Clone and build
git clone https://github.com/Basalt-Foundation/basalt.git
cd basalt
dotnet build

# Run tests (2,891 tests)
dotnet test

# Start a local 4-validator devnet
docker compose up --build
```

## License

All repositories are licensed under [Apache License 2.0](https://github.com/Basalt-Foundation/basalt/blob/main/LICENSE).
