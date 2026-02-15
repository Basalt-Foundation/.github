# Basalt Foundation

High-performance Layer 1 blockchain built on .NET 9 with Native AOT compilation.

## Architecture

Basalt combines institutional-grade compliance with cutting-edge blockchain technology:

- **BFT Consensus** — Byzantine fault-tolerant protocol with pipelined block finalization
- **Native AOT** — Ahead-of-time compiled for bare-metal performance
- **BLS12-381 + Ed25519** — Dual cryptographic scheme for signatures and aggregate consensus
- **Merkle Patricia Trie** — Ethereum-compatible state storage with cryptographic proofs
- **Smart Contracts** — .NET-based contract SDK with Roslyn analyzers for safety guarantees
- **Built-in Compliance** — Identity, KYC, and sanctions screening at the protocol level
- **Zero-Knowledge Privacy** — Pedersen commitments, Groth16 proofs, and encrypted channels
- **EVM Bridge** — Cross-chain interoperability with Ethereum and EVM-compatible networks

## Repositories

| Repository | Description |
|------------|-------------|
| [basalt](https://github.com/Basalt-Foundation/basalt) | Core blockchain — consensus, networking, execution, APIs, SDK, explorer, and tools |
| [basalt-docs](https://github.com/Basalt-Foundation/basalt-docs) | Technical documentation and specifications |
| [basalt-contracts](https://github.com/Basalt-Foundation/basalt-contracts) | Solidity bridge contracts for EVM interoperability |

## Quick Start

```bash
# Clone and build
git clone https://github.com/Basalt-Foundation/basalt.git
cd basalt
dotnet build

# Run tests (1,380+ tests)
dotnet test

# Start a local 4-validator devnet
docker compose up --build
```

## License

All repositories are licensed under [Apache License 2.0](https://github.com/Basalt-Foundation/basalt/blob/main/LICENSE).
