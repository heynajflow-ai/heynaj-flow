# Deployment Integrity Protection

HeyNaj Flow customers use a customer-owned Cloudflare workspace for their customer runtime.

Ownership of the Cloudflare workspace does not mean that every infrastructure-level change is safe for the managed HeyNaj Flow installation.

## What HeyNaj Flow protects

Controlled upgrades verify the expected:

- installation
- owner
- customer runtime
- package/build
- schema
- authorization
- deployment state

If the required deployment state has changed, expired, or cannot be verified, the controlled upgrade is blocked instead of being forced through.

## What this does not mean

This protection does **not** lock the customer's Cloudflare account.

It does not remove the customer's ownership or access to Cloudflare.

It is an upgrade-safety mechanism designed to avoid applying a HeyNaj Flow update to an installation that no longer matches the state the platform expects.

## Recommended practice

Avoid manually changing the HeyNaj Flow-managed:

- Worker code
- Worker bindings
- D1 schema
- deployment configuration
- installation pairing/configuration

unless you understand the consequences.

Use the supported HeyNaj Flow setup and controlled-upgrade flow whenever possible.

If you intentionally make infrastructure-level changes, HeyNaj Flow may require the deployment state to be reconciled before a future controlled upgrade can proceed.
