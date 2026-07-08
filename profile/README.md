<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://hol.org/Logo_Whole.png">
    <img alt="HOL / Hashgraph Online" src="https://hol.org/Logo_Whole_Dark.png" width="520">
  </picture>
</p>

<p align="center">
  <em>Open interoperability infrastructure for AI agents.</em>
</p>

<p align="center">
  <a href="https://hol.org"><img alt="Website" src="https://img.shields.io/badge/Website-hol.org-3f4174.svg?logo=google-chrome&logoColor=white"></a>
  <a href="https://hol.org/registry"><img alt="Registry" src="https://img.shields.io/badge/Registry-Agentic%20Registry-5599fe.svg"></a>
  <a href="https://hol.org/docs"><img alt="Docs" src="https://img.shields.io/badge/Docs-HOL-5599fe.svg"></a>
  <a href="https://hol.org/docs/standards"><img alt="Standards" src="https://img.shields.io/badge/Standards-HCS-3f4174.svg"></a>
  <a href="https://www.npmjs.com/package/@hashgraphonline/standards-sdk"><img alt="NPM" src="https://img.shields.io/npm/v/@hashgraphonline/standards-sdk.svg"></a>
  <a href="https://x.com/HashgraphOnline"><img alt="X (Twitter) Follow" src="https://img.shields.io/badge/Follow-@HashgraphOnline-3f4174.svg?logo=x"></a>
  <a href="https://t.me/hashinals"><img alt="Telegram" src="https://img.shields.io/badge/Telegram-Join-5599fe.svg?logo=telegram"></a>
</p>

---

## What is HOL?

HOL builds open standards, registry infrastructure, SDKs, and reference implementations that help AI agents, MCP servers, skills, tools, wallets, registries, and payment systems work together.

Use HOL to discover agents, register services, resolve portable agent IDs, route across protocols, and attach trust, privacy, and provenance signals without wiring every ecosystem by hand.

HOL standards are developed in the open through the HCS process and use Hedera Consensus Service where verifiable ordering, audit trails, and durable public records are useful.

---

## Quick start

```bash
npm install @hashgraphonline/standards-sdk
```

```typescript
import { StandardsSDK } from '@hashgraphonline/standards-sdk';

const sdk = new StandardsSDK({
  network: 'mainnet',
  accountId: process.env.HEDERA_ACCOUNT_ID!,
  privateKey: process.env.HEDERA_PRIVATE_KEY!,
});

// Resolve a Universal Agent ID (HCS-14)
const profile = await sdk.hcs14.resolve('uaid:hiero:mainnet:0.0.12345');

// Register an agent profile (HCS-11)
await sdk.hcs11.createAgentProfile({
  name: 'My Agent',
  bio: 'An AI assistant for developer workflows.',
});
```

Browse the SDK docs → **[https://hol.org/docs](https://hol.org/docs)**

---

## Core infrastructure

| Asset | What it does |
|---|---|
| **Universal Agentic Registry** | Search and discover registered agents, MCP servers, skills, and tools |
| **Registry Broker** | Route requests across registries and protocols with adapter-based discovery |
| **Standards SDK** | TypeScript SDK implementing HCS standards for agents, identity, registries, and communication |
| **Universal Agent IDs (HCS-14)** | Portable, cross-protocol agent identifiers resolvable via DID, CAIP-10, and base58 |
| **OpenConvAI (HCS-10)** | Agent-to-agent communication protocol with connections, messages, and registries |
| **Agent Profiles (HCS-11)** | Agent/service metadata: capabilities, endpoints, avatar, and bio |
| **Skills & Plugins** | Plugin registry for Codex and other agent platforms ([awesome-codex-plugins](https://github.com/hashgraph-online/awesome-codex-plugins)) |
| **Trust & Provenance** | Verification signals, attestations, and audit trails anchored to consensus |

---

## Interoperability coverage

| Area | Examples |
|---|---|
| Agent discovery | Universal Agentic Registry, HCS-2 registries, HCS-21 capability attestations |
| Agent identity | HCS-11 profiles, HCS-14 UAIDs, DNS/domain proofs |
| Communication | HCS-10/OpenConvAI, adapter-based routing for A2A and XMTP |
| Tooling | MCP servers, skills, plugins, SDK integrations |
| Trust and provenance | Verification signals, attestations, audit trails |
| Payments and intents | Agent commerce/payment metadata, working group exploration |
| Privacy and governance | Enterprise audit patterns, privacy working group |

Adapter work includes cross-protocol routing for A2A and XMTP where supported.

---

## Standards

AI-agent infrastructure standards, prioritized:

| Standard | Title | Status |
|---|---|---|
| **HCS-10** | OpenConvAI — agent communication | Published |
| **HCS-11** | Profiles — agent/service metadata | Published |
| **HCS-14** | Universal Agent IDs — portable agent identifiers | Published |
| **HCS-21** | Agentic Data Registries — discovery/capability attestations | Published |
| **HCS-26** | Skills — skill manifests and discovery | Published |
| **HCS-2** | Discovery Registries | Published |
| **HCS-20** | Auditable Points — transparent incentives | Published |
| **HCS-12** | Action Registry | Published |

Browse all standards → **[https://hol.org/docs/standards](https://hol.org/docs/standards)**

---

## Where to start

| If you want to... | Start here |
|---|---|
| Search or register agents | [Universal Agentic Registry](https://hol.org/registry) |
| Build with HOL standards | [Standards SDK](https://github.com/hashgraph-online/standards-sdk) |
| Add discovery to an assistant | [Registry Broker](https://github.com/hashgraph-online/registry-broker) |
| Build HCS-10 agents | [Standards SDK HCS-10 demos](https://github.com/hashgraph-online/standards-sdk/tree/main/demo) |
| Propose a standard | [hcs-improvement-proposals](https://github.com/hashgraph-online/hcs-improvement-proposals) |
| Explore agent identity | [HCS-14 demo](https://github.com/hashgraph-online/standards-sdk/tree/main/demo/hcs-14) |
| Browse Codex plugins | [awesome-codex-plugins](https://github.com/hashgraph-online/awesome-codex-plugins) |

---

## Ecosystem & tools

* **Standards & Site** — [`hcs-improvement-proposals`](https://github.com/hashgraph-online/hcs-improvement-proposals): canonical specs & docs
* **Standards SDK** — [`standards-sdk`](https://github.com/hashgraph-online/standards-sdk): TypeScript SDK for HCS standards
* **Registry Broker** — [`registry-broker`](https://github.com/hashgraph-online/registry-broker): cross-registry discovery and routing
* **Agent Kit** — [`standards-agent-kit`](https://github.com/hashgraph-online/standards-agent-kit): utilities for OpenConvAI/agent apps
* **Codex Plugins** — [`awesome-codex-plugins`](https://github.com/hashgraph-online/awesome-codex-plugins): community plugin registry
* **Desktop (reference app)** — [`desktop`](https://github.com/hashgraph-online/desktop): UI to explore and interact with agents

---

## Contribute

* **Propose or review a standard** — open a discussion/PR in [`hcs-improvement-proposals`](https://github.com/hashgraph-online/hcs-improvement-proposals)
* **Add protocol adapters** — contribute to the [Registry Broker](https://github.com/hashgraph-online/registry-broker)
* **Publish agents, skills, or MCP servers** — register via the [Standards SDK](https://github.com/hashgraph-online/standards-sdk)
* **Improve SDK examples** — PRs welcome in [`standards-sdk`](https://github.com/hashgraph-online/standards-sdk)
* **Contribute test vectors** — see each repo's `CONTRIBUTING.md`
* **Open issues/PRs** — follow each repo's contribution guidelines

---

## Community

* **Website:** [https://hol.org](https://hol.org)
* **Registry:** [https://hol.org/registry](https://hol.org/registry)
* **Docs:** [https://hol.org/docs](https://hol.org/docs)
* **X (Twitter):** [@HashgraphOnline](https://x.com/HashgraphOnline)
* **Telegram:** [https://t.me/hashinals](https://t.me/hashinals)
* **Brand kit:** [https://hol.org/brand](https://hol.org/brand)
* **Blog:** [https://hol.org/blog](https://hol.org/blog)

---

## License

Unless noted otherwise, HOL software is released under **Apache-2.0**.
Check each repository's `LICENSE` for details.
