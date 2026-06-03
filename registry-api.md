# Registry API

The Registry API normalizes data across Verra, Gold Standard, Puro.earth, and on-chain protocols into a single, unified taxonomy.

## Endpoints

### 1. Search Projects
`GET /v1/registry/projects`

Search for carbon projects across all global registries simultaneously.

**Query Parameters:**
- `registry` (optional): e.g., `verra`, `gold-standard`.
- `methodology`: e.g., `biochar`, `redd-plus`.
- `country`: ISO 3166-1 alpha-2 country code.

**Response Example:**
```json
{
  "results": [
    {
      "crbn_id": "PRJ-99382",
      "registry": "Puro.earth",
      "project_name": "Nordic Biochar Facility",
      "methodology": "Biochar",
      "composite_rating": "AAA",
      "available_supply": 4500
    }
  ]
}
```

### 2. Get Issuance & Retirement Ledger
`GET /v1/registry/projects/{crbn_id}/ledger`

Returns the complete chronological history of issuances and retirements for a specific project. This endpoint merges off-chain registry PDFs with on-chain polygon/celo retirement events to provide a complete view of the asset's lifecycle.
