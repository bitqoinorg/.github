<img src="https://raw.githubusercontent.com/bitqoinorg/.github/main/profile/bitqoin.png" width="100%" alt="bitQoin" />

<div align="center">

# The World's First Quantum-Proof Shield for Your Coins

*Qonjoint: The dual-key protocol that makes your vault untouchable*

[![Website](https://img.shields.io/badge/website-bitqoin.org-F7931A?style=flat-square)](https://bitqoin.org)
[![X](https://img.shields.io/badge/X-%40bitqoinorg-000000?style=flat-square&logo=x)](https://x.com/bitqoinorg)
[![GitHub](https://img.shields.io/badge/GitHub-bitqoinorg-181717?style=flat-square&logo=github)](https://github.com/bitqoinorg)
[![License](https://img.shields.io/badge/license-MIT-F7931A?style=flat-square)](https://github.com/bitqoinorg/wallet/blob/main/LICENSE)
[![Built on Solana](https://img.shields.io/badge/Built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)

</div>

---

## What is bitQoin

bitQoin is the world's first quantum-proof shield for your coins. Built on Solana, it implements the **Qonjoint protocol**: a dual-key architecture where a single compromised key can never move your funds. Both keys must sign. No exceptions.

---

## Repositories

<table>
  <tr>
    <td>
      <a href="https://github.com/bitqoinorg/wallet"><strong>wallet</strong></a><br/>
      <sub>React · Vite · Tailwind · TypeScript</sub><br/>
      <sub>public</sub>
    </td>
    <td>
      <a href="https://github.com/bitqoinorg/api"><strong>api</strong></a><br/>
      <sub>Express · Helius RPC · Node.js</sub><br/>
      <sub>private</sub>
    </td>
    <td>
      <a href="https://github.com/bitqoinorg/protocol"><strong>protocol</strong></a><br/>
      <sub>Qonjoint specification</sub><br/>
      <sub>public</sub>
    </td>
  </tr>
</table>

---

## Qonjoint Architecture

How a Qonjoint vault works: two independent keys are required to authorize every transaction. Neither key alone can move funds. Both must sign. The Solana runtime enforces this at the validator level.

```mermaid
flowchart LR
    classDef key fill:#1a1a1a,color:#F7931A,stroke:#F7931A,stroke-width:2px
    classDef vault fill:#F7931A,color:#1a1a1a,stroke:none
    classDef chain fill:#0a1a0a,color:#90ee90,stroke:#1a5a1a,stroke-width:2px
    classDef reject fill:#3a0a0a,color:#ff6b6b,stroke:#7a1a1a,stroke-width:2px

    KA(["Key A
Your primary device"]):::key
    KB(["Key B
Your secondary device"]):::key
    V(["Qonjoint Vault
Both keys required to sign"]):::vault
    S(["Solana Network
Transaction confirmed on-chain"]):::chain
    R(["Rejected
One key is not enough"]):::reject

    KA -->|"signs"| V
    KB -->|"signs"| V
    V -->|"both present"| S
    V -. "missing one key" .-> R

    click V "https://github.com/bitqoinorg/wallet" "Open wallet repo"
    click S "https://solana.com" "Solana"
    click KA "https://github.com/bitqoinorg/protocol" "Read the protocol spec"
    click KB "https://github.com/bitqoinorg/protocol" "Read the protocol spec"
```

> Both keys live on separate devices. Losing one does not compromise the other.

---

## Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, Vite, Tailwind CSS, TypeScript |
| Backend | Express 5, Node.js, Pino |
| Blockchain | Solana, @solana/web3.js, Helius RPC |
| Vault | Qonjoint protocol |
| i18n | EN, JA, ZH, DE, ES, AR |
| Explorer | Orb Markets |
| Deploy | GitHub Pages |

---

## Team

<table align="center">
  <tr>
    <td align="center" width="180">
      <a href="https://github.com/kaiming-lang">
        <img src="https://avatars.githubusercontent.com/u/264678797?v=4" width="72" height="72" style="border-radius:50%" alt="Kai" /><br/>
        <strong>Kai</strong><br/>
        <sub><code>@kaiming-lang</code></sub><br/>
        <sub>quant, founder</sub>
      </a>
    </td>
    <td align="center" width="180">
      <a href="https://github.com/apps/bitqoiner">
        <img src="https://avatars.githubusercontent.com/in/3238072?v=4" width="72" height="72" style="border-radius:50%" alt="bitqoiner" /><br/>
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

[bitqoin.org](https://bitqoin.org) · [x.com/bitqoinorg](https://x.com/bitqoinorg) · [github.com/bitqoinorg](https://github.com/bitqoinorg)

</div>
