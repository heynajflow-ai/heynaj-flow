# HeyNaj Flow

**AI website assistance that turns conversations into follow-up-ready inquiries.**

HeyNaj Flow is a free, self-service AI website assistant and business inquiry workspace for website owners, businesses, service providers, professionals, and agencies managing client websites.

**Website:** https://heynajflow.com  
**Get Started:** https://heynajflow.com/get-started/

## Watch HeyNaj Flow

[![Watch the HeyNaj Flow launch video](https://res.cloudinary.com/dt5j91krt/video/upload/so_2,w_1200,c_limit/v1791009669/HeyNaj_V3_720p_wqpiss.jpg)](https://player.cloudinary.com/embed/?cloud_name=dt5j91krt&public_id=HeyNaj_V3_720p_wqpiss)

▶ **[Watch the HeyNaj Flow launch video](https://player.cloudinary.com/embed/?cloud_name=dt5j91krt&public_id=HeyNaj_V3_720p_wqpiss)**

The video is hosted on Cloudinary so this repository stays lightweight while the same public asset can be reused across the HeyNaj Flow website and launch materials.

## Documentation

- **[Getting Started](docs/GETTING_STARTED.md)** — public-safe setup flow from workspace access to website installation and testing
- **[Product Overview](docs/PRODUCT_OVERVIEW.md)** — product workflow, capabilities, Knowledge, Inquiries, voice, notifications, and access model
- **[Architecture Overview](docs/ARCHITECTURE.md)** — high-level public architecture and customer-owned Cloudflare model
- **[Deployment Integrity](docs/DEPLOYMENT_INTEGRITY.md)** — public explanation of managed deployment-integrity checks

## What HeyNaj Flow does

A visitor arrives on your website and asks a question.

HeyNaj Flow can answer using approved business Knowledge, preserve the conversation as an Inquiry, optionally capture contact information, and give the business useful context for follow-up.

**Visitor asks → HeyNaj answers → conversation becomes an Inquiry → optional contact details are captured → the business reviews the context and follows up.**

## Core capabilities

- AI-powered website conversations grounded in approved business Knowledge
- Text Only, Standard Voice, and Premium Live Voice experiences
- Optional contact capture with Off, Soft Capture, and Required modes
- Saved Inquiries with conversation transcripts and Conversation recaps
- Source Page URL context
- Email and Web Push inquiry notifications
- Question Review for genuine missing business Knowledge
- Customizable website widget
- Customer-owned Cloudflare Worker and D1 workspace
- Responsive web dashboard and PWA experience

## Voice experiences

### Text Only
Visitors communicate through normal typed website conversations.

### Standard Voice
Uses supported browser/device speech recognition and speech synthesis.

### Premium Live Voice
Supports compatible realtime voice providers, including OpenAI Realtime and Google Gemini Live.

Voice availability and quality can depend on the browser, device, provider, account permissions, region, credits, and other provider requirements.

## Knowledge

New Business Documents currently support **TXT, MD, DOCX, and PDF**.

PDF files must contain selectable text to become searchable. Scanned or image-only PDFs are not currently readable through OCR.

## Inquiries

Visitor conversations can be preserved as Inquiries even when the visitor does not provide contact information.

When available, an Inquiry can include contact details, transcript, Conversation recap, Page URL, status, and private follow-up context for the business.

HeyNaj Flow helps preserve the conversation and its context. The business remains responsible for human follow-up.

## Contact capture

Businesses can choose:

- **Off** — visitors can chat without being asked for contact details
- **Soft Capture** — contact details may be requested without blocking the conversation
- **Required** — contact details are required before continuing into the configured chat flow

## Customer-owned Cloudflare workspace

Each customer connects a Cloudflare account during setup.

HeyNaj Flow uses a customer-owned Cloudflare Worker and D1 database for the customer runtime and workspace data.

Selected AI, speech, email, push, and other providers may still process information required to provide their respective functions.

## Free to use

HeyNaj Flow is free to use.

Optional community or coffee support does not unlock additional product features or create paid feature tiers.

Third-party services may have their own usage limits, quotas, eligibility requirements, or charges.

## Multilingual support

**Multilingual understanding, with English-first voice support.**

Typed multilingual questions can be understood depending on the configured AI provider. Same-language responses are not guaranteed on every turn, and voice interactions are currently optimized for English.

## Powered by HeyNaj

The HeyNaj Flow website widget retains **Powered by HeyNaj** branding.

## Deployment integrity protection

HeyNaj Flow uses deployment-integrity checks to help protect managed customer installations.

Customers retain ownership of and access to their Cloudflare workspace. If core HeyNaj Flow-managed resources or deployment state are manually changed, a future controlled update may be blocked until the installation is reconciled.

This protection does **not** lock your Cloudflare account or remove your access to Cloudflare.

See [Deployment Integrity](docs/DEPLOYMENT_INTEGRITY.md) for more information.

---

## Important product boundaries

HeyNaj Flow does not guarantee sales or conversions, uninterrupted availability, perfect AI answers, unlimited third-party usage, autonomous appointment completion, comprehensive CRM/analytics functionality, or OCR for scanned/image-only PDFs.

Businesses should review important conversations and information before acting on them.

## Get started

Start here:

https://heynajflow.com/get-started/

The public Get Started page provides the branded entry point to create or access your HeyNaj Flow workspace.

Learn more:

https://heynajflow.com/

## About this repository

This repository is the public home for HeyNaj Flow product information, documentation, issue reporting, feature suggestions, launch updates, and community feedback.

The HeyNaj Flow production platform source code is maintained separately.

No open-source software license is granted unless one is explicitly added in the future.

---

Built with ☕ by HeyNaj Flow.
