# Getting Started with HeyNaj Flow

This guide provides a **public, product-level setup overview** for HeyNaj Flow.

It is intentionally high level. It does not document private infrastructure details, internal endpoints, deployment commands, database schemas, credential internals, provisioning logic, or security-control implementation.

## 1. Open HeyNaj Flow

Start from the public Get Started page:

https://heynajflow.com/get-started/

From there, open the HeyNaj Flow workspace and follow the supported sign-in and onboarding flow.

## 2. Connect your Cloudflare account

HeyNaj Flow uses a customer-owned Cloudflare workspace for the customer runtime.

During supported setup, you connect the Cloudflare account that will own the HeyNaj Flow customer deployment.

At a product level, this deployment includes a customer-owned Cloudflare Worker and D1 database.

Customers retain ownership of and access to their Cloudflare account and resources.

Do not publish Cloudflare credentials, API tokens, account secrets, or private deployment information.

## 3. Configure your assistant

Use the HeyNaj Flow workspace to configure the visitor experience.

Depending on the available settings, this can include:

- assistant tone and behavior
- Text Only, Standard Voice, or Premium Live Voice
- supported AI or realtime voice provider
- notification preferences
- contact-capture behavior
- website widget appearance and attention settings

Premium Live Voice can use compatible realtime providers such as OpenAI Realtime or Google Gemini Live, subject to provider availability, account requirements, credits, limits, and terms.

## 4. Add business Knowledge

Add the information HeyNaj Flow should use when answering visitor questions.

New Business Documents currently support:

- TXT
- MD
- DOCX
- PDF with selectable text

Scanned or image-only PDFs are not currently searchable through OCR.

Business Knowledge can be edited, replaced, or expanded over time. Question Review can help surface genuine information gaps that may need to be added to Knowledge.

## 5. Choose contact capture behavior

HeyNaj Flow supports three contact-capture modes:

- **Off** — visitors can chat without being asked for contact details
- **Soft Capture** — contact details may be requested without blocking the conversation
- **Required** — contact details are required before continuing into the configured chat flow

Conversations may still be preserved as Inquiries even when contact information is not provided, depending on the configured flow.

## 6. Connect supported providers

Some HeyNaj Flow capabilities rely on connected third-party providers.

Depending on the features you enable, these may include providers for:

- AI processing
- realtime voice
- email delivery
- Web Push
- authentication or related platform functions

Third-party services have their own eligibility requirements, usage limits, quotas, regional availability, and possible charges.

Do not put provider credentials into public website code, GitHub Issues, screenshots, or public documentation.

## 7. Review the widget

Configure the website widget for your site.

Depending on the available settings, you can adjust parts of the visitor experience such as:

- branding and appearance
- contact capture
- attention modes
- callouts or promotions
- supported voice experience

The public widget retains **Powered by HeyNaj** branding.

## 8. Complete the supported installation flow

Use the HeyNaj Flow Installation area to complete the supported customer deployment and verify its status.

The exact provisioning sequence, bindings, internal resource names, authentication exchange, and deployment implementation are intentionally not documented publicly.

For the public architecture model, see [Architecture Overview](ARCHITECTURE.md).

For the public explanation of managed deployment checks, see [Deployment Integrity](DEPLOYMENT_INTEGRITY.md).

## 9. Add the website embed

After setup is ready, HeyNaj Flow provides the website integration needed for the configured customer deployment.

Add the provided embed to the website using the supported installation instructions shown in the workspace.

The exact embed value is deployment-specific. Use the value generated for your workspace rather than copying an example from another installation.

You do not need to rebuild the entire website around HeyNaj Flow.

## 10. Test before relying on it

Before using the assistant with real visitors, test the configured experience.

Check that:

- the widget appears correctly on desktop and mobile
- business Knowledge answers are appropriate
- contact capture behaves as expected
- text and enabled voice modes work on supported browsers/devices
- Inquiries are preserved correctly
- enabled notifications reach the intended destination
- important website links and business information are accurate

Businesses should review important conversations and information before acting on them.

## 11. Go live and keep Knowledge current

Once the setup behaves as expected, use the widget on the intended website.

Keep business Knowledge, contact details, FAQs, pricing information, availability, promotions, and other time-sensitive information current.

If a visitor asks something the assistant genuinely cannot answer from available Knowledge, Question Review can help identify information that may need to be added.

## Public setup flow

At a high level:

**Get Started → sign in → connect Cloudflare → configure assistant → add Knowledge → choose contact capture and providers → configure widget → complete installation → add embed → test → go live**

This is the intended public understanding of the setup process. Private deployment implementation remains part of the HeyNaj Flow production platform and is not published in this repository.

## Need help?

For public product feedback, documentation issues, bug reports, or feature suggestions, use GitHub Issues.

Do not post credentials, customer data, API keys, account secrets, or security-sensitive details publicly.

For security-related reports, see [Security Policy](../SECURITY.md).
