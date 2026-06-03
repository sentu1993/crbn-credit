# The Retirement Ledger

Retirement is the final, most critical lifecycle stage of a carbon credit. When a credit is "retired," it is permanently removed from circulation and claimed as an offset against emissions. It cannot be sold or transferred again.

## The Double Counting Problem

A major risk in carbon markets is double counting—where the same carbon credit is sold to or claimed by two different entities. 
Traditional registries mitigate this through serial numbers, but cross-registry and cross-border transactions can still obscure the chain of custody.

## CRBN Credit's Immutable Proof-of-Offset

To provide absolute certainty to our institutional clients, CRBN Credit utilizes a highly secure Retirement Ledger.

### How It Works
1. **Verification**: Before execution, our smart contract escrow queries the registry APIs to verify the credit's vintage, serial number, and active non-retired status.
2. **Execution**: The credit is retired on the native registry (or on-chain if tokenized).
3. **Cryptographic Proof**: We generate an immutable proof-of-offset record. This provides a publicly verifiable certificate containing:
   - The beneficiary name.
   - The exact serial numbers of the credits.
   - The project metadata and vintage.
   - The cryptographic transaction hash of the retirement event.

This ledger is critical for corporate sustainability audits and SEC/CSRD compliance reporting, ensuring that your Net Zero claims are backed by mathematically verifiable proof.
