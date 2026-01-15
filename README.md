# Paces Portfolio

Hi! I'm Charlie, a Permitting and Policy Research Intern with the Data Ops team at Paces. This portfolio showcases projects involving QGIS, Python, and SQL, demonstrating how zoning, permitting, and land-use regulations can be translated into structured, scalable data to support early-stage renewable energy project diligence.

## Projects

### Zoning Code Parser for Renewable Energy Permitting
A Python-based workflow that converts unstructured municipal zoning text into structured data to support early-stage renewable energy site diligence.

**Tools:** Python, Pandas  
**Focus:** Zoning, permitting, policy-to-data automation  

**[View Project](https://github.com/) | [Local Folder](zoning-code-parser/)**
  
## Data Challenges & Debugging

### Zoning Map Georeferencing — Paces Portfolio Project

#### Overview
Georeferenced a scanned municipal zoning map to support spatial zoning interpretation and early-stage renewable energy site diligence. The goal was to align unstructured zoning graphics with authoritative vector reference layers for permitting and land-use analysis.

#### Data Sources
- Scanned municipal zoning map (PDF-derived raster)  
- Reference parcel and street centerline layers

#### Methodology
- Verified coordinate reference systems (CRS) across all layers  
- Selected well-distributed Ground Control Points (GCPs) using road intersections and parcel corners  
- Evaluated transformation types to balance stability and spatial accuracy  

#### Georeferencing Challenge
During georeferencing, QGIS returned the error:

> *"Failed to compute GCP transform: Transform is not solvable"*

This occurred despite using a Polynomial 1 transformation with sufficient GCPs and a reported mean error (~37), suggesting the transformation was mathematically solvable.

#### Root Cause
The failure stemmed from invalid GCP inputs rather than insufficient points. Although QGIS computed transformation coefficients, the raster transformation failed due to:  
- Corrupted or duplicated GCPs  
- Invalid map X/Y values  
- CRS inconsistencies between the raster and reference layers  

This is a common geospatial data integrity issue where a transform appears solvable but cannot be applied.

#### Solution
Applied a systematic debugging workflow:  
1. Reset the Georeferencer session and removed all existing GCPs  
2. Explicitly defined the target CRS to match the reference vector data  
3. Carefully re-selected GCPs, ensuring valid coordinates and even spatial distribution  
4. Re-ran the transformation and verified alignment with reference layers  

This approach ensured a successful georeferencing, enabling accurate spatial analysis for permitting diligence.



