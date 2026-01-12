# Awesome UCP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of awesome Universal Commerce Protocol (UCP) resources, tools, and implementations.

```
                              ┌─────────────────────────────────────────┐
                              │         🛒 MERCHANTS & RETAILERS        │
                              │  ┌─────────┐ ┌─────────┐ ┌─────────┐   │
                              │  │ Shopify │ │  Etsy   │ │ Target  │   │
                              │  └────┬────┘ └────┬────┘ └────┬────┘   │
                              └───────┼───────────┼───────────┼────────┘
                                      │           │           │
                                      ▼           ▼           ▼
┌─────────────────┐           ╔═══════════════════════════════════════╗           ┌─────────────────┐
│   🤖 AI AGENTS  │           ║                                       ║           │  💳 PAYMENTS    │
│  ┌───────────┐  │◀─────────▶║     Universal Commerce Protocol       ║◀─────────▶│  ┌───────────┐  │
│  │  Gemini   │  │           ║              (UCP)                    ║           │  │   Stripe  │  │
│  ├───────────┤  │           ║                                       ║           │  ├───────────┤  │
│  │  Claude   │  │           ║  ┌─────────┬─────────┬─────────┐     ║           │  │   Visa    │  │
│  ├───────────┤  │           ║  │   MCP   │   A2A   │   AP2   │     ║           │  ├───────────┤  │
│  │  ChatGPT  │  │           ║  └─────────┴─────────┴─────────┘     ║           │  │  PayPal   │  │
│  └───────────┘  │           ╚═══════════════════════════════════════╝           │  └───────────┘  │
└─────────────────┘                           │                                   └─────────────────┘
                                              │
                                              ▼
                              ┌───────────────────────────────────────┐
                              │          🔧 TRANSPORTS                │
                              │      REST  •  JSON-RPC  •  SSE        │
                              └───────────────────────────────────────┘
```

### Standardized APIs

```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│  🔍 DISCOVERY                                                                        │
│  ────────────────────────────────────────────────────────────────────────────────    │
│  GET  /.well-known/ucp                        → Merchant profile & capabilities      │
├──────────────────────────────────────────────────────────────────────────────────────┤
│  🛒 CHECKOUT SESSIONS                                                                │
│  ────────────────────────────────────────────────────────────────────────────────    │
│  POST /checkout-sessions                      → Create new checkout                  │
│  GET  /checkout-sessions/{id}                 → Get checkout details                 │
│  PUT  /checkout-sessions/{id}                 → Update checkout (address, items)     │
│  POST /checkout-sessions/{id}/complete        → Complete with payment                │
│  POST /checkout-sessions/{id}/cancel          → Cancel checkout                      │
├──────────────────────────────────────────────────────────────────────────────────────┤
│  📦 ORDERS                                                                           │
│  ────────────────────────────────────────────────────────────────────────────────    │
│  GET  /orders/{id}                            → Get order status & details           │
│  PUT  /orders/{id}                            → Update order                         │
├──────────────────────────────────────────────────────────────────────────────────────┤
│  🔔 WEBHOOKS                                                                         │
│  ────────────────────────────────────────────────────────────────────────────────    │
│  POST /webhooks/partners/{id}/events/order    → Order status updates                 │
└──────────────────────────────────────────────────────────────────────────────────────┘
```

### Agent Shopping Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                           🤖 AI AGENT SHOPPING JOURNEY                              │
├─────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                     │
│   ┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐      │
│   │  DISCOVER   │────▶│   CREATE    │────▶│  CONFIGURE  │────▶│  COMPLETE   │      │
│   │  MERCHANT   │     │    CART     │     │   CHECKOUT  │     │  PURCHASE   │      │
│   └─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘      │
│         │                   │                   │                   │              │
│         ▼                   ▼                   ▼                   ▼              │
│   ┌───────────┐       ┌───────────┐       ┌───────────┐       ┌───────────┐        │
│   │• Payment  │       │• Product  │       │• Shipping │       │• Payment  │        │
│   │  handlers │       │• Quantity │       │• Discounts│       │• Order ID │        │
│   │• Features │       │• Buyer    │       │• Address  │       │• Receipt  │        │
│   └───────────┘       └───────────┘       └───────────┘       └───────────┘        │
│                                                                                     │
└─────────────────────────────────────────────────────────────────────────────────────┘
```

* [What is UCP?](#what-is-ucp)
* [Official Resources](#official-resources)
* [Adopters & Endorsers](#adopters--endorsers)
* [Implementations](#implementations)
* [AI & Agent Integrations](#ai--agent-integrations)
* [Developer Tools](#developer-tools)
* [Learning Resources](#learning-resources)
* [Related Protocols](#related-protocols)

## What is UCP?

[UCP](https://ucp.dev/) is an open protocol that defines building blocks for agentic commerce—from discovering and buying to post-purchase experiences—allowing platforms, AI agents, and businesses to interoperate through one standard. Built on REST and JSON-RPC transports with MCP, A2A, and AP2 support built-in.

<br>

## Official Resources

- [Documentation](https://ucp.dev/) - Protocol overview, core concepts, and design principles
- [GitHub Repository](https://github.com/Universal-Commerce-Protocol/ucp) - Technical spec, SDKs, and reference implementations
- [Specification](https://ucp.dev/specification/overview/) - Complete technical specification
- [Playground](https://ucp.dev/playground/) - Experiment with the protocol
- [Roadmap](https://ucp.dev/documentation/roadmap/) - Future development plans

<br>

## Legend

* 🎖️ – official implementation
* programming language
  * 🐍 – Python
  * 📇 – TypeScript/JavaScript
  * 🏎️ – Go
  * 🦀 – Rust
  * #️⃣ – C#
  * ☕ – Java
* scope
  * ☁️ – Cloud Service
  * 🏠 – Local Service
* role
  * 🏪 – Merchant/Business
  * 🤖 – AI Platform/Agent
  * 💳 – Payment Provider

<br>

## Adopters & Endorsers

### Co-developers

- [Google](https://google.com)
- [Shopify](https://shopify.com)
- [Etsy](https://etsy.com)
- [Wayfair](https://wayfair.com)
- [Target](https://target.com)
- [Walmart](https://walmart.com)

### Payment Providers

- [Adyen](https://adyen.com)
- [American Express](https://americanexpress.com)
- [Ant International](https://www.antgroup.com)
- [Mastercard](https://mastercard.com)
- [PayPal](https://paypal.com)
- [Stripe](https://stripe.com)
- [Visa](https://visa.com)
- [Worldpay](https://worldpay.com)

### Retailers & Marketplaces

- [Best Buy](https://bestbuy.com)
- [Carrefour](https://carrefour.com)
- [Chewy](https://chewy.com)
- [Flipkart](https://flipkart.com)
- [Gap](https://gap.com)
- [Kroger](https://kroger.com)
- [Lowe's](https://lowes.com)
- [Macy's](https://macys.com)
- [Sephora](https://sephora.com)
- [Shopee](https://shopee.com)
- [The Home Depot](https://homedepot.com)
- [Ulta](https://ulta.com)
- [Zalando](https://zalando.com)

<br>

## Implementations

- 🎖️🐍 [Official Python SDK](https://github.com/Universal-Commerce-Protocol/python-sdk) - The official Python library for UCP with Pydantic models
- 🐍 [UCP Client Python](https://github.com/Upsonic/ucp-client-python) - Python client library for UCP
- ☁️🏪 [Google UCP Merchant Docs](https://developers.google.com/merchant/ucp) - Guide for merchants to enable AI-powered purchases through Google's AI surfaces like Search AI Mode and Gemini
- ☁️🏪 [Shopify - Agentic Commerce with UCP](https://shopify.dev/docs/agents) - Framework for building AI agents that search products, create checkouts, and track orders across Shopify merchants

<br>

## AI & Agent Integrations

- 🤖🐍 [UCP Agent Demo](https://github.com/Upsonic/UCP-Agent) - A shopping assistant powered by Upsonic AI Agent and UCP (Universal Commerce Protocol)

<br>

## Developer Tools

- 🎖️🐍📇 [UCP Samples](https://github.com/Universal-Commerce-Protocol/samples) - Sample implementations including Python and Node.js merchant servers and client scripts
- [UCP Demo Playground](https://ucp-demo.web.app) - Community-created playground demo built using Google's guide

<br>

## Learning Resources

- [Building the Universal Commerce Protocol](https://shopify.engineering/UCP) - Shopify's deep dive into UCP architecture, capabilities, and how AI agents conduct transactions with merchants
- [Under the Hood: Universal Commerce Protocol](https://developers.googleblog.com/under-the-hood-universal-commerce-protocol-ucp/) - Google's technical overview of UCP as an open-source standard for agentic commerce
- [Etsy Partners with Google on AI-Powered Shopping](https://www.etsy.com/news/etsy-partners-with-google-on-ai-powered-shopping) - Etsy's announcement about partnering with Google on UCP-powered shopping experiences
- [The Agentic Commerce Platform: Shopify Connects Any Merchant to Every AI Conversation](https://www.shopify.com/news/ai-commerce-at-scale) - Shopify's announcement of UCP and native commerce integrations across AI channels
- [Target's New Shopping Experience on Google](https://corporate.target.com/press/fact-sheet/2026/01/google-gemini-2026) - Target's fact sheet on their UCP-powered shopping experience in Google AI Mode and Gemini app

<br>

## Related Protocols

- [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) - Open protocol for AI model interactions
- [A2A (Agent2Agent)](https://github.com/google/A2A) - Protocol for agent-to-agent communication
- [AP2 (Agent Payments Protocol)](https://github.com/google-agentic-commerce/AP2) - Secure payment protocol with cryptographic consent

<br>

---

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.
