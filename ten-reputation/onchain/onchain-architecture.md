On-Chain Architecture
Overview

The Ten-Reputation blockchain layer powers transparent, decentralized reputation tracking for both tenants and landlords. It leverages Somnia’s testnet, with smart contracts written in Solidity and deployed via Foundry. All blockchain operations are abstracted from end users — only verified data from backend and AI agents interacts with the chain.

Core Principles

Transparency: Reputation and payment history are verifiable on-chain.

Mutual Trust: Both tenants and landlords have reputation profiles.

Automation: AI agents trigger on-chain updates from verified off-chain events.

Abstraction: Users never directly interact with wallets or contracts.

Core Contracts

1. ReputationNFT.sol - Minted to each user (tenant or landlord) upon first interaction.
2. ReputationManager.sol - Central logic for updating and querying reputations.
3. PaymentRegistry.sol - Logs verified payment events from AI agents.
4. LeaseRegistry.sol (Future Expansion) - Tracks relationships between landlords and tenants.


Reputation Model

Each user has an on-chain profile:
struct ReputationProfile {
    bool isLandlord;
    uint8 score; // 0–10 rating
    uint256 lastUpdate;
}
cores evolve automatically based on payment timeliness, verified maintenance, and AI analysis.

Event Flow

Tenant makes a verified payment (off-chain API).
AI Agent confirms and emits on-chain PaymentVerified.
ReputationManager updates tenant’s NFT reputation.
Landlord’s reputation may also increase based on property management consistency.

Both reputations are viewable via getReputation(address).

Integration Points

1. Somnia SDK / Ethers.js for contract interaction.

2. AI Agent triggers updates using a secure wallet or service key.

3.  Backend mirrors key data in Somnia DB for reports and analytics.

Next Steps

Prototype contracts in Foundry test environment.

Connect to Somnia testnet for deployment.

Write basic tests for minting, updating, and viewing reputation.

Integrate with backend payment verification service.