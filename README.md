# Awesome-Environment-Variables-Configuration

## Top Environment Variables & Configuration Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Secrets Management, Config Injection & Self-Hosted Parameter Stores*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Environment Variables & Configuration**. These tools help teams manage secrets and configuration across development, staging, and production—covering everything from `.env` file parsers and encrypted secret vaults to runtime injection engines and feature flag systems that separate config from code.

**Examples** include Doppler, HashiCorp Vault, Infisical, AWS Parameter Store, Pulumi ESC, ConfigCat, LaunchDarkly, and open-source alternatives like Dopbase and dotenv (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted secret management, open-source configuration injection, and community-driven parameter stores—ideal for teams seeking data sovereignty and avoiding per-seat or per-secret SaaS pricing. The open-source landscape splits into **runtime secret injectors** (Dopbase) that replace `.env` files with a self-hosted server , **mature secret vaults** (HashiCorp Vault) with dynamic credentials and audit logging , and **configuration SDKs** (dotenv, fastenv) for local development workflows .

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global secrets and configuration management software market is estimated between **$2.5B and $5.1B** in 2026, expanding at a ~14–16% CAGR driven by multi-cloud infrastructure, CI/CD pipeline automation, and the explosion of machine-to-human identities. The sector is **moderately fragmented**: mega-cap hyper-scalers (AWS, Azure) and enterprise stalwarts (HashiCorp/IBM) anchor the foundational vault layer, while agile specialized vendors (Doppler, Infisical, LaunchDarkly) capture fast-growing developer mindshare with runtime injection, ephemeral secrets, and feature-flag-as-configuration workflows.

## SaaS/Hosted Platforms

| Product | Description | Valuation / Scale | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|-------------------|--------------------------|
| **[Azure App Configuration](https://azure.microsoft.com/en-us/products/app-configuration/)** | Centralized configuration store with feature flags, key-value pairs, and label-based environments. Integrates with .NET, Java, Spring, and Kubernetes. | Parent: Microsoft (~$3.1T Market Cap / ~$245B+ Revenue) | **$1.20/day** (~$36/mo) per store (Standard tier; includes 200,000 requests/day, then $0.06/10k requests) | **Free forever plan**: 1 store, 10 MB configuration storage, 1,000 requests/day (HTTP 429 after limit) |
| **[AWS Systems Manager Parameter Store](https://aws.amazon.com/systems-manager/)** | Secure hierarchical storage for configuration data and secrets. Advanced Parameters: $0.05/parameter/month; standard parameters free. Integrates natively with EC2, Lambda, ECS, and CloudFormation. | Parent: Amazon / AWS (~$2.1T Market Cap / ~$105B+ AWS Revenue) | **Standard: Free ($0)**; **Advanced: $0.05/parameter/month** (prorated hourly + $0.05 per 10,000 API interactions) | **Free forever plan**: Up to 10,000 standard parameters per account/region, 4 KB/parameter, default 40 TPS API throughput |
| **[HashiCorp Vault](https://www.hashicorp.com/)** | **The enterprise secret management standard.** Secure storage for arbitrary key/value pairs, **dynamic secrets** generated on-demand for AWS/SQL with automatic revocation, encryption-as-a-service, and detailed audit logs. Leasing and renewal for every secret. | Acquisition: IBM acquired HashiCorp for **$6.4B EV** (~$583M Revenue) | **HCP Vault Dedicated Development tier**: **~$0.62/cluster/hour** (~$450/month) | **Vault Community Edition**: Free forever (self-hosted); **HCP Vault Cloud**: $500 free trial credits for new HCP accounts (no permanent free managed cluster) |
| **[LaunchDarkly](https://launchdarkly.com/)** | **The enterprise feature management standard.** Flag targeting, percentage rollouts, A/B testing, and **MCP server for AI agents** to safely toggle flags and manage targeting rules. | **$3.0B Valuation** (~$330M total funding, ~$60M+ ARR) | **$0 base / pay-as-you-go** on Foundation tier (~$10–$12 per service connection/month, unlimited seats) | **Free forever plan (Developer)**: Unlimited seats, 1 project, 3 environments, 1,000 client-side MAU, 5 service connections, 5,000 AI runs/mo |
| **[Infisical](https://infisical.com/)** | **Open-source platform for secrets, certificates, and privileged access management.** Centralized secret sync across environments, PKI/certificate management, and AI agent credential proxying. | **$600M Valuation** (~$59M total funding raised) | **$23 per identity / month** ($20/mo billed annually on Pro plan; unlimited identities) | **Free forever plan**: Up to 5 total identities (human/machine), unlimited projects, 3 environments/project, 10 native secret syncs |
| **[Pulumi ESC](https://www.pulumi.com/esc/)** | **Environments, Secrets, and Configuration** for Pulumi and external workflows. Injects env vars and files into GitHub Actions, supports OIDC short-lived tokens, and manages hierarchical environments with revision tags. | **~$390M Valuation** (~$99M total funding, ~$20M ARR) | **$40/month base** (Essentials team tier, unlimited users, includes base credits for 500 managed resources) | **Free forever plan**: 1 user, up to 25 secrets, unlimited plaintext configurations, 10,000 ReadOpen API calls/month, unlimited environments |
| **[Doppler](https://www.doppler.com/)** | **The source-of-truth secret manager for modern dev workflows.** Centralizes environment variables across projects/configs (dev/ci/prod) with CLI injection via `doppler run --`. **Never write secrets to disk**—runtime injection only. Service Tokens for CI scoping, encrypted local fallback for offline work, and secret references to avoid duplication. | **~$45M+ Valuation** (~$28.9M total funding raised) | **$21 per user / month** ($12–$21/mo depending on annual billing on Team plan) | **Free forever plan (Developer)**: Up to 3 users, Doppler CLI runtime injection, service tokens, 5 config syncs, 3-day activity logs |
| **[ConfigCat](https://configcat.com/)** | Feature flag service with **generous free tier for up to 1,000 users**. SDKs for all major languages and frameworks (Angular, React, .NET, Next.js, etc.). | Bootstrapped / $0 external funding (~$300K+ ARR) | **$110/month** (Pro plan; unlimited team members, up to 100 feature flags, 25M config JSON downloads/mo) | **Free forever plan**: Unlimited team members, 10 feature flags, 2 products, 2 environments, ~5M config JSON downloads/month |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Dopbase](https://github.com/dopbase/dopbase)** | [![Stars](https://img.shields.io/github/stars/dopbase/dopbase?style=social&color=white)](https://github.com/dopbase/dopbase/stargazers) | **The most complete self-hosted alternative to Doppler for runtime secret injection.** **Single binary** runs a server, stores secrets per project/environment, and injects them into any command with `dopbase run`. **CLI covers the full workflow**: `init` (create project + import `.env`), `secret` (list/set/get/delete/history/rollback), `import` (bulk from dotenv/JSON/YAML/TOML), `export`, `token` (CI/runner access), **`audit`** (verify audit log integrity), `backup`/`restore` (encrypted snapshots), and `admin` (offline server administration). **Bearer tokens for machine runners and AI agents**. Encrypted runtime cache for offline resilience. **No secrets written to disk**—injection happens at process start . **Best for teams wanting Doppler-style workflows** without a SaaS dependency . |
| **[HashiCorp Vault (Community)](https://github.com/hashicorp/vault)** | [![Stars](https://img.shields.io/github/stars/hashicorp/vault?style=social&color=white)](https://github.com/hashicorp/vault/stargazers) | **The open-source foundation of enterprise secret management.** **Secure storage** with encryption before persistence—raw storage access isn't enough to read secrets. **Dynamic secrets** generated on-demand for AWS/SQL with automatic lease-based revocation. **Encryption as a service** without storing the data. **Revocation trees** for key rolling and intrusion response. **Detailed audit logs** for every access . **Trade-off**: operational complexity—Vault is a high-value target requiring careful hardening, unsealing, and HA setup. **Best for organizations needing dynamic credentials and audit trails** at enterprise scale . |
| **[dotenv](https://github.com/motdotla/dotenv)** | [![Stars](https://img.shields.io/github/stars/motdotla/dotenv?style=social&color=white)](https://github.com/motdotla/dotenv/stargazers) | **The ubiquitous `.env` file parser for Node.js.** **Does not modify already-set variables**—collisions are skipped unless `override: true` is passed. **`dotenvx`** adds encrypted `.env` files over Git, pre-commit hooks to prevent accidental commits, and Docker prebuild hooks to avoid baking secrets into images. Handles quotes, multiline values, backticks, and comments . **Best for local development and simple deployments**—not a replacement for a secret manager in production . |
| **[Infisical (OSS)](https://github.com/Infisical/infisical)** | [![Stars](https://img.shields.io/github/stars/Infisical/infisical?style=social&color=white)](https://github.com/Infisical/infisical/stargazers) | **Open-source secret management platform with certificates and privileged access.** **Self-hostable** with SDKs for all major languages, CLI, Kubernetes operator, and GitHub Actions integration . **Infisical Agent** for AI credential proxying. **PKI and KMIP server** for certificate lifecycle management . **Best for teams wanting a modern open-source secret platform** with broad integration coverage . |
| **[fastenv](https://github.com/br3ndonland/fastenv)** | [![Stars](https://img.shields.io/github/stars/br3ndonland/fastenv?style=social&color=white)](https://github.com/br3ndonland/fastenv/stargazers) | **Async Python `.env` loader with `find_dotenv` support.** Loads `.env` files into a `DotEnv` model with proper type handling. **`find_source=True`** walks up from cwd to locate the file. **`dotenv_values()`** returns a plain dict for simple use cases. Built on AnyIO for async web frameworks (FastAPI, Starlette) . **Best for Python teams** wanting modern async dotenv handling . |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Pulumi ESC (SDK)](https://github.com/pulumi/esc)** | — | **Open-source SDK for Pulumi ESC environments.** .NET SDK (`Pulumi.Esc.Sdk`) for listing, opening, and reading environment configs and secrets from C#/F#/VB. Supports creating/updating/deleting environment definitions, revision tags, and validation . **Best for teams already on Pulumi** wanting programmatic access to ESC environments . |
| **[ConfigCat (SDKs)](https://github.com/configcat)** | — | **Open-source SDKs for ConfigCat feature flags.** Sample apps for Angular, React, Next.js, .NET, React Native, Godot, and OpenFeature demonstrate integration patterns . **Best for teams using ConfigCat** wanting reference implementations across frameworks . |

**Frameworks for building custom systems**: Choose **Dopbase** for a self-hosted Doppler replacement with runtime injection and audit integrity , **HashiCorp Vault** for dynamic secrets and enterprise-grade audit at scale , or **dotenv/dotenvx** for local development with encrypted `.env` files —all without per-seat SaaS fees for basic secret injection.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Secret management tools handle the keys to your entire infrastructure; enforce strong authentication (MFA), least-privilege access, and **never write secrets to plaintext files in production**. A compromised secret store exposes every connected system.
- **Doppler explicitly recommends against writing secrets to disk**—prefer runtime injection (`doppler run --`) or mount features over `doppler secrets download` to a real file . **HashiCorp Vault's dynamic secrets** reduce blast radius by generating and revoking credentials on demand, but Vault itself becomes a high-value target requiring careful hardening . **Dopbase** provides a self-hosted Doppler alternative with `audit` integrity verification and encrypted backups . **dotenv does not modify already-set variables** by default—collisions are skipped unless `override: true` is passed . **ConfigCat offers a genuine free tier** for up to 1,000 users with unlimited flags and all SDKs . **LaunchDarkly and Doppler are quote-only** at team scale. **Validate whether you need runtime injection (Dopbase, Doppler), dynamic credentials (Vault), or simple local `.env` parsing (dotenv)** before committing.

---

**Made for developers, platform engineers, and security teams managing configuration and secrets.**  
Let's make environment variables and configuration more open, secure, and injection-first.
