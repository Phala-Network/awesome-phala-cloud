# This Repo Has Been Moved to https://github.com/Phala-Network/phala-cloud/tree/main/awesome-phala-cloud

# Awesome Phala Cloud

[![](https://cloud.phala.network/deploy-button.svg)](https://cloud.phala.network/templates)

A curated list of awesome Phala Cloud resources, tools, and templates.

[Phala Cloud](https://cloud.phala.network) is a decentralized cloud computing platform that enables developers to build and deploy confidential computing applications.

## Templates

### MCP (Model Context Protocol) Servers

- [**MOOF MCP**](https://github.com/moofdotfun/MOOF-MCP) - An MCP server enables LLMs to work with the MOOF platform, deployed on Phala Cloud. It can list flows, create new flows, and deploy other MCP servers on Phala Cloud. Additionally, it supports fetching public flow templates, forking flows from templates, retrieving authenticated user flows, publishing or unpublishing flows to/from the shared flow store, and deploying MCP servers directly from GitHub with optional Phala hosting and environment variable support. *by MOOF*
- [**DeMCP Defillama**](https://github.com/Phala-Network/awesome-phala-cloud/tree/main/prebuilt/demap-defilama) - A DeFiLlama MCP server deployed on Phala Cloud that enables AI agents to fetch real-time DeFi data, including protocol TVL (Total Value Locked), chain metrics, and token prices. *by DeMCP*
- [**Context7 MCP**](https://github.com/Phala-Network/awesome-phala-cloud/tree/main/prebuilt/context7-mcp) - A Context7 MCP server deployed on Phala Cloud that enables AI agents to fetch real-time Context7 data, including protocol TVL (Total Value Locked), chain metrics, and token prices. *by Phala-Network*
- [**MCP Server Fetch**](https://github.com/Phala-Network/mcp-servers/tree/main/src/fetch) - A MCP server deployed on Phala Cloud that enables AI agents to fetch real-time data from a given URL. *by Leechael*
- [**MCP Server Sequential Thinking**](https://github.com/Phala-Network/mcp-servers/tree/main/src/sequentialthinking) - A MCP server deployed on Phala Cloud that enables AI agents to think sequentially. *by Leechael*
- [**Swarms Agent in Phala TEE**](https://github.com/The-Swarm-Corporation/Phala-Deployment-Template) - A Swarms agent deployed on Phala Cloud that perform a comprehensive legal team swarm for contract creation and management. *by The-Swarm-Corporation*
- [**Armor Crypto**](https://github.com/HashWarlock/armor-crypto-mcp/tree/phala-mcp) - A single source for integrating AI Agents with the Crypto ecosystem. This includes Wallet creation and management, swaps, transfers, event-based trades like DCA, stop loss and take profit, and much more. The Armor MCP supports Solana in Alpha and, when in beta, will support more than a dozen blockchains, including Ethereum. Base, Avalanche, Bitcoin, Sui, Berachain, megaETH, Optimism, Ton, BNB, and Arbitrum, among others. Using Armor's MCP you can bring all of crypto into your AI Agent with unified logic and a complete set of tools. *by Armor Crypto*
- [**Moralis MCP**](https://github.com/HashWarlock/moralis-mcp-server) - The Moralis MCP Server is a local or cloud-deployable engine that connects natural language prompts to real blockchain insights — allowing AI models to query wallet activity, token metrics, dapp usage, and more without custom code or SQL. *by Moralis*
- [**Zep Graphiti MCP**](https://github.com/HashWarlock/graphiti/tree/main/mcp_server) - The [Zep Graphiti MCP Server](https://www.getzep.com/product/knowledge-graph-mcp/) is a framework for building and querying temporally-aware knowledge graphs, specifically tailored for AI agents operating in dynamic environments. Unlike traditional retrieval-augmented generation (RAG) methods, Graphiti continuously integrates user interactions, structured and unstructured enterprise data, and external information into a coherent, queryable graph. The framework supports incremental data updates, efficient retrieval, and precise historical queries without requiring complete graph recomputation, making it suitable for developing interactive, context-aware AI applications. **by Zep**

### Starter Templates

- [**Next.js Starter**](https://github.com/Phala-Network/phala-cloud-nextjs-starter) - Template for developing a Next.js-based app with boilerplate code targeting deployment on Phala Cloud and DStack. It includes the SDK by default to make integration with TEE features easier. *by Phala-Network*
- [**Python Starter**](https://github.com/Phala-Network/phala-cloud-python-starter) - Template for developing a FastAPI-based app with boilerplate code targeting deployment on Phala Cloud and DStack. It includes the SDK by default to make integration with TEE features easier. *by Phala-Network*
- [**Bun + TypeScript Starter**](https://github.com/Phala-Network/phala-cloud-bun-starter) - Template for developing a Bun-based app with boilerplate code targeting deployment on Phala Cloud and DStack. It includes the SDK by default to make integration with TEE features easier. *by Phala-Network*
- [**Node.js + Express + TypeScript Starter**](https://github.com/Gldywn/phala-cloud-node-starter) - Template for developing a Node.js (Typescript) w/ Express app with boilerplate code targeting deployment on Phala Cloud and DStack. It includes the SDK by default to make integration with TEE features easier. *by [Gldywn](https://github.com/Gldywn)*

### Oracles & Data Feeds

- [**Node.js Oracle Template**](https://github.com/Gldywn/phala-cloud-oracle-template) - A template for building high-integrity oracles that provides a two-fold guarantee: verifiable computation and verifiable networking. It includes a price aggregator example that demonstrates how to securely fetch, aggregate, and attest to external data, making it a robust foundation for any oracle use case. *by [Gldywn](https://github.com/Gldywn)*
- [**VRF in TEE**](https://github.com/Phala-Network/phala-cloud-vrf-template) - This is a template for developing a VRF generator on Phala Cloud and DStack. It delivers cryptographically verifiable randomness for Web3 applications with hardware-backed security and unprecedented efficiency. *by Phala-Network*
- [**NEAR Shade Agent**](https://github.com/HashWarlock/shade-agent-template/tree/phala-cloud) - Deploy verifiable blockchain agents and oracles on NEAR Protocol using Phala Cloud's TEE infrastructure. Includes ETH price oracle example and framework for custom agent development with hardware-backed security, private key management, and attestation. *by Near*

### Other Templates

- [**n8n Workflow Automation**](https://github.com/Phala-Network/awesome-phala-cloud/tree/main/templates/n8n) - A powerful workflow automation tool deployed on Phala Cloud with OAuth2 authentication fixes for TEE environment. Build complex automations, integrate with 400+ services, and run workflows securely within the TEE. *by n8n*
- [**Maybe Finance**](https://github.com/Phala-Network/awesome-phala-cloud/tree/main/templates/maybe-ai) - A comprehensive open-source personal finance management app deployed on Phala Cloud. Track expenses, budgets, investments, and net worth with bank syncing, AI insights, and beautiful analytics - all secured within TEE infrastructure. *by Maybe Finance*
- [**Anyone Anon Service**](https://github.com/rA3ka/dstack-examples/tree/main/anyone-anon-service) - Sets up a Anyone Anon (hidden) service and serves an nginx website from that. *by Anyone*
- [**Anyone Network Relay**](https://github.com/rA3ka/anon-relay-docker/tree/main) - Set up a Anon relay and participate in expanding the Anyone Network by providing bandwidth to earn recognition rewards. *by Anyone*
- [**TEE Tor Hidden Service**](https://github.com/Dstack-TEE/dstack-examples/tree/main/tor-hidden-service) - This docker compose example sets up a Tor hidden service and serves an nginx website from that. *by Dstack-TEE*
- [**TEE Coprocessors in Dstack**](https://github.com/Dstack-TEE/dstack-examples/tree/main/lightclient) - Minimal docker file for using the Helios light client to provide a trustworthy view of the blockchain. *by Dstack-TEE*
- [**Webshell**](https://github.com/Dstack-TEE/dstack-examples/tree/main/webshell) - This guide outlines the steps to set up and use a webshell with the ttyd service. *by Dstack-TEE*
- [**Coinbase x402 TEE**](https://github.com/HashWarlock/402-api-test/tree/phala-cloud) - A demonstration of a Node.js Express server that integrates TEE and the [X402 payment protocol](https://www.x402.org/) for monetizing API endpoints. *by Phala-Network*
- [**Microsoft Presidio in TEE**](https://github.com/HashWarlock/presidio/tree/phala-cloud/docs/samples/python/streamlit) - This is a demo application for Microsoft Presidio, a powerful open-source framework for PII (Personally Identifiable Information) detection and de-identification. This demo is optimized for deployment on Phala Cloud's Confidential Virtual Machines (CVMs). *by Microsoft*
- [**NEAR Shade Agent**](https://github.com/HashWarlock/shade-agent-template/tree/phala-cloud) - Deploy verifiable blockchain agents and oracles on NEAR Protocol using Phala Cloud's TEE infrastructure. Includes ETH price oracle example and framework for custom agent development with hardware-backed security, private key management, and attestation. *by Near*
- [**bytebot**](https://github.com/bytebot-ai/bytebot) - Bytebot is a desktop AI agent with its own virtual computer—not just a browser script or RPA bot. It can use any app, manage files, log in with a password manager, read PDFs and spreadsheets, and execute complex multi-step workflows. Think of it as a virtual employee that sees the screen, moves the mouse, types, and gets work done like a human. *by bytebot*

## Contributing

Review the [Contributing guidelines](CONTRIBUTING.md).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
