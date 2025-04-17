# Amazon’s New Oil Frontier: A Biodiversity Bomb in the Making? 

This repository supports the spatial analysis behind the article:

> **Amazon’s New Oil Frontier: A Biodiversity Bomb in the Making?**  
> _Submitted as a Nature Comment_

The article explores the ecological risks associated with offshore oil and gas development along Brazil’s Foz do Amazonas, highlighting how such infrastructure overlaps or lies dangerously close to biodiversity priority areas. This repository contains the code, data structure, diagnostics used to quantify these spatial relationships and final results.




## 🌍 Project Overview

The main goal is to evaluate the spatial relationship between infrastructure and conservation-relevant areas using geospatial analysis. This includes:

- Identifying whether a block or infrastructure intersects biodiversity priority areas.
- Calculating the percentage of overlap with priority zones.
- Measuring the minimum distance to the nearest priority area.
- Exporting all results to Excel for integration into scientific figures and decision-making.
- Generating interactive maps to visually validate the calculations (robustness check).


---


### 🗂️ Shapefiles Access

All spatial datasets used in the analysis — including sedimentary basins, priority areas (Amazon, Cerrado, Caatinga, ZCM, Hybrid zones), exploration blocks, offered blocks, ports, and airports — are available via Google Drive:

📁 [Access the full set of shapefiles here](https://drive.google.com/drive/folders/1BXIuKeB45blt6lMmfuZfsxzy9cKO6E80?usp=sharing)

Each subfolder corresponds to a thematic layer used in the geoprocessing workflow. These files are not version-controlled in the repository due to their size and format but are publicly accessible for transparency and reproducibility.

---

## 🧰 Technologies Used

- Python 3.11+
- GeoPandas
- Pandas
- Folium
- Shapely
- Jupyter / Google Colab

---

## 🧪 Spatial Analysis Workflow

Each spatial unit (block, port, airport) is analyzed using the following steps:

1. **Reproject** features and priority areas to EPSG:3857 for accurate metric calculations.
2. **Check for intersection** with biodiversity priority polygons.
3. **Calculate percentage** of spatial overlap for intersecting cases.
4. **Compute minimum distance** to the nearest priority area if not overlapping.
5. **Store results** in the original GeoDataFrames.
6. **Export to Excel** with fields relevant to environmental risk assessments.

---

## 📈 Output Fields

Each output `.xlsx` file includes the following columns:

| Column                       | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| `priority_class`            | Biodiversity importance level of intersecting area, or "No Priority Area"  |
| `overlap_pct_priority_area` | Percent of the feature's area overlapping with a priority area             |
| `priority_dist` (km)        | Minimum distance (in kilometers) to the nearest priority area if not intersecting |

---

## 🗺️ Map Visualization

An interactive **Folium map** is generated with:

- All spatial features (blocks, ports, airports)
- Biodiversity priority areas
- **Green buffers** from each feature to its nearest priority area (based on `priority_dist`)

This serves as a **robustness check** to visually confirm if the calculations are spatially consistent.

---

## 📌 Notes

- All spatial calculations are performed in **EPSG:3857 (meters)**.
- Results are exported in **EPSG:4326 (WGS84)** for compatibility with GIS/web tools.
- All distances in the diagnostics are reported in **kilometers (km)**.
- All data processing is done **feature-by-feature** with console feedback for traceability.

---


# 📊 Spatial Diagnostics — Foz do Amazonas


## 📊 Offered Blocks — Foz do Amazonas
- **Total**: 47
- **With intersection**: 27
- **% Intersecting**: 57.45%

🔹 **Detailed List of Offered Blocks**:
- ✅ **FZA-M-545** — intersects (Extremely High)
- ✅ **FZA-M-617** — intersects (Extremely High)
- ✅ **FZA-M-407** — intersects (Extremely High)
- ✅ **FZA-M-475** — intersects (Extremely High)
- ✅ **FZA-M-547** — intersects (Extremely High)
- ❌ **FZA-M-619** — no intersection, dist = 8.39 km
- ❌ **FZA-M-690** — no intersection, dist = 9.45 km
- ✅ **FZA-M-409** — intersects (Extremely High)
- ✅ **FZA-M-477** — intersects (Extremely High)
- ✅ **FZA-M-1102** — intersects (Extremely High)
- ✅ **FZA-M-184** — intersects (Extremely High)
- ❌ **FZA-M-255** — no intersection, dist = 3.19 km
- ❌ **FZA-M-261** — no intersection, dist = 23.39 km
- ❌ **FZA-M-328** — no intersection, dist = 0.30 km
- ❌ **FZA-M-263** — no intersection, dist = 18.98 km
- ✅ **FZA-M-330** — intersects (Extremely High)
- ❌ **FZA-M-265** — no intersection, dist = 18.43 km
- ✅ **FZA-M-332** — intersects (Extremely High)
- ❌ **FZA-M-267** — no intersection, dist = 20.04 km
- ✅ **FZA-M-334** — intersects (Extremely High)
- ✅ **FZA-M-399** — intersects (Extremely High)
- ✅ **FZA-M-401** — intersects (Extremely High)
- ✅ **FZA-M-403** — intersects (Extremely High)
- ✅ **FZA-M-1410** — intersects (Extremely High)
- ✅ **FZA-M-541** — intersects (Extremely High)
- ✅ **FZA-M-759** — intersects (Extremely High)
- ✅ **FZA-M-549** — intersects (Extremely High)
- ❌ **FZA-M-621** — no intersection, dist = 9.05 km
- ❌ **FZA-M-692** — no intersection, dist = 23.38 km
- ❌ **FZA-M-761** — no intersection, dist = 7.82 km
- ✅ **FZA-M-338** — intersects (Extremely High)
- ✅ **FZA-M-543** — intersects (Extremely High)
- ❌ **FZA-M-188** — no intersection, dist = 36.71 km
- ❌ **FZA-M-190** — no intersection, dist = 42.68 km
- ❌ **FZA-M-192** — no intersection, dist = 48.94 km
- ❌ **FZA-M-194** — no intersection, dist = 46.89 km
- ❌ **FZA-M-196** — no intersection, dist = 46.35 km
- ✅ **FZA-M-336** — intersects (Extremely High)
- ✅ **FZA-M-469** — intersects (Extremely High)
- ✅ **FZA-M-471** — intersects (Extremely High)
- ✅ **FZA-M-405** — intersects (Extremely High)
- ✅ **FZA-M-473** — intersects (Extremely High)
- ❌ **FZA-M-1040** — no intersection, dist = 14.18 km
- ❌ **FZA-M-1042** — no intersection, dist = 32.07 km
- ✅ **FZA-M-326** — intersects (Extremely High)
- ❌ **FZA-M-257** — no intersection, dist = 10.73 km
- ❌ **FZA-M-259** — no intersection, dist = 18.04 km

## 📊 Exploration Blocks — Foz do Amazonas
- **Total**: 9
- **With intersection**: 3
- **% Intersecting**: 33.33%

🔹 **Detailed List of Exploration Blocks**:
- ❌ **FZA-M-57** — no intersection, dist = 17.88 km
- ❌ **FZA-M-88** — no intersection, dist = 20.09 km
- ✅ **FZA-M-539** — intersects (Extremely High)
- ❌ **FZA-M-90** — no intersection, dist = 33.96 km
- ❌ **FZA-M-254** — no intersection, dist = 0.69 km
- ❌ **FZA-M-127** — no intersection, dist = 15.06 km
- ✅ **FZA-M-125** — intersects (Extremely High)
- ✅ **FZA-M-86** — intersects (Extremely High)
- ❌ **FZA-M-59** — no intersection, dist = 37.40 km

