# Khalsa Governance Protocol (KGP)  
### Litepaper v0.2 — 2025  
*A Decentralised Governance & Seva Coordination Framework for the Global Sikh Panth*  

---

# 1. Overview

The **Khalsa Governance Protocol (KGP)** is a decentralised, identity-aware governance and seva (charity) coordination system for the global Sikh Panth. It does not replace Gurdwaras or Sikh institutions. Instead, it provides **neutral, transparent, cryptographically-verifiable infrastructure** that institutions and Sangat may adopt voluntarily.

KGP delivers:

- **Khalsa ID (SBT):** Verified Sikh identity (non-transferable).  
- **Role SBTs:** Committee roles, maintainers, issuers, membership, and permissions.  
- **KHL Token:** Non-transferable governance access token (fixed price, buy-only).  
- **Seva Treasury Safe:** Transparent custody of seva funds.  
- **Snapshot Governance (v1):** Identity-gated voting.  
- **MACI Governance (v2):** Zero-knowledge, anti-collusion voting.  
- **Provenance Layer:** Event-based audit trails across identity, governance, and treasury.

KGP aligns with Sikh ethics: *Sarbat da Bhala* (universal welfare), *Seva* (selfless service), *Sat* (truth), *Nimrata* (humility), and collective decision making.

---

# 2. Motivation

Sikh institutions conduct vast seva but lack shared digital infrastructure. Problems commonly seen across the global Panth include:

### • Fragmented governance  
Thousands of Gurdwaras operate independently with no shared digital standards, making cross-institution coordination difficult.

### • No verified digital identity  
There is no global, privacy-preserving way to prove “I am a Sikh” in online governance or seva allocations.

### • No transparent, auditable treasury layer  
Donors often cannot see how funds are allocated, and institutions lack cryptographically verifiable transparency.

### • No secure digital voting  
There is no Panthically aligned method to hold Sybil-resistant, tamper-proof, coercion-resistant online votes.

### • No provenance  
Decisions, identity issuance, and treasury actions are not linked by an immutable chain of governance reasoning.

KGP addresses these gaps while respecting existing maryada, constitutional structures, and institutional autonomy.

---

# 3. Architectural Summary

KGP is implemented entirely on **Arbitrum L2**, enabling low-cost, scalable, and verifiable governance without the complexity of maintaining an L1/L2 split.

## 3.1 Core Components

**1. Identity Layer (Khalsa ID + Role SBTs)**  
- Khalsa ID: Verified Sikh identity (ERC-1155 SBT).  
- Role SBTs: Committee, maintainer, issuer, regional, and project roles.

**2. Token Layer (KHL)**  
- Buy-only, non-transferable ERC-20 style token.  
- Fixed price: **10 USDT**.  
- Purpose: governance access (not financial).  
- Holding ≥1 KHL grants governance participation.

**3. Governance Layer**  
- **v1:** Snapshot with SBT/KHL eligibility checks.  
- **v2:** MACI for ZK, anti-coercion, private voting.  
- **L2 Governance Safe:** Executes approved proposals.

**4. Treasury Layer**  
- Seva Treasury Safe: Multisig holding all stablecoins from KHL mints.  
- All treasury actions require governance approval.  
- Full on-chain provenance.

**5. Provenance Layer**  
Event-based lineage linking:

- Identity → Issuer → Governance → Execution → Treasury  
- Every action has a `decisionId` or `contextId` anchor.

## 3.2 System Architecture Diagram

```mermaid
flowchart TB

    %% --- Identity Layer ---
    subgraph IDLayer["Identity Layer"]
        KID["Khalsa ID (SBT)"]
        RSBT["Role SBTs (Issuers, Maintainers, Committee Roles, Membership)"]
    end

    %% --- Token Layer ---
    subgraph TokenLayer["Token Layer"]
        KHL["KHL Token (Non-transferable)"]
        BO["Buy-Only Minter (10 USDT Fixed Price)"]
    end

    %% --- Governance Layer ---
    subgraph GovLayer["Governance Layer"]
        SNAP["Snapshot (Phase 1)"]
        MACI["MACI (Phase 2)"]
        GOVSAFE["L2 Governance Safe (Panj Pyare Multisig)"]
    end

    %% --- Treasury Layer ---
    subgraph TreasuryLayer["Treasury Layer"]
        TRESAFE["Seva Treasury Safe (Multisig)"]
    end

    %% --- Connections ---
    IDLayer --> SNAP
    IDLayer --> MACI

    BO --> KHL
    BO --> TRESAFE

    KHL --> SNAP
    KHL --> MACI

    SNAP --> GOVSAFE
    MACI --> GOVSAFE

    GOVSAFE --> TRESAFE