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
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[Doppler](https://www.doppler.com/)** | **The source-of-truth secret manager for modern dev workflows.** Centralizes environment variables across projects/configs (dev/ci/prod) with CLI injection via `doppler run --`. **Never write secrets to disk**—runtime injection only. Service Tokens for CI scoping, encrypted local fallback for offline work, and secret references to avoid duplication . | Quote-only (team-based) | **Free tier** available for small teams |
| **[HashiCorp Vault](https://www.hashicorp.com/)** | **The enterprise secret management standard.** Secure storage for arbitrary key/value pairs, **dynamic secrets** generated on-demand for AWS/SQL with automatic revocation, encryption-as-a-service, and detailed audit logs. Leasing and renewal for every secret . | Quote-only (enterprise contract); **HCP Vault** from ~$0.03/hour | **Vault Community Edition** free (self-hosted); trial via HCP |
| **[Infisical](https://infisical.com/)** | **Open-source platform for secrets, certificates, and privileged access management.** Centralized secret sync across environments, PKI/certificate management, and AI agent credential proxying . | Quote-only (cloud tiers) | **Free tier** available; **Infisical OSS** self-hosted free |
| **[AWS Systems Manager Parameter Store](https://aws.amazon.com/systems-manager/)** | Secure hierarchical storage for configuration data and secrets. **Advanced Parameters: $0.05/parameter/month**; standard parameters free. Integrates natively with EC2, Lambda, ECS, and CloudFormation. | Advanced: **$0.05/parameter/month**; Standard: **free** | **Free tier**: standard parameters, no additional charge |
| **[Pulumi ESC](https://www.pulumi.com/esc/)** | **Environments, Secrets, and Configuration** for Pulumi and external workflows. Injects env vars and files into GitHub Actions, supports OIDC short-lived tokens, and manages hierarchical environments with revision tags . | Quote-only (included with Pulumi Cloud plans) | **Free tier** available for small teams |
| **[Azure App Configuration](https://azure.microsoft.com/en-us/products/app-configuration/)** | Centralized configuration store with feature flags, key-value pairs, and label-based environments. Integrates with .NET, Java, Spring, and Kubernetes. | **$1.20/day** per Standard tier instance; Free tier available | **Free tier**: 10 MB storage, 1,000 requests/day |
| **[ConfigCat](https://configcat.com/)** | Feature flag service with **generous free tier for up to 1,000 users**. SDKs for all major languages and frameworks (Angular, React, .NET, Next.js, etc.) . | Free: **$0** (1,000 users); Pro: quote-only | **Free forever**: 1,000 users, unlimited flags, all SDKs |
| **[LaunchDarkly](https://launchdarkly.com/)** | **The enterprise feature management standard.** Flag targeting, percentage rollouts, A/B testing, and **MCP server for AI agents** to safely toggle flags and manage targeting rules . | Quote-only (enterprise contract) | **Free tier** available for developers (limited MAU) |

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
