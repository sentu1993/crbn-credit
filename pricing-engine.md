# The CRBN Credit Pricing Engine

CRBN Credit employs a rigorous, multi-layered approach combining on-chain immutable records with traditional registry data to create a unified, institutional-grade view of the Voluntary Carbon Market.

## Layer 1: Data Aggregation (The Oracle Engine)

The Oracle Engine continuously polls three primary source categories:

**A) Traditional Registries**
- Verra (VCS), Gold Standard, ACR, CAR, Puro.earth.
- *Method*: Parsing PDF issuance documents, API endpoints, and public retirement logs.

**B) On-Chain Ledgers (ReFi)**
- Toucan Protocol (BCT, NCT)
- KlimaDAO retirement events
- *Method*: Real-time blockchain monitoring (Polygon, Celo).

**C) Market Venues (Price Feeds)**
- Xpansiv CBL (largest voluntary carbon exchange)
- CME Group (carbon futures contracts)
- Decentralized liquidity pools (Uniswap v3, SushiSwap)
- *Method*: Live feed aggregation and websocket streaming.

## Layer 2: Quality & Integrity Scoring

Raw data passes through a proprietary AI scoring model before price calculation:
1. **Additionality Check**: NLP analysis of project documentation to verify financial additionality claims.
2. **Permanence Risk Assessment**: Geospatial analysis mapping physical risks (fire, drought) against project boundaries.
3. **Vintage Decay Modeling**: Automated discounting of older vintages (>5 years old) based on current market preference curves.

## Layer 3: Fair Value Calculation

Because carbon credits are illiquid and volatile, Fair Value is calculated as a composite metric:

`Fair_Value = (VWAP_CEX × 0.4) + (VWAP_DEX × 0.4) + (OTC_Reported × 0.2)`

- **40% Weight**: Centralized Exchange (CEX) Volume-Weighted Average Price.
- **40% Weight**: Decentralized Exchange (DEX) Volume-Weighted Average Price.
- **20% Weight**: OTC Broker-Reported Prices.

This composite formula smooths out volatility from low-liquidity venues, providing a robust mark-to-market price for institutional portfolios.
