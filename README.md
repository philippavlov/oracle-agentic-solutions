# Oracle Agentic Solutions

A practical catalog of Oracle’s agentic solutions and supporting building blocks. Organized in a single file for quick navigation and easy reference. Use the table of contents to jump to any section.

> **Who is this for?** Solutions engineers, architects, data leaders, developers, and customers evaluating Oracle’s agentic capabilities and how to assemble production solutions.

---

## Table of Contents

* [How to Use This Guide](#how-to-use-this-guide)
* [Quick Decision Flow](#quick-decision-flow)
* [Comparison Matrix](#comparison-matrix)
* [Agentic Solutions](#agentic-solutions)

  * [OCI Generative AI Agents Platform](#oci-generative-ai-agents-platform)
  * [OCI Generative AI Service](#oci-generative-ai-service)
  * [OCI Data Science](#oci-data-science)
  * [Oracle Database 23ai – AI Vector Search](#oracle-database-23ai--ai-vector-search)
  * [Autonomous Database – Select AI](#autonomous-database--select-ai)
  * [Oracle SQLcl MCP Server](#oracle-sqlcl-mcp-server)
  * [Oracle Code Assist](#oracle-code-assist)
  * [Oracle AI Agent Studio for Fusion Applications](#oracle-ai-agent-studio-for-fusion-applications)
* [Reference Architectures](#reference-architectures)
* [Quickstart Demos](#quickstart-demos)
* [FAQ](#faq)
* [Changelog](#changelog)

---

## How to Use This Guide

Each solution section follows the same structure:

* **What it is**
* **When to use**
* **How it works**
* **Pros / Cons / Recommendations**
* **Links**
* **Example use case**

If you’re new to the Oracle stack, read the **Decision Flow** and the **Comparison Matrix** first.

---

## Quick Decision Flow

1. **Need a managed, enterprise agent runtime with tool use, RAG, and governance?**

   * Start with **OCI Generative AI Agents Platform**.
2. **Need LLM endpoints, embeddings, fine-tuning as building blocks?**

   * Use **OCI Generative AI Service**.
3. **Full ML/GenAI lifecycle with notebooks, MLOps, quick actions for LLMs?**

   * Use **OCI Data Science**.
4. **Want in-database vector search and hybrid semantic plus SQL joins?**

   * Use **Oracle Database 23ai – AI Vector Search**.
5. **Want natural language to SQL/RAG over Autonomous Database?**

   * Use **Select AI**.
6. **Expose Oracle Database safely to AI tools via MCP with SQL tools?**

   * Use **Oracle SQLcl MCP Server**.
7. **Need an IDE coding copilot for Oracle-centric stacks?**

   * Use **Oracle Code Assist**.
8. **Building agents inside Fusion Cloud apps (ERP, HCM, SCM, CX) with prebuilt skills?**

   * Use **AI Agent Studio for Fusion Applications**.

---

## Comparison Matrix

| Solution                              | Primary Role              | Best For                                       | Integrations                                          | Strengths                                   | Trade-offs                                    |
| ------------------------------------- | ------------------------- | ---------------------------------------------- | ----------------------------------------------------- | ------------------------------------------- | --------------------------------------------- |
| **OCI Generative AI Agents Platform** | Managed agent runtime     | Secure enterprise agents with tool use and RAG | OCI services, DB 23ai, Object Storage, external tools | Governance, security, turnkey orchestration | Fewer community connectors than open toolkits |
| **OCI Generative AI Service**         | LLM endpoints & tuning    | Model hosting, embeddings                      | OCI Network, partners                                 | Managed models, tuning                      | You assemble orchestration                    |
| **OCI Data Science**                  | DS/ML platform            | Notebooks, MLOps, LLM quick actions            | Model Catalog, OKE, Object Storage                    | End-to-end lifecycle                        | Infra familiarity helpful                     |
| **23ai – AI Vector Search**           | In-DB vector search       | Semantic + relational workloads                | DB 23ai, GPU options, ADB                             | Joins with vectors, transactionality        | DB skills needed for ops                      |
| **Autonomous DB – Select AI**         | NL to SQL/RAG             | Self-service analytics, assistants             | ADB, external LLMs                                    | Fast NL→SQL, governance                     | Works best on ADB                             |
| **SQLcl MCP Server**                  | DB tool exposure via MCP  | Secure AI tool access to Oracle DB             | Oracle Database, MCP clients                          | Strong governance, minimal lift             | Requires DB/SQLcl familiarity                 |
| **Oracle Code Assist**                | IDE coding copilot        | Oracle-centric dev teams                       | VS Code, IntelliJ                                     | Oracle stack expertise                      | Scope beyond Oracle varies                    |
| **AI Agent Studio (Fusion)**          | Design-time inside Fusion | Line-of-business agents within apps            | Fusion Apps (ERP/EPM/HCM/SCM/CX)                      | Embedded context, prebuilt agents           | App-suite scoped                              |

---

## Agentic Solutions

### OCI Generative AI Agents Platform

**What it is.** Fully managed service to build and operate enterprise AI agents with tool use, RAG, security, observability, and lifecycle management. Sometimes referred to as the “OCI AI Agent Platform.”

**When to use.**

* Enterprise agents that invoke tools, search, and structured data
* Security, auditability, and governance are required
* You want hosted orchestration over building your own stack

**How it works.** Define agents, connect tools (for example SQL, HTTP, file search), add RAG over Object Storage or 23ai vectors, configure policies and monitoring, and deploy behind APIs.

**Pros.** Managed security and governance, enterprise integrations, turnkey orchestration.

**Cons.** Smaller third-party connector ecosystem compared to OSS frameworks.

**Recommendations.** Use as your default for regulated workloads; pair with **23ai AI Vector Search** for in-database RAG and **OCI GenAI Service** for model endpoints.

**Links.** Docs: [https://docs.oracle.com/en-us/iaas/Content/generative-ai-agents/overview.htm](https://docs.oracle.com/en-us/iaas/Content/generative-ai-agents/overview.htm)

**Example.** A tax advisory firm builds a compliance copilot that answers questions over filings stored in Object Storage and verified facts in 23ai.

---

### OCI Generative AI Service

**What it is.** Managed LLM endpoints, embeddings, tuning, and playgrounds used by agents and apps.

**When to use.** You need production model hosting and customization as building blocks.

**How it works.** Choose models, deploy endpoints, fine-tune, evaluate, and gate with policies.

**Pros.** Enterprise controls, model catalog, cost and performance options.

**Cons.** You still assemble orchestration or pair with **Agents**.

**Links.** [https://docs.oracle.com/en-us/iaas/Content/generative-ai/overview.htm](https://docs.oracle.com/en-us/iaas/Content/generative-ai/overview.htm)

**Example.** Central platform team publishes approved models to business units through a model catalog.

---

### OCI Data Science

**What it is.** End-to-end DS/ML platform including **AI Quick Actions** to one-click deploy, fine-tune, evaluate, and register LLMs into a model catalog.

**When to use.** Full ML lifecycle, governed experiments, and MLOps around GenAI plus classic ML.

**How it works.** Notebooks and jobs orchestrate training, fine-tuning, evaluation, and deployment with native integrations.

**Pros.** Integrated Model Catalog, evaluation, and deployment; strong OCI integrations.

**Cons.** Requires familiarity with OCI DS workflow; choose shapes and budgets thoughtfully.

**Links.** Docs landing: [https://docs.oracle.com/en-us/iaas/data-science/](https://docs.oracle.com/en-us/iaas/data-science/) and product blogs/updates.

**Example.** Data science team fine-tunes a domain LLM, evaluates with custom metrics, and deploys behind a managed endpoint.

---

### Oracle Database 23ai – AI Vector Search

**What it is.** Native **VECTOR** type and vector indexes in Oracle Database 23ai for semantic search and RAG inside the database with transactional guarantees.

**When to use.** You want hybrid semantic plus structured joins, ACID semantics, and operational simplicity by keeping vectors with business data.

**How it works.** Store embeddings in VECTOR columns, build vector indexes, combine with SQL filters, policies, and MViews.

**Pros.** Powerful hybrid queries, governance, performance, fewer moving parts.

**Cons.** Database operations and sizing considerations; embedding generation external or via Select AI/OCI services.

**Links.** Product: [https://www.oracle.com/database/ai-vector-search/](https://www.oracle.com/database/ai-vector-search/) and User Guide: [https://docs.oracle.com/en/database/oracle/oracle-database/23/vecse/](https://docs.oracle.com/en/database/oracle/oracle-database/23/vecse/)

**Example.** Legal discovery assistant runs vector-plus-metadata filters for privileged document retrieval.

---

### Autonomous Database – Select AI

**What it is.** Natural language to SQL and RAG features in Autonomous Database, integrating with multiple LLM providers.

**When to use.** You want self-service analytics or chat over your database with controlled execution.

**How it works.** Converts NL prompts to SQL, can execute, explain, and integrate retrieval.

**Pros.** Rapid NL→SQL with governance, ADB operational simplicity.

**Cons.** Best scoped to ADB environments; complex joins still benefit from modeled schemas.

**Links.** Docs: [https://docs.oracle.com/en-us/iaas/autonomous-database-serverless/doc/sql-generation-ai-autonomous.html](https://docs.oracle.com/en-us/iaas/autonomous-database-serverless/doc/sql-generation-ai-autonomous.html)

**Example.** Finance analysts ask: “Show Q2 write-offs by region vs last year,” receive SQL and an explanation.

---

### Oracle SQLcl MCP Server

**What it is.** SQLcl can run as an **MCP server** and expose managed tools so AI clients can securely connect to Oracle Database and run SQL or SQLcl ops.

**When to use.** You want a straightforward, policy-controlled way for an AI assistant to access Oracle Database.

**How it works.** Start SQLcl in MCP mode, register tools like run-sql, authenticate against the database, and route AI client calls through MCP.

**Pros.** Governance and audit via SQLcl, minimal integration, works with any MCP-capable client.

**Cons.** Requires DB access and SQLcl; not a full agent runtime by itself.

**Links.** Blog: [https://blogs.oracle.com/database/post/introducing-mcp-server-for-oracle-database](https://blogs.oracle.com/database/post/introducing-mcp-server-for-oracle-database)

**Example.** An analyst assistant uses the run-sql tool to execute parameterized queries with row-level policies.

---

### Oracle Code Assist

**What it is.** Oracle’s IDE copilot for VS Code and IntelliJ, optimized for Java, SQL, OCI patterns, and Oracle Database ecosystems.

**When to use.** Developer productivity on Oracle stacks, secure on-prem and cloud codebases.

**How it works.** Inline suggestions, chat, code transformations, and Oracle-aware patterns.

**Pros.** Oracle-centric knowledge, accelerates consistent patterns.

**Cons.** Non-Oracle ecosystems may see less coverage.

**Links.** Announcement: [https://www.oracle.com/news/announcement/oracle-code-assist-can-help-developers-build-applications-faster-with-ai-2024-05-07/](https://www.oracle.com/news/announcement/oracle-code-assist-can-help-developers-build-applications-faster-with-ai-2024-05-07/)

**Example.** Team standardizes data-access patterns and reduces boilerplate in Java services.

---

### Oracle AI Agent Studio for Fusion Applications

**What it is.** Design-time studio inside Fusion to create or extend agents and agent teams directly where business processes live. This includes the prebuilt 50+ Fusion AI Agents.

**When to use.** You need agents embedded in ERP, HCM, SCM, CX with enterprise data, roles, and workflows.

**How it works.** Use prebuilt templates and data access policies; deploy agents to Fusion environments.

**Pros.** Short time to value, embedded context/security, line-of-business fit.

**Cons.** Scoped to Fusion; for cross-app agents use **OCI Generative AI Agents Platform**.

**Links.** [https://www.oracle.com/applications/fusion-ai/ai-agents/](https://www.oracle.com/applications/fusion-ai/ai-agents/)

**Example.** Finance team extends an approvals agent to triage exceptions with policy-aware actions.

---

## Reference Architectures

* **Secure Enterprise Agent with In-DB RAG**: OCI Generative AI Agents Platform + 23ai Vector Search + Object Storage; optional SQLcl MCP tools for governed DB access.
* **Fusion-Embedded Agent**: AI Agent Studio + prebuilt agents extended with org policies; calls out to OCI GenAI Service for model endpoints.
* **Analytics Assistant**: Autonomous Database Select AI + OCI Generative AI Service embeddings for hybrid retrieval.

---

## Quickstart Demos

* **Agents + Vector RAG**: Minimal example connecting Agents to 23ai Vector Search with a small document set and a guarded tool.
* **SQLcl MCP**: Start SQLcl in MCP mode, register a run-sql tool, execute a parameterized query from an AI client.
* **Select AI NL→SQL**: Walkthrough converting prompts to SQL with explain and safe-execute flags.
* **OCI DS Quick Actions**: Fine-tune and deploy a small LLM, register to Model Catalog, and call from an agent.

---

## FAQ

**Q: What’s the quickest way to stand up a governed enterprise agent?**
A: Use **OCI Generative AI Agents Platform** with RAG over Object Storage or 23ai and attach the SQL tool if needed.

**Q: How do I choose between Select AI and Agents?**
A: **Select AI** if your primary need is NL→SQL or chat over a single database. **Agents** if you need multi-tool orchestration and cross-system workflows.

**Q: Do I need a separate vector database?**
A: Often no. **23ai AI Vector Search** keeps vectors in the same database as your business data for rich hybrid queries.

**Q: Can my IDE get Oracle-aware coding help?**
A: Yes, **Oracle Code Assist** supports VS Code and IntelliJ with Oracle-centric patterns.

---

## Changelog

* v0.1 Initial single-file README created with core Oracle agentic solutions and building blocks.
