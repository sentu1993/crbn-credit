# Retirement Verification Process

Retiring a carbon credit is the ultimate proof of environmental impact. Ensuring this process is flawless, secure, and verifiable is paramount to preventing double counting.

## The CRBN Credit Verification Workflow

When an institutional client executes a retirement via our platform or API, the following strict workflow is triggered:

### Step 1: Pre-Execution Verification
Before any funds move or ledgers are updated, our system queries the source registry (e.g., Verra API).
- We verify the exact serial numbers.
- We confirm the credit is currently active and has not been retired or cancelled previously.
- We check for any holds or compliance flags on the issuing project.

### Step 2: Escrow and Execution
Funds are held in a secure smart contract or institutional escrow.
The retirement request is dispatched to the registry with the specific beneficiary details (e.g., "Retired on behalf of XYZ Corp for 2026 Scope 1 Emissions").

### Step 3: Ledger Synchronization
Once the registry confirms the retirement, the CRBN Credit Oracle Engine syncs the state.
- The credits are permanently removed from available marketplace inventory.

### Step 4: Cryptographic Proof Generation
To provide our clients with immutable, audit-ready evidence, we generate a cryptographic proof-of-offset.
- A public certificate is minted (optionally on-chain).
- The certificate contains a transaction hash, serial numbers, project metadata, and a timestamp.
- This proof can be directly exported to ESG auditors or appended to CSRD/SEC climate disclosures.
