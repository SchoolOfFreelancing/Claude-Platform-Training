# Claude AI Platform Training Module

A comprehensive, hands-on, 5-day training program for the **full management and operation of the Claude AI Platform** — covering the Claude Developer Platform (API), Claude Code, Claude.ai/Claude Cowork for teams, and the administrative, security, and governance controls needed to run Claude at organizational scale.

![Duration](https://img.shields.io/badge/Duration-5%20Days-blue)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-orange)
![Format](https://img.shields.io/badge/Format-Hands--on%20Labs-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> ⚠️ **Living document notice:** Anthropic ships new models, plans, and console features frequently. This README defines the training *structure and objectives*; instructors and participants should verify current product specifics (model names, plan tiers, limits, pricing) against official documentation before each cohort — see [Additional Resources](#-additional-resources).

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Learning Objectives](#-learning-objectives)
- [Audience](#-audience)
- [Prerequisites](#-prerequisites)
- [Lab Environment](#-lab-environment)
- [Training Schedule](#-training-schedule)
  - [Day 1: Platform Landscape & Console Fundamentals](#day-1-platform-landscape--console-fundamentals)
  - [Day 2: Building with the API](#day-2-building-with-the-api)
  - [Day 3: Claude Code & Agentic Workflows](#day-3-claude-code--agentic-workflows)
  - [Day 4: Organization Management, Security & Governance](#day-4-organization-management-security--governance)
  - [Day 5: Scaling, Cost Management & Production Operations](#day-5-scaling-cost-management--production-operations)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Lab Exercises](#-lab-exercises)
- [Assessment & Certification](#-assessment--certification)
- [Reference Architecture](#-reference-architecture)
- [Troubleshooting Guide](#-troubleshooting-guide)
- [Additional Resources](#-additional-resources)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

This training module prepares administrators, developers, and platform teams to fully manage the **Claude AI Platform** across its surfaces: the Console (organization/workspace administration), the Claude Developer Platform (API), Claude Code (agentic coding), and Claude.ai/Claude Cowork (end-user products). The course combines conceptual instruction with hands-on labs, culminating in participants standing up a governed, cost-monitored, production-ready Claude deployment for an organization — complete with role-based access, security controls, and usage reporting.

## 🎓 Learning Objectives

By the end of this training, participants will be able to:

- Navigate the Claude Console: organizations, workspaces, API keys, and the model catalog
- Make robust API calls to Claude (Messages API), including streaming, system prompts, and multi-turn conversations
- Select the right Claude model for a given task based on capability, latency, and cost trade-offs
- Use tool use (function calling), vision, and extended thinking features appropriately
- Install, configure, and operate Claude Code for agentic software development workflows, including MCP server integration
- Understand and evaluate Claude Cowork and other agentic/desktop surfaces for non-developer knowledge work
- Administer an organization: user provisioning, roles and permissions, SSO/SCIM integration, and workspace segmentation
- Implement usage governance: rate limits, spend limits, and per-workspace budget controls
- Apply security and compliance best practices: API key rotation, audit logs, data retention settings, and content safety configuration
- Monitor usage, cost, and performance across teams; build internal reporting and chargeback processes
- Design a rollout and change-management plan for introducing Claude across an organization

## 👥 Audience

- Platform/IT administrators responsible for provisioning and governing AI tools org-wide
- Developers and engineering teams building products on the Claude API
- DevOps/engineering managers evaluating or rolling out Claude Code
- Security, compliance, and procurement stakeholders involved in AI platform governance
- Technical leads coordinating a company-wide Claude adoption

## ✅ Prerequisites

**Required:**
- Basic familiarity with REST APIs and JSON
- Comfort with the command line
- For Day 3–4: administrative or IT-admin experience (SSO, identity provider concepts) is helpful

**Recommended:**
- Working proficiency in at least one programming language (Python, TypeScript, or similar)
- Prior exposure to SaaS admin consoles (user/role management, SSO)
- Basic understanding of cloud cost/usage monitoring concepts

**Not required but helpful:** Experience with another LLM provider's platform or API, prior exposure to Git and CI/CD tooling

## 🖥️ Lab Environment

Each participant is provisioned with an isolated lab environment consisting of:

| Component | Specification |
|---|---|
| Dev Workstation | Cloud IDE (VS Code Server) with a supported SDK language runtime |
| Claude Access | Sandboxed Console organization with a capped usage budget per participant |
| Identity Provider | Mock IdP (e.g., Okta/Azure AD sandbox) for SSO/SCIM labs |
| Claude Code | Pre-installed in the lab workstation, with a sample repository |
| Supporting Services | Git server, a small internal API/service for tool-use labs, logging/reporting dashboard |
| Access | Browser-based terminal/IDE, Console admin access scoped to the lab organization |

> 💡 A cloud-based lab or a fully local (Docker Compose) option is provided — see [`/labs/environment-setup`](./labs/environment-setup).

---

## 🗓️ Training Schedule

### Day 1: Platform Landscape & Console Fundamentals

**Morning — Concepts**
- Claude Platform landscape: Claude.ai (consumer/pro/team), Claude Developer Platform (API), Claude Code, and Claude Cowork — what each is for
- Console fundamentals: organizations, workspaces, members, and API keys
- Model catalog overview and how to choose a model for a given workload (capability vs. latency vs. cost)
- Plan tiers and account types at a high level (individual, team, enterprise)

**Afternoon — Hands-on Labs**
- **Lab 1.1:** Set up a Console organization, create a workspace, and generate your first API key
- **Lab 1.2:** Send your first API request and inspect the response structure
- **Lab 1.3:** Explore the model catalog and compare responses/latency across models for the same prompt
- **Lab 1.4:** Tour the Console's usage dashboard and billing pages

**Deliverable:** A configured lab organization with a workspace, API key, and a documented model-selection rationale for a sample use case.

---

### Day 2: Building with the API

**Morning — Concepts**
- The Messages API: system prompts, multi-turn conversations, and streaming
- Prompt engineering fundamentals for Claude: clear instructions, examples, XML tags, and structured output patterns
- Vision inputs and multimodal prompting
- Tool use (function calling): defining tools, handling tool-call responses, and multi-step tool loops
- Extended thinking and when to use it
- Prompt caching and batching for cost/latency optimization

**Afternoon — Hands-on Labs**
- **Lab 2.1:** Build a multi-turn conversational app with streaming responses
- **Lab 2.2:** Design and test a structured-output prompt (e.g., JSON extraction) with clear success criteria
- **Lab 2.3:** Implement tool use — connect Claude to a sample internal API via a defined tool schema
- **Lab 2.4:** Add prompt caching to reduce latency/cost on a repeated-context workload
- **Lab 2.5:** Benchmark and document cost/latency trade-offs across two model choices for the same task

**Deliverable:** A working tool-use-enabled application with documented prompt design decisions and a cost/latency benchmark.

---

### Day 3: Claude Code & Agentic Workflows

**Morning — Concepts**
- Claude Code overview: installation, authentication, and supported environments (terminal, IDE extensions, desktop app)
- Core workflows: understanding codebases, fixing bugs, refactoring, writing tests, generating documentation
- Configuration: project-level settings, permissions, and custom slash commands
- Extending Claude Code with the Model Context Protocol (MCP): connecting internal tools and data sources
- Subagents and multi-step agentic task delegation
- Claude Cowork for non-developer, multi-step knowledge work (research, document generation, cross-tool tasks)

**Afternoon — Hands-on Labs**
- **Lab 3.1:** Install and configure Claude Code against the lab's sample repository
- **Lab 3.2:** Use Claude Code to onboard onto an unfamiliar codebase and fix a seeded bug
- **Lab 3.3:** Connect an MCP server (e.g., a Git host or issue tracker) and use it from Claude Code
- **Lab 3.4:** Create a custom slash command and a project-scoped configuration for team standardization
- **Lab 3.5:** Explore a Claude Cowork-style multi-step task and compare it against a developer-focused Claude Code task

**Deliverable:** A documented Claude Code setup (config + MCP integration + custom command) suitable for team-wide rollout, plus a short comparison memo on when to use Claude Code vs. Cowork vs. the raw API.

---

### Day 4: Organization Management, Security & Governance

**Morning — Concepts**
- Organization structure: workspaces, roles, and permission boundaries
- Identity and access: SSO and SCIM provisioning, member lifecycle management
- API key management: scoping, rotation policies, and secrets handling
- Data governance: data retention settings, training/opt-out controls, and audit logging
- Content safety: usage policies and platform safety tooling relevant to enterprise deployments
- Compliance considerations or organizations evaluating Claude (data residency, certifications) — pointers to current documentation

**Afternoon — Hands-on Labs**
- **Lab 4.1:** Configure SSO against the mock Identity Provider and test SCIM-based user provisioning
- **Lab 4.2:** Design a workspace and role structure for a multi-team organization (e.g., separate workspaces per product team with scoped API keys)
- **Lab 4.3:** Implement an API key rotation policy and audit-log review process
- **Lab 4.4:** Review and configure data retention and privacy-relevant settings for the lab organization
- **Lab 4.5:** Draft an internal AI usage policy covering acceptable use, data handling, and escalation paths

**Deliverable:** A governed lab organization with SSO, scoped workspaces/roles, a key-rotation runbook, and a written internal usage policy.

---

### Day 5: Scaling, Cost Management & Production Operations

**Morning — Concepts**
- Usage and cost monitoring: reading Console usage reports, per-workspace attribution, chargeback models
- Rate limits and capacity planning for production workloads; handling throttling gracefully
- Reliability patterns: retries/backoff, timeouts, and fallback strategies
- Observability: logging, tracing, and building internal dashboards for latency/cost/error rate
- Change management: rolling out new models, deprecations, and version-pinning strategy
- Building an internal center of excellence: enablement, support channels, and feedback loops

**Afternoon — Hands-on Labs**
- **Lab 5.1:** Build a usage/cost dashboard aggregating API and workspace-level data
- **Lab 5.2:** Implement retry/backoff and graceful degradation for rate-limited requests
- **Lab 5.3:** Set up alerting for budget thresholds and anomalous usage spikes
- **Lab 5.4:** Draft a model-upgrade/version-pinning runbook for production applications
- **Lab 5.5 (Capstone):** Present a complete organizational rollout plan — Console structure, security controls, developer tooling (API + Claude Code), cost governance, and an enablement plan — for a fictional company scenario

**Deliverable (Capstone Project):** A full Claude Platform management plan and lab implementation: governed org structure, working API/Claude Code integrations, monitoring dashboard, and a written rollout/enablement strategy.

---

## 📁 Repository Structure

```
claude-platform-training/
├── README.md
├── slides/                        # Day-by-day presentation decks
│   ├── day1-platform-fundamentals.pdf
│   ├── day2-building-with-the-api.pdf
│   ├── day3-claude-code-and-agents.pdf
│   ├── day4-governance-and-security.pdf
│   └── day5-scaling-and-operations.pdf
├── labs/
│   ├── environment-setup/         # Docker Compose / Terraform lab bootstrap
│   ├── day1/
│   ├── day2/
│   ├── day3/
│   ├── day4/
│   └── day5/
├── app/
│   ├── api-client/                 # Reference API client wrappers
│   ├── tool-use-examples/
│   └── prompt-library/
├── claude-code/
│   ├── sample-repo/                # Seeded repository with bugs/tasks for Day 3
│   ├── mcp-servers/                 # Example MCP server configs
│   └── custom-commands/
├── governance/
│   ├── sso-scim/                    # Mock IdP configs
│   ├── policy-templates/            # Sample usage policy, key-rotation runbook
│   └── reporting/                   # Usage/cost dashboard starter
├── solutions/                        # Reference solutions for each lab
└── docs/
    ├── troubleshooting.md
    ├── architecture-diagrams/
    └── glossary.md
```

## 🚀 Getting Started

1. **Clone this repository:**
   ```bash
   git clone https://github.com/<your-org>/claude-platform-training.git
   cd claude-platform-training
   ```

2. **Provision your lab environment:**
   ```bash
   cd labs/environment-setup
   docker compose up -d
   ```

3. **Configure your credentials:**
   ```bash
   cp .env.example .env
   # Add your sandboxed ANTHROPIC_API_KEY and lab org details to .env
   ```

4. **Verify prerequisites:**
   ```bash
   ./labs/environment-setup/scripts/check-prereqs.sh
   ```

5. **Start with Day 1:**
   ```bash
   cd labs/day1
   cat README.md
   ```

## 🧪 Lab Exercises

Each day's lab folder (`labs/dayN/`) contains:
- `README.md` — step-by-step instructions and success criteria
- `starter/` — starting-point code and configs
- `hints.md` — progressive hints for anyone who gets stuck
- Corresponding reference solution in `solutions/dayN/`

Labs are designed to be completed sequentially, with each day building on the organizational and technical setup created the day before.

## 📜 Assessment & Certification

- **Daily checkpoints:** short knowledge checks at the end of each day
- **Capstone project (Day 5):** graded on completeness of the governance plan, technical implementation, and clarity of the enablement/rollout strategy
- **Certificate of completion** issued to participants who complete all daily labs and the capstone project

## 🏗️ Reference Architecture

The course builds toward the following organizational management structure:

```
                     ┌─────────────────────────┐
                     │   Claude Console          │
                     │  (Organization root)      │
                     └──────────────┬────────────┘
                                    │
             ┌──────────────────────┼──────────────────────┐
             │                      │                      │
   ┌─────────▼─────────┐  ┌─────────▼─────────┐  ┌─────────▼─────────┐
   │  Workspace: Eng     │  │  Workspace: Data   │  │  Workspace: Ops    │
   │  (scoped API keys,  │  │  (scoped API keys, │  │  (scoped API keys, │
   │   budget limits)    │  │   budget limits)   │  │   budget limits)   │
   └─────────┬─────────┘  └─────────┬─────────┘  └─────────┬─────────┘
             │                      │                      │
   ┌─────────▼─────────┐  ┌─────────▼─────────┐  ┌─────────▼─────────┐
   │  API Applications  │  │  Claude Code        │  │  Reporting /       │
   │  (Messages API,     │  │  (dev workflows,    │  │  Cost Dashboard    │
   │   tool use)          │  │   MCP servers)      │  │                    │
   └────────────────────┘  └────────────────────┘  └────────────────────┘

     Cross-cutting: SSO/SCIM, Audit Logs, Data Retention Policy, Usage Alerts
```

See [`docs/architecture-diagrams/`](./docs/architecture-diagrams) for detailed diagrams per day.

## 🛠️ Troubleshooting Guide

Common issues and resolutions are documented in [`docs/troubleshooting.md`](./docs/troubleshooting.md), covering:
- Rate limit and throttling errors under load
- API key scoping and permission errors across workspaces
- SSO/SCIM provisioning mismatches
- MCP server connection failures in Claude Code
- Unexpected cost spikes and how to trace them to a workspace/key
- Tool-use loops and malformed tool-call arguments

## 📚 Additional Resources

> Product details (models, plans, limits, and console features) change frequently — always confirm against current official docs before teaching or deploying.

- Claude Developer Platform documentation: https://docs.claude.com
- Claude Code documentation: https://docs.claude.com/en/docs/claude-code/overview
- Claude.ai / Claude Cowork support: https://support.claude.com
- Anthropic product news: https://www.anthropic.com/news
- Enterprise/sales inquiries: https://www.anthropic.com/contact-sales

## 🤝 Contributing

Contributions to improve labs, fix errata, or add advanced modules are welcome. Please open an issue or submit a pull request following the guidelines in `CONTRIBUTING.md`.

## 📄 License

This training material is released under the [MIT License](./LICENSE).

---

*Questions or feedback? Open an issue in this repository or contact the training team.*
