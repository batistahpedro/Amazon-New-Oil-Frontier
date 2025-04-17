# Amazon-New-Oil-Frontier

This repository supports the spatial analysis behind the article:

> **Amazon’s New Oil Frontier: A Biodiversity Bomb in the Making?**  
> _Submitted as a Nature Comment_

The article explores the ecological risks associated with offshore oil and gas development along Brazil’s Equatorial Margin, highlighting how such infrastructure overlaps or lies dangerously close to biodiversity priority areas. This repository contains the code, data structure, and diagnostics used to quantify these spatial relationships.

---

## 🌍 Project Overview

The main goal is to evaluate the spatial relationship between infrastructure and conservation-relevant areas using geospatial analysis. This includes:

- Identifying whether a block or infrastructure intersects biodiversity priority areas.
- Calculating the percentage of overlap with priority zones.
- Measuring the minimum distance to the nearest priority area.
- Exporting all results to Excel for integration into scientific figures and decision-making.
- Generating interactive maps to visually validate the calculations (robustness check).


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

## 📂 Folder Structure

```none
Amazon-New-Oil-Frontier/
── Results/                      # Output Excel files (diagnostics)
── shapefiles/                   # Shapefiles (https://drive.google.com/drive/folders/1BXIuKeB45blt6lMmfuZfsxzy9cKO6E80?usp=sharing)
── analysis/                     # Python scripts
── README.md                     # Project documentation (this file)



