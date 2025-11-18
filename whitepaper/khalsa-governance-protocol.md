# Khalsa Governance Protocol (KGP)
### A Decentralised Governance and Seva Infrastructure for the Global Sikh Panth  
**Version:** v1.0  
**Published:** 2025  

---

## Table of Contents

1. Abstract  
2. Introduction  
3. Problem Statement  
4. Design Principles  
5. System Architecture Overview  
6. KHL Token Model  
7. Identity Framework (Khalsa ID)  
8. Governance Protocol  
9. Treasury Architecture  
10. Smart Contract Architecture  
11. Risk Analysis  
12. Ethical & Panthic Alignment  
13. Roadmap  
14. Conclusion  
15. Appendix  
16. Disclaimer  
17. References  

---

# 1. Abstract

The **Khalsa Governance Protocol (KGP)** is a decentralised governance and seva coordination framework designed to empower the global Sikh Panth through transparent, secure, and identity-verified collective decision-making. KGP integrates Sikh ethical principles — *sarbat da bhala*, *seva*, *nimrata*, equality, and accountability — with modern blockchain architecture anchored in Ethereum security.

KGP introduces two core primitives:

1. **KHL Token (non-transferable ERC-20-style)**  
   A fixed-supply, non-transferable governance access token minted exclusively on Arbitrum L2 at a fixed price of 10 USDT. Holding ≥1 KHL grants governance access; additional KHL does not increase voting power.

2. **Khalsa ID (ERC-1155 Soulbound Token)**  
   A cryptographic Sikh identity credential issued by authorised Gurdwaras or Sikh institutions. Required for participating in Panthic governance.

Execution is enforced through a dual-safe architecture:

- **L1 Governance Safe (Panj Pyare Multisig):**  
  Root configuration authority, max supply, and L2 contract authorisation.

- **L2 Governance Safe:**  
  Executes governance-approved actions such as treasury spending, whitelist updates, issuer management, and contract upgrades.

- **L2 Seva Treasury Safe:**  
  Holds stablecoins from KHL purchases and releases funds only after governance approval.

KGP does not replace Sikh institutions.  
It strengthens them by providing transparent, non-political, Panthically aligned digital infrastructure for accountability and seva coordination.

---

# 2. Introduction

The Sikh Panth has a long tradition of decentralised governance rooted in Sangat, Panthic consensus, and shared seva. Yet in the modern era, governance is fragmented, seva transparency varies across Gurdwaras, and no global digital infrastructure exists for verified Sikh participation.

The **Khalsa Governance Protocol (KGP)** addresses these gaps by providing an identity-gated, transparent, decentralised governance system that any Sikh institution can adopt.

KGP is not a political movement.  
It is **open-source infrastructure** that supports global Sikh communities.

---

# 3. Problem Statement

## 3.1 Governance Fragmentation
Thousands of Gurdwaras operate independently, without shared digital governance standards.

## 3.2 Absence of Digital Identity
There is no cryptographic way to verify Sikh identity online without exposing personal data.

## 3.3 Lack of Transparent Seva Funding
Financial flows are difficult to track, creating inefficiencies and mistrust.

## 3.4 Trust Deficit & Political Capture
Factionalism, opaque accounting, and lack of accountability structures weaken institutions.

## 3.5 No Global Panthic Infrastructure
The diaspora lacks unified digital coordination tools for seva and decision-making.

---

# 4. Design Principles

## 4.1 Sarbat da Bhala
Infrastructure must promote universal welfare.

## 4.2 Seva-Centric Economics
The treasury supports seva, not profit.

## 4.3 Decentralisation & Byzantine Safety
Power is distributed via multi-signature safes.

## 4.4 Identity-Based Governance
Khalsa ID ensures authentic Sikh participation.

## 4.5 Transparency & Auditability
All treasury and governance actions are verifiable.

## 4.6 Non-Speculation
KHL is non-transferable, fixed-price, and cannot be traded.

## 4.7 Minimal Trust
Contracts enforce rules; humans do not need to be trusted.

## 4.8 Evolution With the Sangat
KGP evolves through governance.

---

# 5. System Architecture Overview

KGP combines four subsystems:

1. **KHL Token Layer**  
2. **Identity Layer (Khalsa ID)**  
3. **Governance Layer (Snapshot → ZK-MACI)**  
4. **Treasury Layer (Seva Treasury Safe)**

Two-layer security model:

- **Ethereum L1:** Root-of-truth, Panj Pyare multisig.  
- **Arbitrum L2:** All operational logic.

---

## 5.1 High-Level Architecture Diagram

![System Architecture](diagrams/system-architecture.svg)

---

## 5.2 Architectural Rationale

### L1 (Ethereum)
- Max supply of KHL  
- Authorisation of L2 contracts  
- Migration & emergency capabilities  
- Controlled by Panj Pyare multisig

### L2 (Arbitrum)
- All minting  
- Governance execution  
- Identity issuance  
- Treasury operations  
- Low gas costs for Sangat

---

## 5.3 Execution Flow Overview

### KHL Distribution
- Buy-Only Contract mints non-transferable KHL  
- Buyer must be whitelisted  
- Funds → Seva Treasury Safe  
- MAX_SUPPLY enforced by L1

### Identity Verification
- Off-chain verification  
- On-chain SBT (Khalsa ID)

### Governance
- Eligibility varies by proposal type:
  - Panthic: Khalsa ID + ≥1 KHL  
  - Technical: ≥1 KHL  
- Snapshot → ZK-MACI

### Treasury Flow
- 100% of purchases fund seva  
- Treasury actions require governance approval

---

# 6. KHL Token Model

## 6.1 Token Definition
- Non-transferable ERC-20-like  
- Minted only on L2  
- Fixed supply: 96 crore  
- Price: 10 USDT  
- No trading, no liquidity pools  
- Governance access token  
- No financial rights

## 6.2 Token Roles
- Governance access  
- Seva contribution  
- Participation credential  
- Identity intent signal

## 6.3 Token Lifecycle
- Wallet is whitelisted  
- User buys KHL → funds to Treasury  
- KHL minted  
- Non-transferability enforced

## 6.4 Distribution Phases
- Phase 0: Manual invite-only  
- Phase 1: Trusted inviters  
- Phase 2: Khalsa-ID-gated onboarding  
- Phase 3: Institutional distribution

## 6.5 Why Fixed Price?
Fairness, simplicity, anti-speculation.

## 6.6 No Redemption Mechanism
Avoids liability + speculation + bank-runs.

## 6.7 Non-Transferability
```
function transfer(...) public pure returns (bool) {
    revert("NON_TRANSFERABLE");
}
function transferFrom(...) public pure returns (bool) {
    revert("NON_TRANSFERABLE");
}
```

---

# 7. Identity Framework (Khalsa ID)

## 7.1 Definition
Soulbound ERC-1155 credential proving verified Sikh identity.

## 7.2 Issuer Registry
Authorised institutions assign Khalsa ID; managed by governance.

## 7.3 Issuance Workflow
- User verifies with institution  
- Institution mints SBT  
- Optional role/membership credentials issued

## 7.4 Privacy
No personal data stored on-chain.

## 7.5 Hierarchical Structure
Individual → Gurdwara → Regional → Global

---

# 8. Governance Protocol

## 8.1 Objectives
Transparency, accountability, decentralisation, Panthic alignment.

## 8.2 Eligibility
- Panthic: Khalsa ID + ≥1 KHL  
- Technical: ≥1 KHL

## 8.3 Weighting
One-person-one-vote.

## 8.4 Governance Layers
- Gurdwara-level  
- Regional (future)  
- Global (long-term)

## 8.5 Voting Mechanisms
- Phase 1: Snapshot  
- Phase 3: ZK-MACI

## 8.6 Proposal Types
- Informational  
- Treasury allocations  
- Contract execution

## 8.7 Governance Safe (L2 Execution)
Executes approved proposals:
- Treasury disbursements  
- Whitelist updates  
- ID issuer management  
- Contract upgrades  
- Emergency actions  

---

# 9. Treasury Architecture

## 9.1 Goals
Transparent, trust-minimised seva funding.

## 9.2 Components
- Seva Treasury Safe  
- Governance Safe  
- Buy-Only Contract  

## 9.3 Treasury Safe
Holds stablecoins. Cannot execute without Governance Safe.

## 9.4 Buy-Only Contract
Whitelisted buyers only; mints KHL.

## 9.5 No Sell-Back Mechanism
Funds remain for seva.

## 9.6 Treasury Flow
Proposal → Vote → Governance Safe → Treasury Safe → Payment  

---

# 10. Smart Contract Architecture

## 10.1 Overview
- KhalsaRootL1 (L1)  
- L1 Governance Safe  
- KHL Token (L2)  
- Buy-Only Contract  
- Khalsa ID  
- Issuer Registry  
- Governance Safe  
- Treasury Safe  

## 10.2 Relationship Diagram
![Contract Architecture](diagrams/contract-architecture.svg)

## 10.3 Upgradeability
Minimal proxies; governance-approved upgrades.

## 10.4 Security Assumptions
Audited contracts, safe multisigs, minimal trust surfaces.

---

# 11. Risk Analysis

- Identity risks  
- Governance capture  
- Treasury misallocation  
- Technical vulnerabilities  
- Social risks  
(Details can be expanded)

---

# 12. Ethical & Panthic Alignment

- Sarbat da bhala  
- Equality & fairness  
- Seva over profit  
- Transparency  
- Decentralisation aligns with Sikh values  

---

# 13. Roadmap

## Phase 1 — MVP (2025)
- KHL minting  
- Snapshot governance  
- Basic identity issuance

## Phase 2 — Identity Expansion (2025–26)
- Gurdwara onboarding  
- Role SBTs

## Phase 3 — ZK Governance (2026–27)
- MACI integration  
- Regional decision-making

## Phase 4 — Global Governance (2027+)
- Panthic coordination  
- Institutional adoption

---

# 14. Conclusion

KGP provides decentralised, transparent, and identity-gated governance infrastructure for the global Sikh Panth — rooted in Gurmat and secured by Ethereum.  
It is non-political, seva-centric, and designed for long-term evolution with the Sangat.

---

# 15. Appendix

- Credential definitions  
- Contract interfaces (KHL, ID, Issuer Registry, Buy-Only)  
- Threat models  
- Data structures  
(We can expand these in separate commits.)

---

# 16. Disclaimer

- Non-financial token  
- No profit rights  
- Not a replacement for Sikh institutions  
- Not political  
- Experimental technology

---

# 17. References

(To be populated)