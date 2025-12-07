# Biodiversity Intactness Index Change in Phoenix, Arizona (2017-2020)

**Author**: Lucian Scher  
**Repository**: https://github.com/lucianbluescher/Phoenix_BII_Change  
**Date**: December 2025

## About

This project quantifies the loss of high-quality habitat in the Phoenix, Arizona subdivision by analyzing temporal changes in the Biodiversity Intactness Index (BII) between 2017 and 2020. The Biodiversity Intactness Index, developed by Impact Observatory, provides a measure of how intact natural ecosystems are compared to an untouched state, with values ranging from 0 (completely degraded) to 1 (pristine).

*Highlights*
- Approximately 26.28 km² of land with high biodiversity intactness (BII ≥ 75%) was lost in the Phoenix subdivision between 2017 and 2020
- The analysis combines cloud-based Earth observation data with U.S. Census geographic boundaries
- Results are visualized through static maps and temporal GIFs to communicate biodiversity change patterns

This work demonstrates modern geospatial data science workflows by accessing large-scale environmental datasets directly from cloud storage and performing reproducible spatial analysis.

![Phoenix BII Analysis](https://github.com/user-attachments/assets/6bd897e8-4260-4beb-8f1a-1d300aacf5af)

## Repository Structure

```
Phoenix_BII_Change/
│
├── phoenix_BII.ipynb # Jupyter notebook
├── data/
│ └── tl_2025_04_cousub/ # Geographic data (Census shapefile)
│
└── README.md
```

## Data

This analysis uses two primary datasets:

### 1. Biodiversity Intactness Index (BII) Time Series

The Biodiversity Intactness Index data is sourced from Microsoft Planetary Computer and accessed directly from Azure Blob Storage via the STAC API, eliminating the need for local downloads. The dataset provides global coverage at approximately 30-meter resolution, stored as Cloud Optimized GeoTIFFs (COG). For this analysis, annual BII data from 2017-2020 was extracted for the Phoenix metropolitan area.

The BII data is accessed programmatically using the `pystac-client` library. The notebook demonstrates how to query the Planetary Computer STAC API and load data directly from cloud storage.

### 2. Phoenix Subdivision Boundary

The Phoenix subdivision boundary data is sourced from the U.S. Census Bureau's 2025 TIGER/Line Shapefiles for Arizona county subdivisions. The shapefile is stored locally in the `data/tl_2025_04_cousub/` directory and can be downloaded from the [U.S. Census Bureau TIGER/Line portal](https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2025&layergroup=County+Subdivisions) by selecting year 2025, layer type "County Subdivisions," and state "Arizona."

## References

**Datasets:**

Impact Observatory & Vizzuality. (2023). *Biodiversity Intactness Index* [Dataset]. Microsoft Planetary Computer. https://planetarycomputer.microsoft.com/dataset/io-biodiversity

U.S. Census Bureau. (2025). *TIGER/Line Shapefiles: County Subdivisions* [Dataset]. https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2025&layergroup=County+Subdivisions

**Background**

Z. Levitt and J. Eng, “Where America’s developed areas are growing: ‘Way off into the horizon’,” The Washington Post, Aug. 2021, Available: https://www.washingtonpost.com/nation/interactive/2021/land-development-urban-growth-maps/. [Accessed: Nov. 22, 2024]

F. Gassert, J. Mazzarello, and S. Hyde, “Global 100m Projections of Biodiversity Intactness for the years 2017-2020 [Technical Whitepaper].” Aug. 2022. Available: https://ai4edatasetspublicassets.blob.core.windows.net/assets/pdfs/io-biodiversity/Biodiversity_Intactness_whitepaper.pdf

**Code Resources:**

Microsoft Planetary Computer. (2025). Biodiversity Intactness Index example notebook. https://planetarycomputer.microsoft.com/dataset/io-biodiversity#Example-Notebook

**Course:**

Masters of Environmental Data Science (MEDS), Bren School of Environmental Science & Management, University of California, Santa Barbara. EDS 220: Working with Environmental Datasets.

---
