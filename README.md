# Awesome-Third-Party-Data-App-Marketplace

# Top Third-Party Data & App Marketplace Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Data Exchange, Agent Distribution & Self-Hosted Marketplace Infrastructure*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Third-Party Data & App Marketplaces**. These platforms enable organizations to discover, procure, and integrate external data assets—and increasingly, AI agents and applications—directly within their existing cloud or software ecosystems, with billing often flowing through committed cloud spend.

**Examples** include Snowflake Marketplace, AWS Marketplace, Google Cloud Marketplace, Microsoft Commercial Marketplace, Databricks Marketplace, Datarade, Salesforce AppExchange, Bloomberg Enterprise Access Point, FactSet Marketplace, and Crux Informatics (the category leaders).

**Open-source emphasis**: Third-Party Data & App Marketplace is a domain where open-source tooling is **exceptionally sparse**. The core marketplace infrastructure—listing management, secure token issuance, payments, and access control—is rarely open-sourced because it sits at the intersection of commercial data licensing and proprietary procurement workflows. The notable exception is **Unified Data Marketplace (UDAM)**, an API-first backend for monetizing data services with Stripe integration and encrypted token delivery . **FQora** is an academic prototype for quality-based data marketplace pricing, not a production platform . **World Vibe Web** offers a federated app directory model, but it is a static index of GitHub repos rather than a commerce-enabled marketplace . The critical gap: **no open-source project replicates the enterprise procurement integration** of AWS Marketplace or Snowflake Marketplace—where purchases draw down committed cloud spend and listings are inseparable from the runtime environment .

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Snowflake Marketplace](https://www.snowflake.com/)**  
  Data and app marketplace delivering listings as **live shares** directly into Snowflake accounts—no ETL or file copy; data appears as a queryable database. Sellers earn **90% revenue share**, the highest among major platforms . Market share ~16.56% in integrations marketplace category, with 1,383 customers including JPMorgan Chase, EY, and LSEG . Best for Snowflake-native teams wanting fastest integration.

- **[AWS Marketplace](https://aws.amazon.com/marketplace)**  
  The largest enterprise data marketplace with **3,500+ paid commercial listings** and 48.45% market share . Data delivered as files to S3, Redshift, or via API; purchases run through AWS billing, simplifying procurement against committed cloud spend . Sellers earn **70%** (30% platform cut). Categories include financial data (Refinitiv, FactSet), healthcare (IQVIA), location, and weather .

- **[Google Cloud Marketplace](https://cloud.google.com/marketplace)**  
  Google Cloud's marketplace with **14.56% market share** and a protocol-first approach for AI agents via the **Agent2Agent (A2A) protocol**; vendors publish an Agent Card JSON and get listed with minimal friction . Billing consolidates through Google Cloud accounts. Best for organizations already on Vertex AI/Gemini Enterprise.

- **[Microsoft Commercial Marketplace](https://azuremarketplace.microsoft.com/)**  
  Microsoft's commercial marketplace (Azure Marketplace + Microsoft 365 Agent Store) with a **distribution moat of 400M+ Microsoft 365 seats**; Agent Store lives directly inside Copilot Chat with 70+ curated agents at launch . Install-once-use-everywhere across Teams, Outlook, and M365 surface. Revenue share **85% to developers** on Windows Agent Store (preview) .

- **[Databricks Marketplace](https://www.databricks.com/)**  
  Marketplace for Lakehouse users delivering data as **Delta Sharing tables** (cross-cloud); **10.34% market share** . Leans heavily on free public datasets and AI training corpora; paid commercial listings exist but catalog is smaller than Snowflake . Sellers earn **90%** on paid datasets .

- **[Datarade](https://datarade.ai/)**  
  **Neutral data marketplace directory** connecting buyers with **550+ data providers** across financial, geospatial, AI training, and B2B contact data . Free for buyers to browse, sample, and request quotes; quote requests route details to vendor sales teams . **Directory only**—no quality control, delivery, or data tooling . Best for comparing vendors before committing.

- **[Salesforce AppExchange](https://appexchange.salesforce.com/)**  
  The oldest and most consolidated cloud app marketplace (20+ years, 5,000+ apps); **AgentExchange** extends this to AI agents with **1,000+ agents and skills** and 200+ partners, leveraging AppExchange's security review heritage . Revenue share 15% (ISVforce) or 25% (OEM) . Best for buyers already in Salesforce CRM/Service Cloud/Slack.

- **[Bloomberg Enterprise Access Point](https://www.bloomberg.com/professional/)**  
  Web-based platform for clients to discover and act on Bloomberg data products; focused on financial data distribution within Bloomberg's ecosystem .

- **[FactSet Marketplace](https://www.factset.com/marketplace)**  
  Financial data marketplace with **327+ products** including data feeds, APIs, and platforms; integrates with Snowflake, Databricks, Amazon Redshift, and FactSet's hosted environment . Strong for investment research and portfolio analytics workflows.

- **[Crux Informatics](https://www.cruxinformatics.com/)**  
  Data operations and delivery platform connecting buyers with data providers; focused on reducing the friction of data onboarding and pipeline management for financial firms .

## Open-Source GitHub Projects

### Marketplace Backend Infrastructure

- **[Unified Data Marketplace (UDAM)](https://github.com/data-agent-marketplace/data-agent-marketplace)**  
  The most complete open-source **API-first data marketplace backend** available (open-source, Node.js/Next.js/PostgreSQL) . Provides ready-to-use API for **listings, orders, and token management**; **Stripe integration** for payments (or instant tokens for small orders); **AES-256 token encryption** for service credentials; **concurrency-safe order processing** with PostgreSQL row locks to prevent overselling; session-based auth with OAuth provider support; and Docker-ready deployment . **For data sellers**: create listings with pricing and units, manage API keys securely, automated token issuance on purchase. **For buyers**: browse, instant purchase for small orders, Stripe checkout for larger orders, token management . **This is the closest open-source equivalent to the transactional plumbing of AWS Data Exchange**—but it is a backend only (bring your own frontend design) and does not provide the enterprise procurement or cloud-spend integration.

### Academic & Research Prototypes

- **[FQora](https://github.com/Songyue-Guo/FQora_web_demo)**  
  Academic prototype for a **fair and quality-based data marketplace** (ACM Web Conference 2025) . Introduces quality-constrained queries with quality-based pricing functions, effective quality assessment mechanisms, and **Balanced Pareto Optimization** to maximize utilities for both buyers and sellers . **Not production-ready**—it is a demonstration system for research on marketplace fairness and pricing, not a deployable platform.

### Federated App Directories

- **[World Vibe Web (WVW)](https://github.com/f/wvw.dev)**  
  Federated app store for open-source, "vibe-coded" projects (open-source, static site on GitHub Pages) . **No central authority**—anyone with a GitHub repo publishes an `apps.json`; a GitHub Action runs every 6 hours to aggregate, deduplicate, and enrich listings with live GitHub stats . **Guardrails**: declared stars/forks ignored (fetched live from GitHub API), featured apps curated by AI agent daily, only recognized categories accepted, owner attribution derived from repo path . **Not a commerce-enabled marketplace**—no payments, no transactions, no data licensing. It is a **discovery index** demonstrating the federated listing pattern.

### Additional Strong Open-Source Options

- **No open-source equivalent to enterprise cloud marketplaces exists** — The procurement integration (purchases drawing down committed cloud spend) and runtime coupling (listings inseparable from where the agent executes) of AWS, Snowflake, and Microsoft marketplaces are not replicable by open-source software . These are business-model and infrastructure integrations, not software features.
- **No open-source agent marketplace with commerce exists** — AgentExchange, Gemini Enterprise, and Microsoft Agent Store provide security review, revenue share, and billing integration; no open-source project replicates this .

**Frameworks for building custom systems**: For a **transactional data marketplace backend**, UDAM provides the most complete open-source foundation with Stripe payments and encrypted token delivery . For a **federated app directory without commerce**, WVW demonstrates the listing aggregation pattern . For **enterprise data procurement with cloud-spend integration**, no open-source option exists—organizations must use AWS, Snowflake, or Databricks marketplaces directly.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Data and app marketplaces handling third-party assets and transactions must comply with applicable data licensing terms, privacy regulations (GDPR, CCPA), and procurement policies; **data licensing terms vary significantly by provider and platform**—review resale, sublicensing, and warranty clauses before purchasing .
- **Open-source third-party marketplace infrastructure is severely limited**—UDAM provides a transactional backend for data services , and WVW demonstrates federated app discovery , but **no open-source project replicates the enterprise procurement and cloud-spend integration** of AWS, Snowflake, or Microsoft marketplaces. These platforms derive their value from billing relationships and runtime coupling that software alone cannot provide.
- Verify license terms for commercial use; UDAM is open-source (check repository) , and WVW is open-source (check repository) .

---

**Made for data platform engineers, procurement architects, and organizations building or evaluating marketplace infrastructure.**  
Let's make third-party data and app marketplaces more open, but with clear eyes about the procurement and billing integration that commercial platforms own.
