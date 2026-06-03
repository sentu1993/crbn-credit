# Getting Started with the CRBN Credit API

The CRBN Credit API provides institutional-grade access to global carbon market data, real-time pricing feeds, and programmatic retirement execution. This guide will walk you through authenticating your first request.

## Base URL
All API requests should be made to the `v1` endpoint:
`https://api.crbn.credit/v1`

## API Capabilities
- **Market Data**: Live and historical carbon price feeds across registries and on-chain protocols.
- **Projects**: Carbon project metadata, quality scores, and vintage availability.
- **Retirements**: Execute carbon credit retirements and generate immutable proof-of-offset certificates.

## Access Tiers

CRBN Credit provides different tiers of access:
1. **Developer (Free)**: Rate limited to 60 requests per minute. End-of-day pricing only.
2. **Institutional**: Real-time websocket data, 1,000 requests per minute.
3. **Enterprise**: Dedicated infrastructure, unrestricted rate limits, and data redistribution rights.

*Note: Raw data feeds cannot be resold or sub-licensed without an Enterprise License.*

## Making Your First Request

To test your API key, make a simple GET request to the `/ping` endpoint:

```bash
curl -X GET "https://api.crbn.credit/v1/ping" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

If successful, you will receive a `200 OK` status.
