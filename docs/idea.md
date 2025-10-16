🏠 Ten-Reputation

(Tenant reputation out of ten — trust made transparent)

💡 Core Concept

Ten-Reputation is a Web3-powered, AI-driven landlord management platform that brings transparency, automation, and trust to rental property operations.

It allows landlords to manage rent, utilities, and taxes in one place, while AI agents autonomously validate payments, verify meter readings, and update on-chain tenant reputation NFTs — abstracting blockchain complexity away from users entirely.

🧩 Problem

Landlords manually track rent and utility usage (water, electricity, Wi-Fi) with spreadsheets or WhatsApp confirmations.

Payment delays and disputes are common.

Tenants have no digital way to prove reliability when moving between properties.

Landlords lack automated tools for financial summaries or tax reporting.

⚙️ Solution

Ten-Reputation creates an intelligent, transparent system where:

Landlords/admins manage buildings, tenants, and utility meters through a unified dashboard.

AI agents verify payments, interpret meter images, and automatically log data on-chain.

Tenants simply pay rent and utilities through familiar channels (M-Pesa, Co-op Bank, PayPal, Stripe) — no crypto or wallet interaction required.

Each tenant’s reliability is represented by a non-transferable reputation NFT (soulbound) viewable by current and future landlords.

👥 User Roles
Tenant

Sees rent and utility bills (values sent by landlord).

Pays via standard channels — no blockchain exposure.

Builds on-chain reputation NFT passively.

Landlord / Admin

Creates and manages buildings, tenants, and utility meters.

CRUD operations for meters (water, power, internet, etc.).

Receives and verifies payments.

Views tenant status: Paid / Unpaid / Arrears + Reputation score.

Generates monthly summaries, tax estimates, and AI insights from Somnia DB data.

🤖 AI Agent Roles

Meter & Image Recognition

Reads and authenticates images of water, electricity, and other meters uploaded by the landlord/admin.

Detects tampering or low-quality images.

Payment Verification

Listens to payment webhooks (M-Pesa, Co-op Bank, PayPal, Stripe).

Checks timeliness and accuracy.

Updates tenant payment status.

Smart Contract Interaction

Calls Somnia contract functions to log verified payments.

Automatically upgrades tenant reputation NFT (e.g., 7 → 8).

Analytics & Reporting

Generates AI-driven summaries: income trends, unpaid tenants, tax insights.

Detects anomalies (e.g., recurring late payments, sharp utility spikes).

🔗 Blockchain Layer (Somnia Testnet)

Smart Contract Handles:

Minting and managing soulbound NFTs representing tenant reliability.

Logging payment verification events (from AI Agent).

Updating NFT metadata with cumulative scores.

Publicly viewable tenant reputation (abstracted from tenants).

Design:

Tenants don’t interact with blockchain directly — all interactions happen through backend or agent calls.

Landlords can query verified tenant scores through Somnia or the dApp.

🗄️ Somnia DB Integration

Stores:

Meter images, proof of readings.

Payment receipts, financial documents.

Landlord financial/tax data (summaries, reports).

Hashes of stored files are linked on-chain for proof of authenticity.

Enables AI model training and analytics queries on verified data.

💻 Frontend (dApp)

Built with: Scaffold-ETH + React + Tailwind

Tenant View (Simplified):

Login with phone/email (no wallet).

See rent + utility balances, due dates, and payment status.

Pay through embedded M-Pesa or Stripe interface.

Landlord Dashboard:

Manage buildings, units, tenants, and meters.

View payment statuses (paid/unpaid/arrears).

See each tenant’s Ten-Reputation Score (1–10).

View AI summaries (income, tax, anomalies).

Access attached meter images + readings.

Export or print reports.

Abstraction Layer:
All blockchain calls handled by backend; the UI feels fully Web2.

☁️ Backend / AI Infrastructure
Function Tool / Service
Payment API Integration Node.js · AWS Lambda
AI Agent Python / TensorFlow.js / AWS Rekognition
Storage Somnia DB (images, docs)
Notifications AWS SNS / Twilio
Reports DynamoDB / MongoDB + AI Summaries
Blockchain Interaction Ethers.js · Somnia SDK

🔥 Demo Flow (Hackathon MVP)

Landlord: Logs in → Registers property → Adds tenants + meter images.

AI Agent:

Verifies image authenticity + reads meter values.

Waits for payment events from M-Pesa or Stripe mock API.

Upon Payment Verification:

AI Agent calls smart contract → logs payment + updates NFT reputation.

Landlord Dashboard:

Sees tenant’s payment status (Paid/Unpaid/Arrears).

Views new tenant score (e.g., 7 → 8).

Generates AI financial/tax report.

On Somnia Explorer:

Tenant’s reputation NFT updated — visible to other landlords.

🧠 Hackathon Fit

✅ AI Agent autonomy (image verification + analytics).
✅ On-chain logic (NFT reputation system).
✅ Somnia DB utilization (off-chain storage + proof linking).
✅ Practical and high-impact — fits Open Track or DeFi Agent Track.
✅ Abstracted UX — no crypto friction for end users.

🧰 Tech Stack
Layer Tools
Smart Contracts Solidity · Scaffold-ETH · Somnia Testnet
Frontend Scaffold-ETH · React · Tailwind
AI / Backend Node.js · Python · TensorFlow.js · AWS Rekognition
Storage Somnia DB · IPFS backup
Payments M-Pesa · Co-op Bank · Stripe · PayPal
Reports / DB DynamoDB · MongoDB
Wallets (abstracted) Somnia Wallet (backend only)
Version Control Git · VS Code · Remix IDE


-tenants can view reputation of landlord before renting
-landlords can view reputation of tenant before renting