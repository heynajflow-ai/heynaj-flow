# Deployment Integrity Protection

HeyNaj Flow uses deployment-integrity checks to help protect managed customer installations.

Each customer runtime is deployed in a customer-owned Cloudflare workspace. Customers retain ownership of and access to their Cloudflare account and resources.

If core HeyNaj Flow-managed resources or deployment state are manually changed, a future controlled update may be blocked until the installation is reconciled.

## What this means

Deployment integrity protection:

- does **not** lock your Cloudflare account
- does **not** remove your access to Cloudflare
- helps prevent a controlled HeyNaj Flow update from being applied when the expected installation state cannot be verified

## Recommended practice

Use the supported HeyNaj Flow setup and update flows whenever possible.

If you intentionally make infrastructure-level changes to HeyNaj Flow-managed resources, be aware that the installation may need to be reconciled before a future controlled update can proceed.
