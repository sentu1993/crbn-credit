# WebSocket Feeds

For high-frequency trading desks, hedge funds, and live portfolio dashboards, REST APIs are too slow. CRBN Credit offers low-latency WebSocket feeds for real-time market data.

## Connection

Connect to the WebSocket server using your API key:
`wss://stream.crbn.credit/v1/realtime?api_key=YOUR_API_KEY`

## Channels

Once connected, you can subscribe to specific channels by sending a JSON payload.

### 1. Ticker Channel
Streams every price update (trades and VWAP shifts) across CEX and DEX venues.

**Subscription Request:**
```json
{
  "action": "subscribe",
  "channel": "ticker",
  "assets": ["EUA", "NCT", "BCT", "TECH-REM"]
}
```

### 2. Retirement Event Channel
Streams global retirement events as they happen on-chain or are published by legacy registries. Useful for monitoring macro supply shocks.

**Subscription Request:**
```json
{
  "action": "subscribe",
  "channel": "retirements",
  "size_threshold": 1000  // Only stream retirements > 1000 tonnes
}
```

## Heartbeats
The server will send a `ping` frame every 30 seconds. Your client must respond with a `pong` frame within 10 seconds to keep the connection alive.
