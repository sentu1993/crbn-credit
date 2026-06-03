# Registry Sync Process

Ensuring our terminal reflects the true, real-time state of the global carbon market requires aggressive, highly redundant synchronization with underlying registries.

## Sync Architecture

The CRBN Credit sync architecture utilizes a multi-pronged approach:

### 1. Webhook APIs
Where modern registries support it, we maintain active webhook connections. State changes (new issuances, project status updates, retirements) are pushed to our servers instantly.

### 2. Polling Engines
For legacy registries that do not support webhooks, our distributed polling engine queries their public endpoints at high frequencies (up to every 60 seconds for high-liquidity assets).

### 3. PDF and Ledger Parsing
Some registries still rely on publishing static reports or PDFs for specific compliance data. We utilize NLP (Natural Language Processing) OCR models to extract tabular data from these documents the moment they are published.

### 4. On-Chain Listeners
For tokenized carbon (Polygon, Celo), we run dedicated RPC nodes. Our listeners subscribe to specific smart contract events (e.g., `Retire` events on Toucan or KlimaDAO contracts), updating our database within block-time limits (typically under 3 seconds).

## Resolving Sync Conflicts

If an on-chain ledger reports a retirement but the legacy registry API is delayed in reflecting it (a common occurrence due to manual registry processing), CRBN Credit applies a "Pending Sync" status. This prevents the credit from being double-sold while awaiting final confirmation from the slow registry.
