# Ten-Reputation

Ten-Reputation is a Web3-powered, AI-driven property management platform developed for the Somnia AI Hackathon 2025. It enables landlords to manage tenants, rent, utilities, and taxes with automation and transparency, while tenants build on-chain reputation scores without directly interacting with blockchain systems.

## Table of Contents

- [Overview](#overview)
- [Problem](#problem)
- [Solution](#solution)
- [Features](#features)
- [AI Agent Functions](#ai-agent-functions)
- [Blockchain Layer](#blockchain-layer)
- [Frontend](#frontend)
- [Backend and AI Infrastructure](#backend-and-ai-infrastructure)
- [Demonstration Flow](#demonstration-flow)
- [Hackathon Relevance](#hackathon-relevance)
- [Tech Stack](#tech-stack)
- [Future Extensions](#future-extensions)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

## Overview

The system brings trust and efficiency to rental management by combining artificial intelligence, blockchain, and real-world payment integrations. It allows landlords to handle buildings and tenants in one place, automatically verify rent and utility payments, and generate reputation NFTs for tenants. The AI agent verifies payment and meter data, stores records securely, and updates tenant reputation scores transparently on the Somnia network.

## Problem

Landlords often track rent and utilities manually using spreadsheets or chat apps, leading to disputes and data loss. Tenants have no reliable way to prove their payment history or credibility. Financial summaries and tax calculations are also tedious and error-prone.

## Solution

Ten-Reputation provides an AI-enhanced system that automates these processes. Landlords can register buildings, tenants, and utility meters. Payments through familiar methods such as M-Pesa, Co-op Bank, PayPal, or Stripe are verified by an AI agent. The agent checks timeliness and accuracy, reads meter images, and updates tenant payment records. Tenant reliability is represented by non-transferable NFTs stored on the Somnia blockchain. Landlords can view these reputation scores when evaluating new tenants.

## Features

- Tenants view rent and utility balances, payment due dates, and pay through normal channels.
- Landlords manage buildings, units, tenants, and utility meters from a single dashboard.
- AI agents read meter images, verify payments, detect anomalies, and generate financial summaries.
- Somnia DB stores meter images, payment proofs, and tax-related documents. Hashes of stored data are linked on-chain for verification.
- Tenant reputation NFTs automatically update after every verified payment.
- Landlords can view tenant payment status, arrears, and generate tax and income reports.

## AI Agent Functions

- Meter recognition and authenticity checks.
- Payment verification through connected APIs.
- Smart contract interaction for NFT updates.
- Automated reporting and analytics generation.

## Blockchain Layer

The smart contract on Somnia Testnet manages NFT minting, reputation updates, and event logging.
Tenants are abstracted from blockchain complexity; all interactions are handled through backend automation.
Reputation NFTs are soulbound and publicly visible to other landlords through the Somnia explorer.

## Frontend

- Developed using Scaffold-ETH and React.
- Tenant interface provides rent details and payment status.
- Landlord interface provides management tools, dashboards, and financial analytics.
- The design keeps blockchain details invisible to users while ensuring transparent, verifiable data in the background.

## Backend and AI Infrastructure

- Payment integration through Node.js and AWS Lambda.
- AI image recognition using TensorFlow.js or AWS Rekognition.
- Data storage and AI processing with Somnia DB.
- Notifications via AWS SNS or Twilio.
- Blockchain interaction handled through Ethers.js and the Somnia SDK.

## Demonstration Flow

1. The landlord logs in, registers a property, and adds tenants and meters.
2. The AI agent verifies meter image authenticity and listens for payment events.
3. When a payment is confirmed, the AI agent updates the smart contract, logs the transaction, and adjusts the tenant’s NFT reputation score.
4. The landlord views tenant payment status, arrears, and monthly summaries.
5. The updated reputation NFT is visible on the Somnia network for transparency.

## Hackathon Relevance

Ten-Reputation demonstrates how AI agents can operate autonomously to verify off-chain actions and interact with blockchain contracts. It aligns with the Somnia hackathon goals of combining AI, automation, and decentralized systems in a practical real-world use case.

## Tech Stack

- **Smart contracts:** Solidity, Hardhat, Somnia Testnet
- **Frontend:** Scaffold-ETH, React, Tailwind
- **AI and backend:** Node.js, Python, TensorFlow.js, AWS Rekognition
- **Storage:** Somnia DB, IPFS backup
- **Payments:** M-Pesa, Co-op Bank, Stripe, PayPal
- **Database:** DynamoDB or MongoDB
- **Wallet abstraction:** Somnia wallet
- **Development tools:** Git, VS Code, Remix IDE

## Future Extensions

- Tenant credit scoring API for financial institutions.
- Predictive analytics for meter anomaly detection.
- Automated landlord tax filing.
- Formation of decentralized landlord networks for verified trust and data sharing.
- Prototype DEMO landlord frontend for property and tenant management.  - authentication email:sonson@gwag.com password:blunrenpawn

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

- npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Ten-Reputation.git
   ```
2. Install NPM packages
   ```sh
   npm install
   ```

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m '''Add some AmazingFeature'''`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE.md` for more information.