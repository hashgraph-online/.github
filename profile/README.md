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

## HOL Guard — local runtime firewall for AI coding agents

[**HOL Guard**](https://hol.org/guard) is local-first **runtime** control on the developer machine. It can ask or block before supported AI coding agents run shell commands, read secrets or files, change MCP servers, or install plugins and skills.

It is not a cloud MCP gateway, not a catalog scanner, and not a complete prompt-injection preventer. Cursor/artifact trust is not full pre-exec on every MCP tool call.

```bash
# https://hol.org/guard/install
set -o pipefail; curl -fsSL https://hol.org/guard/install.sh | bash -s -- --mode install --verify
hol-guard init
```

Plugin **catalog scan** is a separate tool ([`plugin-scanner`](https://github.com/hashgraph-online/hol-guard), [`ai-plugin-scanner-action`](https://github.com/hashgraph-online/ai-plugin-scanner-action)). Browse the catalog at [hol.org/plugins](https://hol.org/plugins). A scan is not a safety guarantee.

[Install →](https://hol.org/guard/install) · [Source →](https://github.com/hashgraph-online/hol-guard)

---

## Standards SDK

The [`@hashgraphonline/standards-sdk`](https://www.npmjs.com/package/@hashgraphonline/standards-sdk) provides TypeScript libraries for HCS standards — agent identity, registries, communication, and more.

```bash
npm install @hashgraphonline/standards-sdk
```

```typescript
import { HCS14Client, HCS11Client } from '@hashgraphonline/standards-sdk';

// Resolve a Universal Agent ID (HCS-14)
const hcs14 = new HCS14Client({
  network: 'mainnet',
  operatorId: process.env.HEDERA_ACCOUNT_ID!,
  privateKey: process.env.HEDERA_PRIVATE_KEY!,
});
const profile = await hcs14.resolveUaidProfile('uaid:hiero:mainnet:0.0.12345');

// Create an agent profile (HCS-11)
const hcs11 = new HCS11Client({
  network: 'mainnet',
  auth: {
    operatorId: process.env.HEDERA_ACCOUNT_ID!,
    privateKey: process.env.HEDERA_PRIVATE_KEY!,
  },
});
const result = await hcs11.createAndInscribeProfile({
  name: 'My Agent',
  bio: 'An AI assistant for developer workflows.',
});
```

Browse the SDK docs → **[https://hol.org/docs](https://hol.org/docs)**

---

## Core infrastructure

| Asset | What it does |
|---|---|
| [Universal Agentic Registry](https://hol.org/registry) | Discover agents, MCP servers, skills, and plugins across protocols |
| [Registry Broker](https://github.com/hashgraph-online/registry-broker) | Route agent discovery queries across registries and protocols |
| [Standards SDK](https://github.com/hashgraph-online/standards-sdk) | TypeScript libraries for HCS standards — identity, registries, communication |
| [HOL Guard](https://hol.org/guard) | Local runtime firewall for AI coding agents — shell, secrets/file reads, MCP server change, plugin/skill install |
| Universal Agent IDs / HCS-14 | Portable, cross-protocol agent identifiers with DNS and DID proofs |
| OpenConvAI / HCS-10 | Agent communication standard for messaging and presence |
| Agent Profiles / HCS-11 | Metadata, capabilities, and service discovery for agents |
| Plugin catalog scan | Static checks via [plugin-scanner](https://github.com/hashgraph-online/hol-guard); browse [hol.org/plugins](https://hol.org/plugins). Scan is not a safety guarantee |

---

## Interoperability coverage

| Area | Examples |
|---|---|
| Agent discovery | Universal Agentic Registry, HCS-2 registries, HCS-21 capability attestations |
| Agent identity | HCS-11 profiles, HCS-14 UAIDs, DNS/domain proofs |
| Communication | HCS-10/OpenConvAI, adapter-based routing for A2A and XMTP |
| Tooling | MCP servers, skills, plugins, SDK integrations |
| Trust and provenance | HOL Guard runtime control, catalog scan (not a safety guarantee), attestations, audit trails |
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
| **HCS-2** | Discovery Registries | Published |
| **HCS-20** | Auditable Points — transparent incentives/rewards | Published |
| **HCS-21** | Agentic Data Registries — discovery/capability attestations | Published |
| **HCS-1** | File Storage & Retrieval | Published |
| **HCS-3** | Resource Linking & Recursion | Published |

Full standards catalog → **[https://hol.org/docs/standards](https://hol.org/docs/standards)**

---

## Where to start

| If you want to... | Start here |
|---|---|
| Search or register agents | [Universal Agentic Registry](https://hol.org/registry) |
| Add runtime protection for AI coding agents | [HOL Guard](https://hol.org/guard) |
| Run a catalog scan (not a safety guarantee) | [Plugin catalog](https://hol.org/plugins) · [plugin-scanner](https://github.com/hashgraph-online/hol-guard) |
| Build with HOL standards | [Standards SDK](https://github.com/hashgraph-online/standards-sdk) |
| Add discovery to an assistant | [Registry Broker](https://github.com/hashgraph-online/registry-broker) |
| Build HCS-10 agents | Standards SDK HCS-10 modules |
| Propose a standard | [hcs-improvement-proposals](https://github.com/hashgraph-online/hcs-improvement-proposals) |
| Explore examples | [Quickstarts and demos](https://hol.org/docs) |

---

## Contribute

* **Propose or review a standard** — open issues and PRs in [hcs-improvement-proposals](https://github.com/hashgraph-online/hcs-improvement-proposals)
* **Build protocol adapters** — help extend cross-protocol routing
* **Publish agents, skills, or MCP servers** — list them in the [registry](https://hol.org/registry)
* **Improve SDK examples** — PRs welcome in [standards-sdk](https://github.com/hashgraph-online/standards-sdk)
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
