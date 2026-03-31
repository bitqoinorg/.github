<div align="center">

<img src="https://raw.githubusercontent.com/bitqoinorg/wallet/main/public/favicon.png" width="72" height="72" alt="bitQoin" />

# bitQoin

**Quantum-Resistant Solana Vault Infrastructure**

*Qonjoint: The dual-key protocol built for the post-quantum era*

[![X](https://img.shields.io/badge/X-%40bitqoinorg-000000?style=flat-square&logo=x)](https://x.com/bitqoinorg)
[![GitHub](https://img.shields.io/badge/GitHub-bitqoinorg-181717?style=flat-square&logo=github)](https://github.com/bitqoinorg)
[![License](https://img.shields.io/badge/license-MIT-F7931A?style=flat-square)](https://github.com/bitqoinorg/wallet/blob/main/LICENSE)
[![Built on Solana](https://img.shields.io/badge/Built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)

</div>

---

## What is bitQoin

bitQoin is a non-custodial Solana wallet that implements the **Qonjoint protocol**, a dual-key architecture designed to withstand both classical and quantum adversaries.

A single compromised key is never enough. Both keys must sign together. No exceptions.

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

```mermaid
flowchart LR
    classDef key fill:#1a1a1a,color:#F7931A,stroke:#F7931A,stroke-width:2px
    classDef vault fill:#F7931A,color:#1a1a1a,stroke:none
    classDef chain fill:#0a1a0a,color:#90ee90,stroke:#1a5a1a,stroke-width:2px

    KA(["Key A"]):::key
    KB(["Key B"]):::key
    V(["Qonjoint Vault"]):::vault
    S(["Solana"]):::chain

    KA --> V
    KB --> V
    V --> S

    click KA "https://github.com/bitqoinorg/protocol" "Protocol spec"
    click V "https://github.com/bitqoinorg/wallet" "Wallet repo"
    click S "https://solana.com" "Solana"
```

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

[x.com/bitqoinorg](https://x.com/bitqoinorg) · [github.com/bitqoinorg](https://github.com/bitqoinorg)

</div>
