# Ten-Reputation Project Architecture

## 1. Concept Overview

Ten-Reputation is a Web3-powered, AI-driven property management platform designed for the Somnia AI Hackathon 2025. It allows landlords to manage rent, utilities, and taxes while building transparent, on-chain tenant reputation scores. Blockchain operations are abstracted from users, with AI agents automating verification, analysis, and reporting.

## 2. Architecture Summary

### a. Frontend Layer

* Built with Scaffold-ETH and React.
* Provides separate views for tenants and landlords.
* Landlord dashboard: manage properties, tenants, and meters; view payments and AI insights.
* Tenant interface: view rent and utility bills, payment history, and receipts.
* Communication via REST or GraphQL APIs to backend.
* Blockchain interactions are abstracted through backend calls.

### b. Backend & AI Agent Layer

* Core logic implemented using Node.js and Python.
* Handles authentication, data management, and external API integrations.
* AI agent submodules:

  * Payment verification agent for M-Pesa, Stripe, PayPal, and Co-op Bank integrations.
  * Image recognition agent using TensorFlow.js or AWS Rekognition to verify utility meter images.
  * Financial summarization agent generating reports and tax estimates.
* Connects to Somnia smart contracts through Somnia SDK or Ethers.js.

### c. Blockchain Layer (Somnia Testnet)

* Smart contracts manage tenant reputation NFTs and payment event logging.
* Contracts handle NFT minting, reputation scoring, and upgrade logic.
* Events emitted from verified payments trigger on-chain updates.
* All blockchain operations handled by backend or AI agents.

### d. Database & Storage Layer

* Somnia DB stores meter images, payment receipts, and reports.
* DynamoDB or MongoDB stores property metadata, user profiles, and analytics data.
* Hash references of stored files are committed on-chain for proof of authenticity.

### e. Payment Integration Layer

* Supports M-Pesa, Co-op Bank, Stripe, and PayPal.
* Payments trigger backend verification logic.
* Webhooks or event listeners forward payment confirmation to AI agent.
* AI agent validates and updates smart contracts accordingly.

### f. Authentication & Abstraction

* Tenants authenticate using email or phone (Web2 login).
* Landlords connect wallets for on-chain interactions.
* Backend abstracts blockchain complexity from tenant-facing features.
* Somnia identity layer used to link wallet and profile data securely.

## 3. Data Flow Description

Tenant makes a rent or utility payment using traditional methods. The backend receives payment confirmation through webhook integration. The AI agent validates the payment details, cross-checks timeliness, and, upon successful verification, triggers the smart contract update to adjust the tenant's reputation NFT. The landlord dashboard reflects the updated payment status and reputation score. Utility and financial data are stored securely in Somnia DB and DynamoDB for analytics and reporting.

Landlords can view property performance, tenant arrears, and tax summaries. AI agents generate insights and highlight anomalies, such as irregular meter readings or recurring late payments.

## 4. Somnia Notes (Dynamic)

### Network Basics

[Placeholder for notes summarizing Somnia network, consensus model, and testnet configuration.]

### Somnia Agents

[Placeholder for how Somnia AI agents function, lifecycle, deployment, and interaction with contracts.]

### Somnia DB

[Placeholder for how data is stored, queried, and verified in Somnia DB.]

### Contracts SDK

[Placeholder for key SDK functions, libraries, and APIs for smart contract interaction.]

### Testnet Setup

[Placeholder for wallet setup, faucet usage, and deployment commands.]

## 5. Development Plan

### Learning Tasks

* Study Solidity basics (ERC721 and soulbound NFTs).
* Learn Somnia SDK and DB integration.
* Review Scaffold-ETH architecture.
* Understand payment API webhook integration.
* Implement AI model for image recognition.

### Week-by-Week Milestones

Week 1: Environment setup, Somnia wallet, and contract skeleton.
Week 2: AI payment verification agent and mock payment integration.
Week 3: Frontend prototype and dashboard design.
Week 4: Testing, demo setup, and documentation.

## 6. Future Enhancements

* Tenant credit scoring API integration for financial institutions.
* Predictive maintenance using AI anomaly detection.
* Automated tax filing integration with government portals.
* DAO layer for verified landlord governance.

## 7. Glossary & References

* Soulbound NFT: Non-transferable NFT used for tenant reputation.
* Somnia Agent: Autonomous entity executing smart contract calls.
* Scaffold-ETH: React-based framework for building Web3 frontends.
* AI Agent: Off-chain logic performing verification and analysis.
* Webhook: Mechanism for external services (e.g., payment APIs) to notify backend systems of events.

## 8. Dual Frontend Strategy

- Two separate frontends will be maintained: one for tenants and one for landlords.
- Both will be scaffolded using Scaffold-ETH (Next.js), then customized for their respective user roles.
- AI prompts and automation will be used to generate and maintain Next.js templates for each frontend, improving development speed and UX.
- This separation allows for tailored user experiences and easier code management.

## 9. Microservices Overview

Recommended microservices:

1. **Auth Service**: Handles login, wallet linking, and profile management.
2. **Payment Verification Service**: Integrates with M-Pesa, Stripe, PayPal, Co-op Bank.
3. **AI Agent Service**: Image recognition, financial summarization, reporting.
4. **Blockchain Service**: Smart contract interactions and event logging.
5. **Data Storage Service**: Manages Somnia DB, DynamoDB/MongoDB, file storage.
6. **Notification/Communication Service**: Alerts, receipts, status updates.

## 10. Folder Structure Suggestions

- `/frontend-tenant/` (Next.js, Scaffold-ETH)
- `/frontend-landlord/` (Next.js, Scaffold-ETH)
- `/services/auth/`
- `/services/payment-verification/`
- `/services/ai-agent/`
- `/services/blockchain/`
- `/services/data-storage/`
- `/services/notification/`
- `/contracts/` (Somnia smart contracts)
- `/docs/` (Documentation)

## 11. AWS Hosting Plan

- Selected microservices (AI agent, data storage, payment verification) may be hosted on AWS for scalability and reliability in later stages of the project lifecycle.
- Blockchain and core Web3 logic will remain decentralized and on-chain.
- This hybrid approach allows leveraging cloud benefits while maintaining Web3 principles.
