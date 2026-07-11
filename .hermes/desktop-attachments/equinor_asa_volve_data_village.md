
# **equinor_asa_volve_data_village** Catalog Summary

## Overview
This catalog contains the complete **Volve Field dataset** - Equinor's open-source oil and gas field data from the North Sea. This is the **SOURCE catalog** where all the raw data files are stored that we used to create the 9 tables in `workspace.volve_data`.

## Structure

### **Schemas:**
1. **information_schema** - System metadata schema
2. **public** - Main data schema

### **Volumes:**

#### **1. volve** - Main data volume (uncompressed files)
13 directories with raw field data:

#### **2. volvezipfiles** - Compressed archive volume
14 ZIP files (4.8 TB total compressed data)

---

## 📊 **Volve Volume Contents** (Source Files)

### **1. 📈 Production_data/**
- **Volve production data.xlsx** (2.3 MB)
- Daily and monthly production data by well
- *Used to create: production_data_daily (15,634 records) & production_data_monthly (526 records)*

### **2. 🛢️ Well_logs/**
14 subdirectories organized by log type:
- **01.MUD_LOG/** - Mud logging data
- **02.LWD_EWL/** - Logging While Drilling
- **03.PRESSURE/** - Pressure measurements
- **04.COMPOSITE/** - Composite log data
- **05.PETROPHYSICAL INTERPRETATION/** - Petrophysical analysis
- **06.LFP/** - LFP logs
- **07.IMAGE/** - Borehole imaging
- **08.VSP_VELOCITY/** - Vertical Seismic Profile
- **09.CORE/** - Core analysis data
- **10.PRODUCTION LOGS/** - Production logging
- **11.INTEGRITY LOGS/** - Casing/cement integrity
- **12.BIOSTRAT/** - Biostratigraphy
- **13.GEOCHEM/** - Geochemistry
- **14.DIV. REPORTS/** - Miscellaneous reports
- **VOLVE_INVENTORY.xlsx** (91 KB) - Master inventory file
  - *Used to create: well_logs_inventory (575 records)*

### **3. 📡 WITSML Realtime drilling data/**
- 26 wells with real-time drilling XML files
- *Used to create: witsml_bha_runs (161 records), witsml_drilling_messages (11,134 records), witsml_wellbores (33 records), witsml_log_inventory (7,150 records), drilling_telemetry (2,652,891 records)*

### **4. 📄 Reports/**
- PDF reports and documentation
- *Used to create: reports_catalog (2 records)*

### **5. 🗺️ Geophysical_Interpretations/**
- Seismic interpretations and horizon picks

### **6. 🌊 Seismic/**
- 3D/4D seismic data volumes
- ST0202, ST10010 surveys
- VSP (Vertical Seismic Profile) data

### **7. 🏗️ Reservoir_Model-Eclipse_model/**
- ECLIPSE reservoir simulation model files

### **8. 🎯 Reservoir_Model-RMS_model/**
- RMS (Reservoir Modeling System) files

### **9. 🪨 GeoScience_OW_Archive/**
- OpenWorks geological archive

### **10. 🏭 PI System Manager Sleipner/**
- PI historian data from Sleipner platform

### **11. 🔧 Well_technical_data/**
- Well completion diagrams
- Casing programs
- Technical specifications

### **12. 📁 Well_logs_pr_WELL/**
- Well logs organized by individual well

### **13. 📋 License & Terms**
- **HRS and Terms and conditions for license to data - Volve.pdf** (213 KB)

---

## 📦 **VolvezipFiles Volume** (Compressed Archives)

| File | Size | Description |
|------|------|-------------|
| **Volve_Seismic_ST10010.zip** | 2.6 TB | Largest seismic survey |
| **Volve_Seismic_ST0202.zip** | 1.2 TB | Base seismic survey |
| **Volve_Seismic_ST0202vsST10010_4D.zip** | 330 GB | 4D seismic difference |
| **Volve_GeoScience_OW_Archive.zip** | 54.6 GB | Geological archive |
| **Volve_Well_logs_pr_WELL.zip** | 7.0 GB | Well logs by well |
| **Volve_Well_logs.zip** | 6.9 GB | Well logs by type |
| **Volve_WITSML Realtime drilling data.zip** | 2.3 GB | Drilling XML data |
| **Volve_Reservoir_Model-RMS_model.zip** | 2.1 GB | RMS reservoir model |
| **Volve_Reservoir_Model-Eclipse_model.zip** | 390 MB | ECLIPSE model |
| **Volve_Well_technical_data.zip** | 212 MB | Well engineering data |
| **Volve_Reports.zip** | 162 MB | Field reports |
| **Volve_Geophysical_Interpretations.zip** | 99 MB | Seismic interpretations |
| **Volve_Seismic_VSP.zip** | 95 MB | VSP data |
| **Volve_Production_data.zip** | 1.9 MB | Production Excel file |

**Total:** ~4.8 TB of compressed data

---

## 🔗 **Relationship to workspace.volve_data Tables**

The 9 tables we created in workspace.volve_data were extracted from files in this catalog:

| Source Volume File | → | Created Tables |
|-------------------|---|----------------|
| `volve/Well_logs/VOLVE_INVENTORY.xlsx` | → | well_logs_inventory (575) |
| `volve/Production_data/Volve production data.xlsx` | → | production_data_daily (15,634), production_data_monthly (526) |
| `volve/Reports/*.pdf` | → | reports_catalog (2) |
| `volve/WITSML Realtime drilling data/` | → | witsml_bha_runs (161), witsml_drilling_messages (11,134), witsml_wellbores (33) |
| `volvezipfiles/Volve_WITSML Realtime drilling data.zip` | → | witsml_log_inventory (7,150), drilling_telemetry (2,652,891) |

---

## 🎯 **Key Differences**

| Feature | equinor_asa_volve_data_village | workspace.volve_data |
|---------|-------------------------------|---------------------|
| **Type** | Raw file storage (Volumes) | Structured Delta tables |
| **Format** | XLSX, XML, PDF, DLIS, LAS, SEGY | Delta Lake tables |
| **Access** | File system operations | SQL queries |
| **Size** | ~4.8 TB compressed | 2.7M records |
| **Purpose** | Source data archive | Analytics-ready tables |

**Note:** This catalog contains the **complete Volve field dataset** - far more data than we've ingested. The seismic data alone (4+ TB) has not been converted to tables. Opportunities exist to extract more value from well logs, cores, reports, and reservoir models stored here!