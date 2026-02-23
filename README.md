# Universal GitHub Repository Analysis Prompt Framework

> A systematic, security-first prompt framework to analyze **any** GitHub repository —
> whether it's a tool, library, microservice, ML pipeline, or full-stack application.

[![Version](https://img.shields.io/badge/version-1.0-6366f1?style=flat-square)](.)
[![Edition](https://img.shields.io/badge/edition-Universal-06b6d4?style=flat-square)](.)
[![Focus](https://img.shields.io/badge/focus-Cybersecurity%20%7C%20DevSecOps%20%7C%20NetAdmin-8b5cf6?style=flat-square)](.)
[![License](https://img.shields.io/badge/license-MIT-22c55e?style=flat-square)](LICENSE)
[![Prompts](https://img.shields.io/badge/prompts-86-f97316?style=flat-square)](prompts/github-repo-analysis-prompts.csv)
[![Year](https://img.shields.io/badge/updated-2026-ec4899?style=flat-square)](.)

---

## Table of Contents

- [Overview](#overview)
- [Why This Framework Exists](#why-this-framework-exists)
- [Who This Is For](#who-this-is-for)
- [Framework Structure](#framework-structure)
- [Quick Start Workflow](#quick-start-workflow)
- [Section Reference](#section-reference)
  - [Section 1 — Core Understanding](#section-1--core-understanding)
  - [Section 2 — Architecture Analysis](#section-2--architecture-analysis)
  - [Section 3 — Data Flow Mapping](#section-3--data-flow-mapping)
  - [Section 4 — Code Architecture](#section-4--code-architecture)
  - [Section 5 — Storage and Persistence](#section-5--storage-and-persistence)
  - [Section 6 — Security Audit](#section-6--security-audit)
  - [Section 7 — Integrations and APIs](#section-7--integrations-and-apis)
  - [Section 8 — Network Analysis](#section-8--network-analysis)
  - [Section 9 — Configuration Review](#section-9--configuration-review)
  - [Section 10 — Testing and CI/CD](#section-10--testing-and-cicd)
  - [Section 11 — Deployment and Operations](#section-11--deployment-and-operations)
  - [Section 12 — Code Quality and Technical Debt](#section-12--code-quality-and-technical-debt)
  - [Section 13 — Specialist Probes](#section-13--specialist-probes)
- [Files in This Repository](#files-in-this-repository)
- [Usage Tips](#usage-tips)
- [Security Notice](#security-notice)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This framework provides **86 structured prompts** organized across 13 sections, designed to give you a thorough, repeatable lens for analyzing open-source GitHub repositories before trusting them in any production, security, or infrastructure context.

It is built for use with AI assistants (Claude, GPT-4, Gemini, etc.) — paste a repo's README or code, then work through the prompts in sequence to surface architecture risks, security vulnerabilities, operational gaps, and dependency concerns.

```
Foundation → Architecture → Data Flow → Security → Network → Deployment → Specialist Probes
```

---

## Why This Framework Exists

The open-source ecosystem in 2026 moves faster than any single team can manually review. Supply chain attacks have become a primary threat vector. AI-generated code floods public repositories. Regulatory frameworks now require demonstrable due diligence over every open-source component your organization ships or depends on.

**Clicking "clone and run" is not an option anymore.**

This framework gives engineers, analysts, and administrators a consistent, security-first review methodology — regardless of the repository type, language, or domain.

---

## Who This Is For

| Role | Primary Sections |
|---|---|
| Security Engineer / Analyst | 6, 7, 8, 13 |
| DevSecOps Engineer | 1, 6, 9, 10, 11 |
| Network Administrator | 8, 9, 11 |
| Software Architect | 2, 3, 4, 12 |
| ML / AI Engineer | 2 (ML probe), 3, 13 |
| Infrastructure / DevOps | 5, 9, 11, 13 |
| General Developer | 1, 2, 10, 12 |

---

## Framework Structure

```
Universal GitHub Repo Analysis Prompt Framework
│
├── Section 1   Core Understanding          (P001–P005)   Foundation questions
├── Section 2   Architecture Analysis       (P006–P011)   System design & concurrency
├── Section 3   Data Flow Mapping           (P012–P016)   Input → Processing → Output
├── Section 4   Code Architecture           (P017–P022)   Modules, algorithms, detection
├── Section 5   Storage & Persistence       (P023–P028)   DBs, caching, retention
├── Section 6   Security Audit              (P029–P041)   Auth, injection, secrets, supply chain
├── Section 7   Integrations & APIs         (P042–P045)   External services, webhooks
├── Section 8   Network Analysis            (P046–P051)   Ports, protocols, firewall rules
├── Section 9   Configuration Review        (P052–P056)   Config files, env vars, secrets mgmt
├── Section 10  Testing & CI/CD             (P057–P061)   Test coverage, pipelines, scanning
├── Section 11  Deployment & Operations     (P062–P068)   Setup, runbooks, hardening
├── Section 12  Code Quality & Tech Debt    (P069–P076)   Patterns, entry points, risks
└── Section 13  Specialist Probes           (P077–P086)   MITRE, ML/AI, Network Tools, IaC
```

---

## Quick Start Workflow

**Step 1** — Provide the repository URL or paste the README/code into your AI chat.

**Step 2** — Use the prompts in sequence: Foundation → Security → Deployment.

**Step 3** — For security or DevSecOps repositories, prioritize **Sections 6, 8, 9, and 13**.

**Step 4** — Adapt bracketed placeholders `[like this]` to your specific context.

**Step 5** — Use follow-up probes from **Section 13** to drill deeper into specialist findings.

> **Always run unknown repositories in an isolated environment first.
> Complete Section 6 (Security Audit) before deploying anything to production networks.**

---

## Section Reference

### Section 1 — Core Understanding

Start here for every repository. These five prompts establish what the system is, who it serves, and whether it is actively maintained.

| ID | Sub-Category | Prompt |
|---|---|---|
| P001 | Foundation | What problem does this repository solve? Describe the target user and primary use case in 2–3 sentences. |
| P002 | Foundation | What is the full tech stack? List every language, framework, runtime, and major library used. Explain WHY each was chosen over alternatives. |
| P003 | Foundation | Is this a library, CLI tool, web service, agent, daemon, plugin, or framework? What is its deployment model (self-hosted, SaaS, embedded, etc.)? |
| P004 | Foundation | Who are the intended operators — developers, sysadmins, security analysts, end-users? What level of technical expertise is assumed? |
| P005 | DevSecOps Probe | Is this project actively maintained? When was the last commit, release, or security patch? Are there open CVEs or unpatched vulnerability reports? |

---

### Section 2 — Architecture Analysis

Understand how the system is built before you trust it.

| ID | Sub-Category | Prompt |
|---|---|---|
| P006 | System Overview | Explain the overall architecture from a bird's-eye view. What are the major components and how do they connect? |
| P007 | System Overview | Draw the system as a component diagram in plain text. Label each component, its role, and the direction of dependencies. |
| P008 | Concurrency | What is the threading/concurrency model? Are components synchronous, asynchronous, event-driven, or multi-threaded? |
| P009 | Reliability | What are the critical paths — the sequences of operations where a failure would have the highest impact? |
| P010 | Reliability | Are there any single points of failure? Does the system degrade gracefully or fail hard? |
| P011 | ML/AI Repos | If this repo contains ML models: What models are used? How are they served? What is the inference pipeline from raw input to output? |

---

### Section 3 — Data Flow Mapping

Follow the data everywhere — from entry to exit.

| ID | Sub-Category | Prompt |
|---|---|---|
| P012 | General | Walk me through how data enters, moves through, and exits the system. Be specific about formats, transformations, and handoffs. |
| P013 | Inputs | What are the data sources? What formats are accepted (JSON, CSV, binary, Syslog, PCAP, etc.)? |
| P014 | Processing | What processing or transformation steps occur on the data? Are there enrichment, normalization, filtering, or classification stages? |
| P015 | Outputs | What does the system output? Where does output go and in what format? |
| P016 | Security/SIEM Probe | If this is a security tool: How does data flow from raw event ingestion through detection logic to alert generation? |

---

### Section 4 — Code Architecture

Understand modules, algorithms, and which functions carry the most risk.

| ID | Sub-Category | Prompt |
|---|---|---|
| P017 | Modules | List every core module or package and describe its responsibility in one sentence each. |
| P018 | Module Communication | How do the modules communicate — function calls, message queues, REST, gRPC, pub/sub? |
| P019 | Business Logic | What are the key algorithms or business logic rules? Explain each at a conceptual level. |
| P020 | Critical Functions | What are the most complex or critical functions? Which ones, if buggy, would cause the most damage? |
| P021 | Detection Tools | What are the detection rules, signatures, heuristics, or ML decision boundaries used? |
| P022 | Alert Scoring | How are alerts or findings scored, prioritized, or ranked? What is the confidence scoring model? |

---

### Section 5 — Storage and Persistence

Audit what is stored, where, and how it is protected.

| ID | Sub-Category | Prompt |
|---|---|---|
| P023 | Databases | What databases or storage systems are used? Why was each chosen? |
| P024 | Data Model | Describe the data model or schema. What are the main entities and their relationships? |
| P025 | Caching | What data is cached vs. persistently stored? What is the cache invalidation strategy? |
| P026 | Retention | What is the data retention policy? Are there TTL settings, rotation, archival, or purge mechanisms? |
| P027 | Security Probe | What sensitive data is stored? Is it encrypted at rest? What key management approach is used? |
| P028 | Availability | What happens if the storage backend is unavailable? Fail-open or fail-closed behavior? |

---

### Section 6 — Security Audit

**The most critical section. Complete this before any production deployment.**

| ID | Sub-Category | Prompt |
|---|---|---|
| P029 | Authentication | How is authentication implemented? What methods are supported? Where are credentials validated? |
| P030 | Authorization | How is authorization enforced? RBAC, ABAC, or ACL? Is it checked consistently across all endpoints? |
| P031 | Attack Surface | What is the attack surface? List every external-facing interface an attacker could target. |
| P032 | Input Validation | What input validation is performed? Any unsanitized input reaching a database, shell command, or file path? |
| P033 | Injection Vulnerabilities | Identify potential injection points: SQL, command, path traversal, SSTI, SSRF, or XXE. |
| P034 | Secrets Management | How are secrets managed? Any hardcoded in source files, config files, or docker-compose? |
| P035 | Secrets Audit | Run a conceptual secrets audit: any cloud keys, private keys, passwords, or tokens accidentally committed? |
| P036 | Supply Chain | What third-party dependencies are used? Any known CVEs? How are dependencies pinned? |
| P037 | Supply Chain Runtime | Does this project pull from external sources at runtime? Supply chain injection risk? |
| P038 | Data Protection | Is sensitive data protected in transit? TLS enforced everywhere? Any cleartext paths? |
| P039 | Logging | Could logs contain sensitive data (passwords, tokens, PII) that should be masked? |
| P040 | Container Security | What base images are used? Do containers run as root? Are Linux capabilities dropped? |
| P041 | Privileges | What system calls or kernel interfaces does this software require? Elevated privileges needed? |

---

### Section 7 — Integrations and APIs

Map every external dependency and integration point.

| ID | Sub-Category | Prompt |
|---|---|---|
| P042 | External Services | What external services or APIs does this system call? Cloud providers, SaaS, identity providers, threat intel feeds? |
| P043 | Exposed APIs | What APIs does this project expose? List all endpoints with method, path, auth requirement, and purpose. |
| P044 | Webhooks | What webhook receivers or event listeners are implemented? What data do they accept and from which sources? |
| P045 | Resilience | What happens if an external dependency is unavailable? Retries, circuit breakers, fallbacks, or hard failures? |

---

### Section 8 — Network Analysis

Build your firewall policy and network segmentation plan from these prompts.

| ID | Sub-Category | Prompt |
|---|---|---|
| P046 | Ports | What TCP/UDP ports does this application listen on? Which should be firewalled from public access? |
| P047 | Outbound Connections | What outbound network connections does this application make? Destination hosts, ports, and protocols? |
| P048 | Protocols | What network protocols does this system speak natively (HTTP/2, WebSocket, MQTT, AMQP, Kafka, Syslog, SNMP)? |
| P049 | Firewall Rules | What network flows are required? Help me write firewall allow-rules (source, destination, port, protocol). |
| P050 | Active Probing | Does this system perform network scanning, probing, packet capture, or traffic analysis? |
| P051 | TLS/mTLS | Is TLS/mTLS used for all network communications? Is certificate validation enforced or can it be disabled? |

---

### Section 9 — Configuration Review

Misconfiguration is one of the most common production security failures.

| ID | Sub-Category | Prompt |
|---|---|---|
| P052 | Config Files | List all configuration files. What does each control and which settings are security-sensitive? |
| P053 | Environment Variables | What environment variables are used? Which are required vs. optional? Which contain sensitive data? |
| P054 | Tunable Parameters | What parameters affect detection sensitivity, performance, or security posture? Safe defaults vs. risky values? |
| P055 | Misconfiguration Risk | Any config options that, if misconfigured, would create a security risk (disabled TLS, debug mode, open CORS)? |
| P056 | Secrets Integrations | What secret management integrations are supported (Vault, AWS Secrets Manager, Azure Key Vault, K8s Secrets)? |

---

### Section 10 — Testing and CI/CD

Understand test coverage and what automated security scanning exists.

| ID | Sub-Category | Prompt |
|---|---|---|
| P057 | Test Coverage | What types of tests exist (unit, integration, e2e, fuzzing, load, SAST)? What is the overall test coverage? |
| P058 | Running Tests | How do I run the full test suite? Provide exact commands including setup, env vars, and required services. |
| P059 | Security Tests | Are there security-specific tests: fuzzing, authentication bypass, injection tests, privilege escalation checks? |
| P060 | CI/CD | What CI/CD pipeline is used? What security scanning steps are included (SAST, DAST, dependency scan, container scan)? |
| P061 | Detection Simulation | How does the test framework work for detection? What attack scenarios are available? |

---

### Section 11 — Deployment and Operations

Everything you need to deploy safely and operate reliably.

| ID | Sub-Category | Prompt |
|---|---|---|
| P062 | Prerequisites | What are the complete infrastructure requirements (OS, CPU arch, RAM, disk, GPU, network, external services)? |
| P063 | Setup Guide | Provide the step-by-step setup guide: clone, install, configure, initialize, and start the service. |
| P064 | Run Modes | What run modes or profiles exist (dev, staging, production, debug, offline)? How do they differ in security posture? |
| P065 | Containers | Is there a Docker or Kubernetes deployment? Container setup, volumes, service accounts, network policies? |
| P066 | Runbooks | What are the operational runbooks? Health checks, log viewing, service restart, rolling updates? |
| P067 | Observability | What monitoring and observability is built in? Metrics, tracing, health endpoints, log formats, alerting rules? |
| P068 | Hardening Checklist | Generate a production hardening checklist: network exposure, auth settings, logging, secrets, containers, patching. |

---

### Section 12 — Code Quality and Technical Debt

Assess the long-term maintainability and hidden risk in the codebase.

| ID | Sub-Category | Prompt |
|---|---|---|
| P069 | Folder Structure | Describe the top-level folder structure. What does each directory contain and what concern does it own? |
| P070 | Design Patterns | What design patterns are used (MVC, event-driven, CQRS, actor model, microservices, monorepo)? |
| P071 | Entry Point | Where is the entry point? Trace the startup sequence from entry through initialization to steady-state. |
| P072 | Abstractions | What are the main abstractions or interfaces? How do they promote modularity and testability? |
| P073 | Limitations | What are the known limitations (scalability caps, unsupported platforms, unhandled edge cases)? |
| P074 | Technical Debt | What technical debt is visible? TODO/FIXME/HACK comments, deprecated APIs, architectural shortcuts? |
| P075 | Improvement Priority | If you owned this codebase, what would you improve first? Prioritized by impact and effort. |
| P076 | Top Security Risks | What are the top 3 security risks you would address immediately before deploying to a production network? |

---

### Section 13 — Specialist Probes

Domain-specific deep-dives for SIEM, ML/AI, Network Tools, and IaC repositories.

| ID | Sub-Category | Prompt |
|---|---|---|
| P077 | MITRE ATT&CK | How does this map to the MITRE ATT&CK framework? Which TTPs can it detect, and which are gaps? |
| P078 | Threat Detection | What APT behaviors, lateral movement, or persistence mechanisms does this tool detect? Confidence score model? |
| P079 | False Positives | What is the false positive rate strategy? How does the system handle alert fatigue and tune thresholds per environment? |
| P080 | Packet Capture | What packet capture or network monitoring capabilities exist? Requires libpcap, raw sockets, eBPF, or AF_PACKET? |
| P081 | Deployment Mode | Passive (tap/span) or inline deployment? Latency and throughput characteristics? |
| P082 | ML Model Choice | What ML model architecture is used? Why chosen over alternatives (LightGBM vs XGBoost, LSTM vs Transformer)? |
| P083 | Class Imbalance | How does the system handle class imbalance (rare attack events vs. normal traffic)? SMOTE, weighted loss? |
| P084 | Model Retraining | How is the model retrained as threats evolve? Feedback loop, active learning, or manual retraining workflow? |
| P085 | IaC Tools | What IaC tools are used (Terraform, Ansible, Pulumi, CloudFormation)? Cloud resources provisioned? IAM permissions? |
| P086 | Infrastructure Testing | How are infrastructure changes tested before production? Is there a drift detection mechanism? |

---

## Files in This Repository

```
├── README.md                                  # This file
├── prompts/
│   └── github-repo-analysis-prompts.csv      # All 86 prompts in structured CSV format
├── docs/
│   └── github-repo-analysis-blog.md          # Full blog post (Medium-ready)
└── assets/
    └── featured-image.html                    # 700x360px featured banner image
```

### CSV Column Reference

The `github-repo-analysis-prompts.csv` file contains the following columns:

| Column | Description |
|---|---|
| `Prompt_ID` | Unique identifier (P001–P086) |
| `Section` | Section number (1–13) |
| `Category` | High-level category name |
| `Sub_Category` | Specific topic within the category |
| `Prompt_Text` | The full prompt text, ready to paste into any AI assistant |

---

## Usage Tips

**For a quick security review**, run Sections 1, 6, and 8 in sequence. This covers foundation, the full security audit, and network exposure — the three highest-leverage areas before making any deployment decision.

**For a thorough production readiness review**, run all 13 sections in order. Budget 2–4 hours for a moderately complex repository.

**For specialist repositories** (SIEM, EDR, ML security tools, network analyzers), always include Section 13 after the core sections.

**Adapt the prompts** — the bracketed placeholder style `[like this]` is intentional. Replace these with your specific repo name, environment, or constraints to get more targeted analysis from the AI assistant.

**Document your findings** — use the section structure as a report template. Fill in the AI's responses section by section to build a reproducible security assessment artifact.

---

## Security Notice

> **Always run unknown repositories in an isolated environment before performing any analysis that involves executing code.**
>
> This framework is designed for prompt-based, static analysis using an AI assistant. It does not require running the target repository's code. However, if you choose to run code as part of your analysis, use a fully isolated virtual machine or container with no connectivity to production systems.
>
> Findings from this framework are hypotheses that require validation. Do not make production deployment decisions based solely on AI-assisted prompt analysis. Complement this framework with dynamic testing, professional penetration testing, and formal security audits for high-risk systems.

---

## Contributing

Contributions are welcome. If you have additional specialist probes, domain-specific sections, or improvements to existing prompts, please open a pull request with:

1. A clear description of the new or modified prompt
2. The target audience or repository type it addresses
3. The section it belongs to, or a proposed new section with justification

Please follow the existing `Prompt_ID` and column naming conventions in the CSV file.

---

## License

This framework is released under the MIT License. See [LICENSE](LICENSE) for full terms.

---

**Use responsibly. Always analyze unknown repositories in isolated environments before production deployment.**

*Universal GitHub Repository Analysis Prompt Framework — Cybersecurity / DevSecOps / Network Admin Edition*
*Version 1.0 | Updated February 2026*
