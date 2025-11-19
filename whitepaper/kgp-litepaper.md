# Khalsa Governance Protocol (KGP)
### Litepaper (v0.1, 2025)  
*A Decentralised Governance & Seva Infrastructure for the Global Sikh Panth*

---

# 1. Overview

The **Khalsa Governance Protocol (KGP)** is a decentralised governance and seva (charitable) coordination framework for the global Sikh Panth. KGP does not replace Gurdwaras, committees, or Sikh institutions. Instead, it delivers **neutral, transparent, cryptographically sound tools** that Sikh bodies can use when they choose.

KGP provides:

- **Khalsa ID (SBT):** Verified Sikh identity
- **KHL Token:** Non-transferable governance access token
- **Seva Treasury:** Multisig-controlled seva funds
- **Snapshot → ZK-MACI:** Staged governance evolution
- **Ethereum + Arbitrum security:** Transparent, verifiable decision systems

Its purpose is to align Sikh governance with Sikh ethics: *Sarbat da Bhala* (Universal Welfare), *Seva* (Selfless Service), truth, fairness, humility, and collective decision making.

---

# 2. Why KGP?

Sikh governance today is fragmented. Thousands of Gurdwaras operate independently with varying processes and no shared digital infrastructure. Challenges include:

- No global digital Sikh identity  
- No transparent digital seva funding  
- No secure, Sybil-resistant online voting  
- No coordination across organisations  
- No mechanism for global Panthic consultation  

KGP addresses these gaps through:

1. **Khalsa ID** → Verified Sikh identity credential  
2. **KHL Token** → Governance access, non-transferable  
3. **Safes** → Transparent multisig-based execution  
4. **MACI** → Anti-collusion cryptographic voting  

This provides the Panth with an ethical, trust-minimised digital governance substrate.

---

# 3. Architecture Summary

KGP is deployed across **Ethereum L1** and **Arbitrum L2**.

![KGP Unified Architecture Diagram](diagrams/system-architecture-kgp.svg)

---

## 3.1 Ethereum L1 — Root Layer

The L1 layer acts as the *constitutional foundation*.

### Components

**L1 Governance Safe**  
- Panj Pyare–style (5 member) multisig  
- Controls the root configuration

**KhalsaRootL1 Contract**  
- Stores global `MAX_SUPPLY` for KHL  
- Registers authorised L2 contracts  
- Defines upgrade authority boundaries  

This layer is minimal and stable.

---

## 3.2 Arbitrum L2 — Execution Layer

All active interaction occurs on L2 to minimise costs and improve UX.

### Core Contracts

**KHL Token (non-transferable ERC-20 style)**  
- Minted at a fixed price (10 USDT)  
- Non-transferable: prevents vote buying and speculation  
- Holding ≥1 KHL enables governance participation

**Buy-Only Contract**  
- Enforces whitelist-only access  
- Forwards all stablecoins directly to the Seva Treasury Safe  
- Cannot redeem KHL; no sell-back mechanism

**Khalsa ID (SBT)**  
- Verified Sikh identity credential  
- Required for Panthic governance matters

**Issuer Registry**  
- Authorised Sikh institutions may mint Khalsa ID  
- Managed by governance

**L2 Governance Safe**  
- Executes all approved governance decisions  
- Updates issuer registry, whitelists, contract configs

**Seva Treasury Safe**  
- Multisig custody of all stablecoins  
- Controlled exclusively via governance-approved Safe transactions

---

# 4. Governance Lifecycle

KGP governance evolves in phases:

---

## 4.1 Phase 1 — Snapshot Voting (MVP)

- Eligibility:  
  - Technical proposals → ≥1 KHL  
  - Panthic proposals → ≥1 KHL + Khalsa ID  
- Off-chain vote tally  
- On-chain execution via L2 Governance Safe

---

## 4.2 Phase 2 — Controlled Expansion

- Trusted inviter network  
- Strict whitelist controls  
- Gurdwaras or Sikh institutions may participate

---

## 4.3 Phase 3 — ZK-MACI Governance

**MACI (Minimum Anti-Collusion Infrastructure)**:  
- Encrypted ballots  
- Zero-knowledge verified tally  
- Prevents vote buying and coercion  
- Ensures one-person-one-vote privacy  
- Strong Sybil resistance

This becomes the long-term governance mode.

---

## 4.4 Phase 4 — Institutional Adoption

Gurdwaras and Sikh organisations may optionally use KGP to:

- manage internal elections  
- transparently allocate seva funds  
- coordinate projects with other institutions  
- run local and regional consultations  

KGP remains neutral and non-political.

---

# 5. Token Model — KHL

### Key Properties

- **Supply:** Fixed maximum of 96 crore (960,000,000)  
- **Price:** Fixed 10 USDT per KHL  
- **Minting:** Only via Buy-Only contract  
- **Transferability:** Disabled (non-transferable)  
- **Redemption:** No sell-back, no liquidity pools  
- **Nature:** Non-financial governance access token  
- **Rights:** No profit-sharing, no yield, no claims

### Why Non-Transferable?

- Prevent vote buying  
- Prevent accumulation of influence  
- Enforce equal weighting  
- Remove speculative incentives  
- Align with Sikh ethical principles

KHL signals **participation**, not wealth.

---

# 6. Identity Layer — Khalsa ID

**Khalsa ID** is a Soulbound Token proving Sikh identity.

### Characteristics

- Issued by approved Sikh institutions  
- Zero personal data stored on-chain  
- Required for Panthic proposals  
- Non-transferable  
- Extensible (committee roles, seva roles, membership SBTs)

### Workflow

1. Sikh presents for verification (offline)  
2. Institution checks identity using its own process  
3. Institution mints Khalsa ID SBT  
4. Wallet becomes eligible for Panthic voting

This preserves local autonomy and maryada.

---

# 7. Treasury Flow

Every KHL purchase directs stablecoins to:

### **Seva Treasury Safe**

- Multisig Safe on Arbitrum  
- Publicly auditable  
- Funds only released through governance  
- No redemption risk  
- No speculation  

A typical flow:

1. Address whitelisted  
2. Buyer pays 10 USDT per KHL  
3. Buy-Only contract mints KHL + sends USDT → Treasury Safe  
4. Treasury disbursement only after governance approval  
5. Governance Safe executes spend transaction on-chain

This ensures **full transparency** and complete separation of **decision-making** and **custody**.

---

# 8. Security Model

KGP is secured by:

- Ethereum L1  
- Arbitrum L2  
- Multisig Safes  
- Non-transferable tokens  
- SBT-based identity limits  
- Strict contract permissions  
- MACI (future)  
- Conservative upgradeability

Threats mitigated:

- Sybil attacks  
- Vote buying  
- Committee capture  
- Identity fraud  
- Treasury misuse  
- Governance coercion  
- Speculative market manipulation

---

# 9. Non-Political, Panthic-Aligned Design

KGP:

- Is not a political institution  
- Does not replace Gurdwaras or any Sikh organisations  
- Does not impose identity verification requirements  
- Is optional, open-source infrastructure  
- Follows Sikh values: truth, seva, accountability, equality  

It is simply a **digital toolset** the Sangat may use to strengthen governance and seva transparency.

---

# 10. Summary

KGP provides:

- Verified Sikh identity (Khalsa ID)  
- Transparent, accountable seva treasury  
- Non-transferable governance token (KHL)  
- Anti-collusion cryptographic voting (MACI)  
- Open-source tools for Sikh institutions  
- A neutral, Panthically grounded governance substrate  

It is a foundation for future Panthic coordination—flexible, transparent and aligned with Sikh values.

---

# Glossary

**Panth**  
The global Sikh collective community.

**Sarbat da Bhala**  
“Universal welfare” — the principle that all actions should aim to uplift humanity.

**Seva**  
Selfless service performed without desire for personal gain.

**Panj Pyare**  
“The Five Beloved Ones” — the original five Khalsa initiates; symbolically represents collective leadership in Sikh tradition.

**Maryada**  
Sikh code of conduct and discipline, often used to describe a Gurdwara’s established practices.

**Gurdwara**  
Sikh place of learning and worship; community hub.

**Khalsa**  
The community of formally initiated Sikhs committed to Sikh values and discipline.

**Khalsa ID**  
In the context of KGP, a soulbound token verifying Sikh identity.

**Sangat**  
The collective community of individuals engaged in Sikh spiritual fellowship.

---

# Contact & Repository

**GitHub:** https://github.com/sarbloc/khalsa-governance-protocol

**Maintainer:** [sarbloc](https://github.com/sarbloc)