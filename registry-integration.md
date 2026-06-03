# Registry Integration and Data Normalization

The global carbon market is highly fragmented, with project data, issuance logs, and retirement records siloed across dozens of independent registries. CRBN Credit solves this through robust registry integration and data normalization.

## Layer 1: Data Aggregation Engine

Our Oracle Engine continuously polls and parses data from the world's leading carbon registries:
- **Verra (VCS)**: The largest issuer of VCM credits.
- **Gold Standard (GS)**: Premium credits with SDG co-benefits.
- **American Carbon Registry (ACR)** & **Climate Action Reserve (CAR)**.
- **Puro.earth**: Specialized in engineered removals (Biochar, DAC).

### Technical Ingestion
We utilize a combination of API webhooks and automated parsing of public ledger documents to ensure our terminal reflects near real-time state changes in global carbon supply.

## Normalizing the Data

Carbon registries use different taxonomies, methodologies, and metadata formats. CRBN Credit normalizes this data into a standardized institutional format.
- We map disparate methodology codes to our unified ontology (e.g., categorizing various forestry methodologies under a unified "Nature-Based Avoidance" or "Nature-Based Removal" tag).
- We standardize vintage years, geography codes, and SDG impact metrics.

## Integrated Registry Lookup

Through the CRBN Credit terminal, users can execute unified queries across all registries simultaneously. 
You can search by serial number, project ID, or developer name and instantly see the issuance, remaining supply, and retirement history without navigating multiple fragmented registry portals.
