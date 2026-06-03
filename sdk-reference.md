# SDK Reference

To accelerate integration with the CRBN Credit platform, we maintain official open-source SDKs for popular programming languages.

## 1. Python SDK

Ideal for data scientists, quantitative analysts, and backend systems.

**Installation:**
```bash
pip install crbn-credit-sdk
```

**Usage Example:**
```python
from crbn import CRBNClient

client = CRBNClient(api_key="sk_live_...")

# Fetch fair value for Tech-Based Removals
price = client.market.get_fair_value(asset_type="tech-removal")
print(f"Current price: ${price['fair_value_usd']}")
```

## 2. Node.js (TypeScript) SDK

Ideal for embedding carbon offsetting into web applications and e-commerce checkouts.

**Installation:**
```bash
npm install @crbn/sdk
```

**Usage Example:**
```typescript
import { CRBN } from '@crbn/sdk';

const crbn = new CRBN('sk_live_...');

async function executeOffset() {
  const receipt = await crbn.retirements.execute({
    crbn_id: "PRJ-99382",
    quantity: 5,
    beneficiary_name: "John Doe"
  });
  console.log(receipt.certificate_url);
}
```

## 3. Go SDK
Designed for high-performance financial infrastructure and microservices. Visit our GitHub repository for full Go documentation and examples.
