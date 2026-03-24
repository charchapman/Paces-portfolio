# Paces Portfolio

Hi! I'm **Charlie**, a Permitting and Policy Researcher with the Data Operations team at [Paces](https://www.paces.com/). 

This portfolio demonstrates how I'm translating zoning regulations, permitting requirements, and land-use data into **structured, scalable datasets** that support early-stage renewable energy project diligence—work that directly contributes to faster, more efficient site screening.

---

## 🎯 What I Do at Paces

I work at the intersection of **policy research and data operations**, helping convert messy municipal data into clean, usable infrastructure:

- **Digitize zoning maps** in QGIS to enable spatial analysis for site diligence
- **Research and document** permitting requirements across jurisdictions
- **Build workflows** to extract and convert data from ArcGIS REST services
- **Debug spatial data issues** and document solutions for team knowledge sharing
- **Explore automation** to make repetitive data tasks more efficient

**The bigger picture:** Clean, well-structured permitting data is what allows renewable energy developers to move from site identification to shovel-ready faster. Every workflow I improve contributes to that mission.

---

## 📂 Portfolio Projects

### 🐍 Zoning Code Parser for Renewable Energy Permitting

A Python-based workflow that extracts structured data from unstructured municipal zoning documents to support early-stage site diligence.

**The Problem:** Municipal zoning codes are published as PDFs or web pages with inconsistent formatting. Extracting key parameters (setbacks, height limits, use permissions) manually is time-intensive and error-prone.

**My Solution:** Built a Python script that:
- Parses zoning text documents
- Extracts critical permitting parameters
- Outputs structured data (CSV format) for downstream analysis

**Tools:** Python, Pandas, Regular Expressions  
**Impact:** Faster extraction of zoning requirements; scalable across multiple jurisdictions  
**Status:** Prototype in development, testing on sample municipal codes

**[View Project →](https://github.com/yourusername/zoning-code-parser)**

---

### 🗺️ Municipal Zoning Map Georeferencing

**Challenge:** Georeferenced a scanned municipal zoning map to enable spatial analysis for renewable energy permitting. Scanned maps lack coordinate information and must be carefully aligned with authoritative reference data.

#### Technical Approach

**Data Sources:**
- Scanned municipal zoning map (PDF-derived raster)
- Reference parcel and street centerline vector layers

**Methodology:**
1. Verified coordinate reference systems (CRS) across all layers
2. Selected well-distributed Ground Control Points (GCPs) using road intersections and parcel corners
3. Evaluated transformation types to balance stability and spatial accuracy

#### Problem Encountered

During georeferencing, QGIS returned this error:
> *"Failed to compute GCP transform: Transform is not solvable"*

This occurred despite:
- Using a Polynomial 1 transformation
- Having sufficient GCPs (8+ points)
- Achieving acceptable mean error (~37 pixels)

The transformation *appeared* mathematically solvable, but the process still failed.

#### Root Cause Analysis

The failure stemmed from **data quality issues**, not insufficient GCPs:
- Corrupted or duplicated ground control points
- Invalid map X/Y coordinate values
- CRS inconsistencies between the raster and reference vector layers

This is a common geospatial data integrity issue where transformation coefficients can be computed, but the actual raster transformation fails due to invalid inputs.

#### Solution Implemented

Applied a systematic debugging workflow:

1. **Reset the session:** Cleared all existing GCPs and started fresh
2. **Explicitly defined target CRS** to match reference vector data
3. **Carefully re-selected GCPs** with verified coordinates and even spatial distribution
4. **Validated alignment** by overlaying the transformed raster with reference layers
5. **Documented the process** for future team use

**Result:** Successfully georeferenced map with accurate spatial alignment, enabling reliable site analysis for permitting diligence.

**Skills Demonstrated:** 
- Spatial data troubleshooting
- CRS management
- Systematic debugging methodology
- Technical documentation

---

### 🔄 ArcGIS Online Conversion to QGIS Data 

**Challenge:** Paces uses QGIS, but many municipalities and utilities publish spatial data exclusively through ArcGIS Online. Accessing this data requires understanding REST service structures and format conversion.

**My Contribution:** Developed and documented a workflow to:
- Identify ArcGIS REST service endpoints using browser developer tools
- Extract feature service URLs from ArcGIS Online portals
- Import data directly into QGIS for local analysis
- Validate geometry and attribute integrity post-conversion

**Tools:** ArcGIS REST APIs, QGIS, browser DevTools  
**Impact:** Team can access critical municipal/utility datasets without ArcGIS licenses  
**Documentation:** Created step-by-step guide for team replication

**Skills Demonstrated:**
- Web service interaction
- Cross-platform data workflows
- Process documentation

---

## 🛠️ Technical Skills

**GIS & Spatial Analysis**
- QGIS: digitization, georeferencing, spatial joins, data conversion
- ArcGIS Online: REST service data extraction
- Coordinate reference systems and spatial data validation
- Troubleshooting common geospatial errors

**Data & Automation**
- Python: Pandas, text processing, file I/O
- SQL: Basic queries and data extraction
- Data cleaning and quality control workflows
- REST API interaction

**Domain Knowledge**
- Zoning regulations and interpretation
- Renewable energy permitting processes
- Municipal data sources and formats
- Land-use planning terminology

**Soft Skills**
- Technical documentation
- Systematic problem-solving
- Cross-functional collaboration
- Process improvement mindset

---

## 📈 What Drives My Work

I'm fascinated by how **data infrastructure enables faster climate action**. The renewable energy industry needs to move at speed, and clean, accessible permitting data is a critical unlock.

At Paces, I'm learning to think about data the way software engineers do:
- **Scalable:** Workflows that work for 1 municipality should work for 100
- **Documented:** Clear processes that others can replicate and improve
- **Quality-first:** Bad data is worse than no data

I'm building skills that bridge **domain expertise** (policy, permitting, energy) with **technical execution** (GIS, Python, data pipelines)—because that's where I can have the most impact.

---

## 🎓 Continuous Learning

**Currently exploring:**
- Python GIS libraries (geopandas, shapely)
- Advanced SQL for spatial databases (PostGIS)
- Workflow automation and scripting
- Data pipeline best practices

**Recent learning:**
- How to systematically debug spatial data issues
- REST API structures for geospatial services
- Text parsing techniques for policy documents

---

## 📫 Let's Connect

- 💼 **LinkedIn:** www.linkedin.com/in/charlotteychapman
- 📧 **Email:** chacychapman@gmail.com
- 🌐 **Notion Portfolio:**[(https://bedecked-walker-bc6.notion.site/Charlotte-Chapman-Portfolio-2e78a32c4bd780e3b142ce464902738e?pvs=74)]
---

## 💡 Why This Work Matters

Every zoning map I digitize, every workflow I document, and every dataset I clean contributes to a larger mission: **helping renewable energy developers identify viable sites faster.**

In an industry racing to meet climate goals, reducing friction in the siting and permitting process isn't just about efficiency—it's about impact.

---

*Building cleaner data infrastructure for renewable energy development, one project at a time.*



