# Market Data API

The Market Data API is the core of the CRBN Credit intelligence terminal. It provides normalized, aggregated pricing and volume data across CEXs, DEXs, and OTC markets.

## Endpoints

### 1. Get Live Fair Value Prices
`GET /v1/market/fair-value`

Retrieves the current composite Fair Value price for standardized carbon assets.

**Query Parameters:**
- `type` (optional): Filter by asset type (e.g., `tech-removal`, `nature-based`, `eu-ets`).

**Response Example:**
```json
{
  "timestamp": "2026-06-03T10:00:00Z",
  "data": [
    {
      "asset_class": "Tech-Based Removal",
      "fair_value_usd": 285.50,
      "24h_change_pct": 1.2,
      "confidence_score": 0.95
    }
  ]
}
```

### 2. Get Historical VWAP
`GET /v1/market/historical`

Retrieves historical Volume-Weighted Average Prices for charting and backtesting.

**Query Parameters:**
- `project_id`: The unified CRBN project ID.
- `start_date`: ISO 8601 format.
- `end_date`: ISO 8601 format.
- `interval`: Data resolution (e.g., `1d`, `1h`).

## Usage Notes
- Historical data is heavily cached; for real-time order book data, please use our **Websocket Feeds**.
