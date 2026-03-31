<div align="center">

<img src="https://raw.githubusercontent.com/bitqoinorg/wallet/main/public/favicon.png" width="88" height="88" alt="bitQoin" />

# bitQoin

**Quantum-Resistant Solana Vault Infrastructure**

*Qonjoint — The 2-of-2 multisig protocol built for the post-quantum era*

[![X](https://img.shields.io/badge/X-%40bitqoinorg-000000?style=flat&logo=x)](https://x.com/bitqoinorg)
[![GitHub](https://img.shields.io/badge/GitHub-bitqoinorg-181717?style=flat&logo=github)](https://github.com/bitqoinorg)
[![License](https://img.shields.io/badge/license-MIT-F7931A?style=flat)](./LICENSE)
[![Built on Solana](https://img.shields.io/badge/Built%20on-Solana-9945FF?style=flat&logo=solana)](https://solana.com)

</div>

---

## What is bitQoin

bitQoin is a non-custodial Solana wallet that implements the **Qonjoint protocol** — a 2-of-2 multisig architecture designed to withstand both classical and quantum adversaries.

A single compromised key is never enough. Both keys must sign together. No exceptions.

---

## Qonjoint Protocol Architecture

```mermaid
flowchart TD
    classDef primary fill:#F7931A,color:#fff,stroke:none,rx:12
    classDef secondary fill:#1a1a1a,color:#FAFAF5,stroke:#F7931A,stroke-width:2px,rx:12
    classDef accent fill:#2a2a2a,color:#F7931A,stroke:#F7931A,stroke-dasharray:6 3,rx:12
    classDef success fill:#1a3a1a,color:#90ee90,stroke:#3a7a3a,stroke-width:2px,rx:12
    classDef danger fill:#3a1a1a,color:#ff6b6b,stroke:#7a3a3a,stroke-width:2px,rx:12

    A(["🔐 User Intent<br/>Send Transaction"]):::primary

    subgraph VAULT ["  Qonjoint Vault  "]
        direction TB
        K1["🗝️ Key A<br/><small>Primary Signer</small>"]:::secondary
        K2["🗝️ Key B<br/><small>Secondary Signer</small>"]:::secondary
        AND{"AND Gate<br/>2 of 2<br/>Required"}:::accent
        K1 --> AND
        K2 --> AND
    end

    subgraph QUANTUM ["  Quantum Threat Layer  "]
        direction LR
        QC["⚛️ Quantum<br/>Computer"]:::danger
        QA["🛡️ Post-Quantum<br/>Guard"]:::accent
        QC -. "Grover / Shor<br/>Attack" .-> QA
    end

    subgraph SOLANA ["  Solana Network  "]
        direction TB
        TX["📦 Transaction<br/>Bundle"]:::secondary
        VAL["✅ Validator<br/>Consensus"]:::success
        CHAIN["⛓️ Immutable<br/>Ledger"]:::success
        TX --> VAL --> CHAIN
    end

    A --> VAULT
    VAULT --> |"Both Keys Present"| QA
    QA --> |"Threat Neutralized"| TX
    AND --> |"One Key Missing"| REJECT(["❌ Rejected"]):::danger

    style VAULT fill:#111,stroke:#F7931A,stroke-width:3px,rx:16,color:#FAFAF5
    style QUANTUM fill:#1a0a0a,stroke:#7a3a3a,stroke-width:2px,rx:16,color:#FAFAF5
    style SOLANA fill:#0a0a1a,stroke:#3a3a7a,stroke-width:2px,rx:16,color:#FAFAF5
```

---

## Transaction Signing Flow

```mermaid
sequenceDiagram
    autonumber
    participant U as 👤 User
    participant V as 🔐 Qoin Vault
    participant KA as 🗝️ Key A
    participant KB as 🗝️ Key B
    participant Q as 🛡️ Quantum Guard
    participant S as ⛓️ Solana

    U->>+V: Open vault with Key A + Key B
    V->>V: Verify 2-of-2 key pair integrity
    V-->>U: Vault unlocked ✓

    U->>+V: Initiate send transaction
    V->>+KA: Request partial signature
    KA-->>-V: sig_A ✓
    V->>+KB: Request partial signature
    KB-->>-V: sig_B ✓

    V->>V: Combine sig_A + sig_B
    V->>+Q: Run post-quantum integrity check
    Q-->>-V: Threat level: None ✓

    V->>+S: Broadcast signed transaction
    S-->>-V: Confirmed · slot #XXXXXXX
    V-->>-U: 🟢 Transaction success
    Note over U,S: Explorer link delivered via Orb Markets
```

---

## Repository Map

```mermaid
graph LR
    classDef repo fill:#1a1a1a,color:#FAFAF5,stroke:#F7931A,stroke-width:2px,rx:10
    classDef core fill:#F7931A,color:#1a1a1a,stroke:none,rx:10
    classDef private fill:#2a1a1a,color:#ff9999,stroke:#7a3a3a,stroke-width:2px,rx:10
    classDef live fill:#0a2a0a,color:#90ee90,stroke:#1a5a1a,stroke-width:2px,rx:10

    ORG(["🏛️ bitqoinorg"]):::core

    ORG --> W(["💼 /wallet<br/>React · Vite · Tailwind<br/>public"]):::repo
    ORG --> API(["⚙️ /api<br/>Express · Helius RPC<br/>private"]):::private
    ORG --> P(["📜 /protocol<br/>Qonjoint Specification<br/>public"]):::repo
    ORG --> GH(["🏠 /.github<br/>Org Profile · CI Templates<br/>public"]):::repo

    W --> D(["🌐 bitqoinorg.github.io/wallet"]):::live
    API --> H(["🔌 Helius WebSocket"]):::repo
    P --> SPEC(["📐 2-of-2 Multisig Spec"]):::repo

    click ORG "https://github.com/bitqoinorg" "bitQoin organization"
    click W "https://github.com/bitqoinorg/wallet" "Wallet repository"
    click API "https://github.com/bitqoinorg/api" "API repository"
    click P "https://github.com/bitqoinorg/protocol" "Protocol specification"
    click GH "https://github.com/bitqoinorg/.github" "Org profile"
    click D "https://bitqoinorg.github.io/wallet" "Live wallet"
    click H "https://www.helius.dev" "Helius RPC"
    click SPEC "https://github.com/bitqoinorg/protocol" "Full specification"
```

---

## Development Timeline

```mermaid
timeline
    title bitQoin Build Progression
    section Foundation
        Q1 2026 : Monorepo bootstrap
               : TypeScript workspace config
               : Express API scaffold
               : Vite React frontend
    section Core Protocol
        Q1 2026 : Qonjoint 2-of-2 multisig
               : Keypair generation vault
               : Helius RPC integration
               : Solana transaction signing
    section User Interface
        Q1 2026 : Landing page with 9 subpages
               : 6-language i18n system
               : Dark and light mode
               : Navbar dropdown navigation
    section Security Layer
        Q2 2026 : Post-quantum threat analysis
               : Hack challenge live
               : Orb explorer integration
               : Audit preparation
```

---

## Security Model

```mermaid
flowchart LR
    classDef threat fill:#3a0a0a,color:#ff6b6b,stroke:#7a1a1a,rx:10
    classDef defense fill:#0a2a0a,color:#90ee90,stroke:#1a5a1a,rx:10
    classDef neutral fill:#1a1a1a,color:#FAFAF5,stroke:#3a3a3a,rx:10

    subgraph ATTACKS ["Known Attack Vectors"]
        direction TB
        T1["Shor's Algorithm<br/>Private key recovery"]:::threat
        T2["Grover's Algorithm<br/>Signature forgery"]:::threat
        T3["Single key theft<br/>Phishing / malware"]:::threat
        T4["Hot wallet compromise<br/>Exchange hack"]:::threat
    end

    subgraph QONJOINT ["Qonjoint Defenses"]
        direction TB
        D1["Key A lives<br/>on cold device"]:::defense
        D2["Key B lives<br/>on separate device"]:::defense
        D3["2-of-2 AND gate<br/>Both required always"]:::defense
        D4["No server custody<br/>100% self-sovereign"]:::defense
    end

    RESULT(["🔐 Vault Secure"]):::neutral

    T1 --> |blocked by| D3
    T2 --> |blocked by| D3
    T3 --> |blocked by| D2
    T4 --> |blocked by| D4
    D1 & D2 & D3 & D4 --> RESULT

    style ATTACKS fill:#1a0505,stroke:#5a1a1a,rx:14
    style QONJOINT fill:#051a05,stroke:#1a5a1a,rx:14
```

---

## Stack

| Layer | Technology |
|---|---|
| Frontend | React 18 · Vite · Tailwind CSS · TypeScript |
| Backend | Express 5 · Node.js · Pino |
| Blockchain | Solana · @solana/web3.js · Helius RPC |
| Wallet | Qonjoint 2-of-2 multisig protocol |
| i18n | EN · JA · ZH · DE · ES · AR |
| Explorer | Orb Markets |
| Deploy | GitHub Pages · bitqoinorg.github.io |

---

## Team

<table align="center">
  <tr>
    <td align="center" width="200">
      <a href="https://github.com/kaiming-lang">
        <img src="https://avatars.githubusercontent.com/u/264678797?v=4" width="80" height="80" style="border-radius:50%" alt="Kai" /><br/>
        <strong>Kai</strong><br/>
        <sub><code>@kaiming-lang</code></sub><br/>
        <sub>quant · founder</sub>
      </a>
    </td>
    <td align="center" width="200">
      <a href="https://github.com/apps/bitqoiner">
        <img src="https://avatars.githubusercontent.com/in/3238072?v=4" width="80" height="80" style="border-radius:50%" alt="bitqoiner" /><br/>
        <strong>bitqoiner</strong><br/>
        <sub><code>@bitqoiner[bot]</code></sub><br/>
        <sub>automated commit assistant</sub>
      </a>
    </td>
  </tr>
</table>

---

<div align="center">

**Built without compromise.**

[x.com/bitqoinorg](https://x.com/bitqoinorg) · [github.com/bitqoinorg](https://github.com/bitqoinorg)

</div>
