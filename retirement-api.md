# Retirement API

The Retirement API allows institutional clients to programmatically retire carbon credits. This is essential for platforms building embedded sustainability features (e.g., a travel booking app offsetting flights in real-time).

> [!CAUTION]
> Retirement actions are irreversible. Once a carbon credit is retired via this API, it is permanently consumed and the transaction cannot be undone.

## Endpoints

### 1. Execute Retirement
`POST /v1/retirements/execute`

Executes a retirement on the native registry or on-chain protocol.

**Request Body:**
```json
{
  "crbn_id": "PRJ-99382",
  "vintage_year": 2025,
  "quantity": 150.5,
  "beneficiary_name": "Acme Corp",
  "retirement_reason": "2026 Scope 1 Emissions Offset"
}
```

### 2. Retrieve Proof of Offset
`GET /v1/retirements/{transaction_id}/proof`

Retrieves the immutable cryptographic proof of the retirement event, suitable for ESG auditing.

**Response Example:**
```json
{
  "transaction_id": "ret_8849302A",
  "status": "confirmed",
  "registry_tx_hash": "0x4a9b...7f1c",
  "certificate_url": "https://crbn.credit/cert/ret_8849302A.pdf",
  "timestamp": "2026-06-03T14:30:00Z"
}
```

## Escrow Requirements
To execute a retirement, your institutional account must have sufficient fiat or stablecoin balance in escrow, or you must be approved for net-30 invoicing.
