# Data Normalization

The Voluntary Carbon Market is notoriously decentralized. With dozens of registries operating independently using different taxonomies, data normalization is required to build a functioning global terminal.

## The Taxonomy Challenge

Consider a simple forestry project. 
- Registry A might classify it as "Afforestation / Reforestation (ARR)".
- Registry B might classify it as "Land Use and Forestry (LULUCF)".
- Registry C might classify it as "Nature-Based Carbon Removal".

Without normalization, searching for "Forestry Removals" across all registries is impossible.

## Our Normalization Pipeline

CRBN Credit applies an advanced ETL (Extract, Transform, Load) pipeline to all incoming registry data.

1. **Methodology Mapping**: We map over 300 unique registry methodologies into a unified, institutional taxonomy. We classify all projects fundamentally into:
   - *Nature-Based Avoidance*
   - *Nature-Based Removal*
   - *Tech-Based Avoidance*
   - *Tech-Based Removal*
2. **Geospatial Standardization**: Normalizing country, state, and region codes using ISO 3166 standards.
3. **Vintage Standardization**: Ensuring issuance years, verification periods, and credit vintages are perfectly aligned for time-series analysis.
4. **Metric Conversion**: Standardizing all volume metrics to metric tonnes of CO2 equivalent (tCO2e).

This normalization allows our users to execute complex queries across the entire global carbon market simultaneously via our API or visual terminal.
