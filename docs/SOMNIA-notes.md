# SOMNIA_NOTES.md

**Comprehensive Technical Overview and Research Notes**

---

## 1. Introduction

Somnia is a high-performance blockchain platform designed to enable real-time, large-scale, Web3 applications. Its architecture focuses on scalability, efficient data compression, and decentralized validation while maintaining sufficient decentralization for security and trustlessness.

It merges advanced consensus, streaming-based compression, and aggregate cryptography to support millions of transactions per second, targeting gaming, DeFi, metaverse, and social applications.

---

## 2. Core Principles

Somnia follows these foundational design goals:

Sufficient Decentralization: Balancing decentralization and performance for optimal security and efficiency.
Scalability: Capable of handling hundreds of thousands to millions of TPS through compression and parallelization.
Symmetrical Bandwidth: Validators share equal upload and download loads to prevent bottlenecks.
Deterministic Validation: Uses a secondary verification engine (Cuthbert) for cross-node consistency.
Composability: Enables fully interoperable on-chain applications such as games, DeFi systems, and social networks.

---

## 3. Advanced Compression Techniques

### 3.1 The Problem

A standard ERC-20 transaction is about 200 bytes. At 1M transactions per second, this equals 190 MB/s (1.5 Gbps). This load cannot be supported by a global decentralized network without optimization.

### 3.2 Power-Law Distribution

Blockchain usage follows a power-law: a small number of contracts dominate activity. This allows compression since repeated contract addresses or functions can be encoded with fewer bits. For instance, a contract appearing in 10% of transactions can be encoded in 3.3 bits instead of 20 bytes.

### 3.3 Streaming Compression vs. Block Compression

Block compression compresses each block independently (e.g., ZIP). It’s simple but less efficient.
Streaming compression builds a shared history between sender and receiver, enabling references to prior data. This achieves superior compression but requires a continuous data stream.

Somnia solves this by giving each validator its own data chain, enabling continuous streaming compression.

---

## 4. Signatures and Hash Handling

### 4.1 Hashes

Hashes change completely with minor input differences and cannot be compressed. Somnia avoids sending hashes by letting nodes recalculate them.

### 4.2 BLS Signature Aggregation

Somnia uses BLS (Boneh–Lynn–Shacham) signatures to aggregate many signatures into one. This drastically reduces bandwidth and verification cost, allowing entire transaction batches to be verified as cheaply as one.

---

## 5. Bandwidth Symmetry Model

In typical blockchains, the block proposer must broadcast the block to all peers, creating an upload bottleneck.

Somnia distributes this load equally. Each validator publishes its own stream of data, sharing upload and download responsibilities evenly. This symmetrical model allows the network to scale up to the bandwidth limits of participating peers.

---

## 6. Consensus and Data Availability

Somnia’s consensus and data availability model supports parallel validator chains:

Each validator maintains a local chain for transaction streaming.
Validators publish cryptographic commitments to the main chain for synchronization.
Global consistency is maintained while supporting real-time, high-throughput processing.

---

## 7. Security and Redundancy

### 7.1 Sufficient Decentralization

Somnia targets node specs between Solana and Aptos validators. Around 100 validators will start globally distributed, expanding as the network matures.

### 7.2 Cuthbert Reference Implementation

A second implementation, Cuthbert, runs alongside the main client. Validators verify each transaction on both systems, halting consensus on any divergence. This ensures consensus integrity and rapid bug detection.

### 7.3 Proof of Stake

Validators stake SOMI tokens to participate. Misbehavior leads to slashing, ensuring network honesty.

---

## 8. Tokenomics Overview (SOMI Token)

### 8.1 Total Supply

1,000,000,000 SOMI tokens.

### 8.2 Token Utility

Staking: Required for validators and delegators.
Gas Payments: All transactions use SOMI for gas.
Governance: Token holders vote on proposals and allocations.

### 8.3 Staking and Delegation

Validators must stake 5,000,000 SOMI. Token holders can delegate to validators for shared rewards.

Reward formula:

```
epoch_rewards × delegation_rate × staking_ratio
```

Unstaking takes 28 days, or immediate withdrawal with a 50% penalty.

---

## 9. Gas and Fee Model

### 9.1 Base Formula

```
Total Fee = Gas Usage × Gas Unit Price
```

### 9.2 Components

Base gas: 21,000 (minimum).
Data cost: 160 gas per 32 bytes.
Opcode cost: Dynamic, per operation.

### 9.3 Dynamic Pricing

Base price: $0.00000000616 per gas unit.
Minimum: $0.000000000616 (at 400 TPS).
Up to 90% gas discounts for high-throughput dApps.

### 9.4 Storage Fees

Transient storage: Cheaper, temporary.
Permanent storage: Higher cost, long-term.
Prices scale by duration (1 hour → indefinite).

---

## 10. Fee Distribution

50% of gas fees are distributed to validators.
50% are burned, creating a deflationary token model.

---

## 11. Governance Framework

Somnia’s governance evolves through three stages: Bootstrap, Transition, Mature.

### 11.1 Governance Bodies

Token House: Token holders voting on funding and proposals.
Validator Council: Controls upgrades and gas parameters.
Developer Council: Oversees technical roadmap.
User Assembly: Provides community checks and balances.
Foundation Board: Manages treasury and emergency overrides.

### 11.2 Governance Roadmap

Bootstrap (0–6 months): Foundation control.
Transition (6–24 months): Shared decision-making.
Mature (>2 years): Fully decentralized, with emergency safeguards.

---

## 12. Validator Rewards and Token Allocation

| Allocation      | %      | Tokens      | Cliff | Vesting |
| --------------- | ------ | ----------- | ----- | ------- |
| Team            | 11     | 110,000,000 | 12 mo | 48 mo   |
| Launch Partners | 15     | 150,000,000 | 12 mo | 48 mo   |
| Investors       | 15.15  | 151,500,000 | 12 mo | 36 mo   |
| Advisors        | 3.58   | 35,800,000  | 12 mo | 36 mo   |
| Ecosystem       | 27.345 | 273,450,000 | 0     | 48 mo   |
| Community       | 27.925 | 279,250,000 | 0     | 36 mo   |

Initial unlock: 16.02% at TGE.

---

## 13. Use Cases

Gaming: Fully on-chain, modifiable games.
SocialFi: On-chain social platforms with portable identities.
Metaverse: Interoperable virtual worlds.
DeFi: Fully on-chain order books with transparency.
Real-Time Apps: Sub-second finality for mass-scale consumer apps.

---

## 14. Legal and Regulatory Notes

Somnia and SOMI are utility-based, not investment assets.
No guarantee of profit or liquidity.
Tokens cannot be sold to residents of the US, Canada, or China.
Documentation is informational only, not legally binding.

---

## 15. Vision and Conclusion

Somnia continues Ethereum’s world computer vision — scalable, composable, and open computing for all. It merges Web2 scalability with Web3 ownership, using breakthroughs in compression, consensus, and streaming to enable large-scale, real-time decentralized applications.

---

## Appendix: Ten-Reputation Integration Notes

Ten-Reputation can leverage Somnia’s technology as follows:

Use data chains for efficient streaming of rental payment logs.
Compress tenant transaction data using Somnia’s power-law compression.
Use BLS aggregation for secure rent verification batches.
Integrate AI analysis for real-time financial summaries over validator data shards.
Utilize SOMI for validator staking, payment settlement, or NFT issuance logic.

This combination provides a scalable, verifiable, and secure backbone for tenant reputation, payment history, and AI-powered analytics in your dApp.

### addendum

## What is Somnia?

Somnia is an EVM-compatible Layer 1 blockchain designed to support real-time, high-volume decentralised applications such as games, social platforms and metaverse environments. It achieves high throughput through technical innovations including compiled EVM bytecode, a custom database (IceDB), and a MultiStream consensus mechanism, enabling over 1,000,000 transactions per second (TPS) with sub-second finality.

Unlike other EVM chains that use traditional consensus structures, Somnia’s architecture separates data generation and consensus. Validators each maintain their own "data chain", while a central "consensus chain" aggregates and finalises the state. This structure allows for increased scalability and the use of streaming compression and BLS signature aggregation, reducing bandwidth and improving efficiency.

Somnia also introduces a custom gas model that reflects the real computational and storage costs of transactions, incorporating dynamic discounts and a dual-fee system where 50% of gas fees are burnt and 50% are distributed to validators.

Initial use cases include gaming, metaverse applications, DeFi infrastructures, and fully on-chain social platforms. The platform is designed to extend to any application requiring high-speed, decentralised infrastructure.
What is Somnia (SOMI) token used for?

SOMI is the native utility and staking token of the Somnia blockchain. It is used for the following functions:

    Gas Fees: All transactions and smart contract operations on the network are paid for using SOMI tokens.
    Staking: Validators are required to stake 5 million SOMI to participate in consensus. Token holders can also delegate tokens to validators in return for a portion of validator rewards.
    Governance: SOMI will be used in the governance framework to inform decisions related to fund allocations, protocol upgrades and network direction. Governance features will expand over time through a three-phase decentralisation roadmap: Bootstrap, Transition and Mature phases.
    Delegated Staking: Token holders can delegate their SOMI to validator-specific or general pools. Depending on the validator’s configuration, token holders may earn a share of gas fee rewards.
    Network Security: The delegated proof-of-stake (dPoS) mechanism relies on SOMI to secure the network. Misbehaving validators are subject to slashing.

SOMI is also required to participate in infrastructure development, resource allocation and incentive distribution across the ecosystem.

Interoperability with other blockchains is enabled through omnichain deployments and bridging via LayerZero’s Stargate.
Who created Somnia (SOMI)?

Somnia was founded by Paul Thomas, who also serves as the CEO. He leads the project’s mission to build a virtual society powered by blockchain infrastructure.

The development of the blockchain is supported by Improbable, a technology company focused on networked virtual experiences, and MSquared, a metaverse initiative also backed by Improbable. These organisations contribute to the technical architecture and core components of the Somnia network.

The token (SOMI) is issued by Somnia Token Co Ltd, and the broader ecosystem is coordinated by a Cayman Islands-based Foundation, with governance transitioning over time to a decentralised structure. The project’s governance includes a Board of Directors, a legal Supervisor and regulatory oversight, alongside the development of a community-driven governance system.

Somnia includes a secondary implementation called Cuthbert—a non-optimised, independent system used to cross-check the main client and enhance security.
