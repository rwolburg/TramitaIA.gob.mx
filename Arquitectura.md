# Architecture Documentation

This folder contains architecture documentation for the `multicanal-ia` platform.

## Documents

| File | Description | Version |
|------|-------------|---------|
| `multicanal-ia-arquitectura-multitenant.docx` | Multi-tenant architecture proposal: SSO, per-tenant RAG, Secrets Vault, Admin Portal | 2.0 |

## Summary

The platform is evolving from a single-tenant PoC (Avatar Web + GPT-4o orchestrator) to a
full multi-tenant SaaS architecture supporting:

- **Authentication**: email/password, Google OAuth2, Microsoft Azure AD, SAML 2.0
- **RAG**: global shared index + private per-tenant index (Azure AI Search)
- **Secrets Vault**: AES-256 encrypted credentials per tenant (Azure Key Vault master key)
- **Admin Portal**: Super Admin (platform) + Tenant Admin (per-client self-service)
- **Channels**: Avatar Web, WhatsApp, Email — each configurable per tenant
- **Agents**: CFDI, Quotes, Calendar, CRM, RRHH — activated and configured per tenant

## Architecture Model

**Recommended: Model B (shared Azure tenant, logical isolation per client)**

One set of Azure resources (Speech, OpenAI, AI Search) with per-tenant data isolation.
Clients can optionally bring their own Azure keys (Model C hybrid) via the Secrets Vault.

See the `.docx` document for full diagrams, data model, and implementation phases.
