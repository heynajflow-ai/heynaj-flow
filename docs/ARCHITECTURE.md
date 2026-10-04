# HeyNaj Flow Architecture Overview

This document describes the **public, product-level architecture** of HeyNaj Flow.

It is intentionally high level. It is **not** a deployment recipe, source-code guide, or reproduction blueprint. Internal implementation details, private endpoints, security controls, schemas, provisioning logic, and deployment mechanics are deliberately omitted.

## High-level model

HeyNaj Flow separates the public website experience, the customer-owned runtime, the business workspace, and connected third-party providers.

```text
Website visitor
      |
      v
HeyNaj Flow website widget
      |
      v
Customer-owned Cloudflare runtime
      |
      +---- Customer-owned D1 data
      |
      +---- Approved business Knowledge
      |
      +---- Connected AI / voice providers
      |
      +---- Connected email / push services

Business owner
      |
      v
HeyNaj Flow workspace
      |
      v
Supported configuration, review, and deployment management
```

The exact internal routing, service boundaries, bindings, authentication flows, and deployment controls are not documented publicly.

## Website widget

The HeyNaj Flow widget is added to a website through a lightweight embed.

It provides the visitor-facing experience for supported text and voice interactions, optional contact capture, and inquiry creation.

The widget retains **Powered by HeyNaj** branding.

The public widget is only one part of the system. Business logic and customer-specific runtime operations are handled through the customer deployment and supported provider connections.

## Customer-owned Cloudflare runtime

Each customer connects a Cloudflare account during setup.

HeyNaj Flow uses customer-owned Cloudflare resources for the customer runtime, including:

- a Cloudflare Worker
- a D1 database

This keeps the customer runtime logically separated from other customer deployments while allowing the customer to retain ownership of and access to their Cloudflare account and resources.

Customer-owned infrastructure does **not** mean every piece of information remains only inside Cloudflare. Selected third-party services may process information required to provide AI, voice, email, push, or related functionality.

## Business Knowledge and RAG

HeyNaj Flow can answer visitor questions using approved business Knowledge.

Supported Knowledge can be used to ground AI responses so the assistant can answer from information the business has provided rather than relying only on general model knowledge.

Current Business Documents support TXT, MD, DOCX, and PDF with selectable text. Scanned or image-only PDFs are not currently searchable through OCR.

The exact retrieval pipeline, indexing implementation, ranking logic, prompts, and internal data structures are not published.

## Inquiry flow

At a product level, a normal interaction follows this pattern:

1. A visitor asks a question through the website widget.
2. The customer runtime processes the request.
3. Approved business Knowledge may be used when relevant.
4. A configured AI or voice provider may process the interaction.
5. The response is returned to the visitor.
6. The conversation can be preserved as an Inquiry.
7. Contact details may be captured depending on the configured contact-capture mode.
8. Eligible email or Web Push notifications may be sent.
9. The business reviews the Inquiry and follows up.

The business remains responsible for final human follow-up and important decisions.

## HeyNaj Flow workspace

The HeyNaj Flow workspace gives the business a web-based interface for supported product configuration and review.

Depending on the configured workspace, this can include:

- Inquiries and conversation context
- business Knowledge
- Question Review
- AI and voice settings
- contact-capture behavior
- notification settings
- widget customization
- installation and deployment status

The workspace is a management layer for the product. This public repository does not expose the private production application source code or internal deployment implementation.

## Connected providers

HeyNaj Flow can connect to supported third-party services for capabilities such as:

- AI processing
- realtime voice
- email delivery
- Web Push
- authentication and related platform functions

Examples of supported AI and realtime voice providers include OpenAI and Google Gemini, depending on the selected feature and account availability.

Third-party providers have their own terms, eligibility requirements, quotas, regional availability, and charges.

## Deployment integrity

Customer deployments are managed through supported HeyNaj Flow setup and update flows.

HeyNaj Flow uses deployment-integrity checks to help prevent a controlled update from being applied when the expected managed installation state cannot be verified.

Customers retain ownership of and access to their Cloudflare account. HeyNaj Flow does not lock the customer's Cloudflare account.

See [Deployment Integrity](DEPLOYMENT_INTEGRITY.md) for the public explanation.

## Data and ownership boundaries

At a high level:

- the customer owns the connected Cloudflare account and customer deployment resources
- customer runtime and workspace data use the customer deployment, including D1
- selected third-party providers may process the data required for their functions
- the public website widget does not represent the entire backend architecture
- the HeyNaj Flow production platform source code is maintained separately from this public repository

## What this document intentionally does not disclose

To keep the public documentation useful without exposing implementation details that could weaken the platform or provide a reproduction blueprint, this document does not publish:

- private source code
- internal service or endpoint maps
- authentication internals
- security-control implementation details
- credential-handling internals
- Worker binding names
- D1 schemas or migration logic
- provisioning or upgrade internals
- deployment verification mechanics
- internal package or release processes
- private prompts, retrieval logic, or ranking implementation
- internal monitoring, validation, or recovery procedures

Those details are not required to understand how HeyNaj Flow works as a product.

## Summary

The public architecture can be understood simply as:

**Website visitor → HeyNaj Flow widget → customer-owned Cloudflare runtime → approved Knowledge and connected providers → Inquiry → business workspace**

This model gives each customer a dedicated runtime inside their own Cloudflare account while keeping the customer-facing experience simple and centrally manageable through HeyNaj Flow.
