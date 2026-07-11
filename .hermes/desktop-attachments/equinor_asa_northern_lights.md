
# **equinor_asa_northern_lights** Catalog Summary

## Overview
This catalog contains well data from the **Northern Lights CO₂ storage project** operated by Equinor. The data is stored in a managed Unity Catalog volume.

## Structure

### **Schemas:**
1. **information_schema** - System metadata schema
2. **public** - Main data schema

### **Volumes:**
- **northernlights** - Managed volume containing well data
  - Storage: Azure Data Lake (abfss://northernlights@equinoropendata.dfs.core.windows.net/)
  - Type: MANAGED VOLUME (Delta Sharing enabled)

---

## **Well Data: 31_5-7 Eos**

The volume contains comprehensive data for the **31/5-7 Eos exploration well**, organized into 13 categories:

### **1. 📊 Drilling & Completion**
`02.Drilling_and_Completion/`
- Drilling reports, mud logs, daily drilling reports
- Completion equipment and procedures

### **2. 📍 Directional Surveys**
`03.Directional_Surveys/`
- Wellbore trajectory data
- Survey measurements and deviation data

### **3. 📡 LWD (Logging While Drilling)**
`05.LWD_Log_data/`
- Real-time logging data collected during drilling
- Formation evaluation logs

### **4. 📈 Wireline Log Data**
`06.Wireline_Log_Data/`
- Post-drill wireline logging measurements
- Petrophysical property logs

### **5. 🔊 Borehole Seismic**
`07.Borehole_Seismic/`
- VSP (Vertical Seismic Profile) data
- Acoustic measurements

### **6. 💧 Formation Pressure Data**
`08.Formation_Pressure_Data/`
- Pressure measurements
- Pore pressure analysis

### **7. 🧪 Well Test Data**
`09.Well_Test_Data/`
- Production test results
- Flow rate and pressure tests

### **8. 🛢️ Fluid Data**
`10.Fluid_Data/`
- Reservoir fluid properties
- PVT (Pressure-Volume-Temperature) analysis

### **9. 🪨 Core Data**
`11.Core_Data/`
- Physical core samples analysis
- CT scan data (DLIS format)
- Core photographs and descriptions

### **10. 🗺️ Geology Data & Evaluations**
`12.Geology_Data_and_Evaluations/`
- Geological interpretations
- Image log data (processed and depth-shifted, DLIS format)
- Stratigraphic analysis

### **11. 📊 Petrophysical Evaluations**
`13.Petrophysical_Data_Evaluations/`
- Rock properties analysis
- Porosity, permeability calculations

### **12. 📄 Final Well Report**
`14.Final_Well_Report_and_Completion_Log/`
- Complete well documentation
- Completion diagrams

### **13. 🔧 Production Logs**
`15.Production_Logs/`
- Production logging tool data
- Flow profiling

---

## Data Updates

- **Initial Upload:** 31.08.2020
- **Latest Update:** 29.09.2021
  - Added: Image log data (processed & depth-shifted) as DLIS
  - Added: CT scan data of cores as DLIS

---

## 🎯 Use Cases

This dataset is ideal for:
- **CO₂ storage research** - Northern Lights is a major carbon capture and storage project
- **Subsurface characterization** - Complete well dataset for reservoir modeling
- **Petrophysical analysis** - Integration of logs, cores, and tests
- **Educational purposes** - Comprehensive real-world well data

**Note:** Currently **no Delta tables** exist in this catalog. All data is stored as **raw files** (DLIS, LAS, PDF, etc.) in the volume and would need to be **parsed and ingested** into tables for SQL-based analysis.

Explore volume contents