# 💊 Italian Medicines Dataset Construction & Analysis

This project focuses on building a **structured dataset of medicines authorized in Italy** using official data from the **Italian Medicines Agency (AIFA)**.

The project simulates the real-world workflow of a **data extraction and data engineering pipeline**, starting from raw regulatory sources and ending with **data analysis dashboards and SQL queries**.

---

# 📊 Project Overview

The objective of the project is to construct a structured dataset containing regulatory and clinical information about medicines available in Italy.

The dataset is built using information extracted from the official AIFA portals and includes both **regulatory metadata** and **clinical descriptions from product leaflets**.

---

# 🗄 Data Sources

The primary data source is the official AIFA website.

Sources used:

- AIFA medicines lists
- Official product pages
- Summary of Product Characteristics (SPC)

Two datasets were initially downloaded:

| Dataset | Size |
|------|------|
| Class A medicines | ~10,400 records |
| Class H medicines | ~2,100 records |

These datasets were merged into a single dataset before processing.

---

# 🧱 Dataset Schema

Each row in the dataset corresponds to a **single medicine identified by its AIC code**.

Main columns include:

| Column | Description |
|------|------|
| AIC | Unique medicine identifier |
| Principio Attivo | Active ingredient |
| Descrizione Gruppo | Therapeutic group |
| Denominazione e Confezione | Medicine name and packaging |
| Titolare AIC | Marketing authorization holder |
| Codice Gruppo Equivalenza | Equivalence group code |
| Classe | Reimbursement class |
| ATC | Anatomical Therapeutic Chemical classification |
| URL | Link to official product leaflet |

Clinical sections extracted from the SPC include:

- Therapeutic indications
- Dosage and administration
- Contraindications
- Warnings and precautions
- Drug interactions
- Pregnancy and fertility information
- Side effects
- Overdose information

---

# ⚙️ Data Construction Workflow

Instead of a traditional ML pipeline, the project follows a **data engineering workflow**:

### Data Extraction

- Download official medicine lists
- Merge Class A and Class H datasets
- Filter relevant columns

### Clinical Information Retrieval

For each medicine:

1. Use the **AIC code** to locate the medicine on the AIFA portal
2. Open the **Summary of Product Characteristics**
3. Extract mandatory clinical sections
4. Add the extracted information to the dataset

### Data Cleaning

The dataset was cleaned by:

- removing empty rows
- eliminating duplicate entries
- validating identifiers

The final dataset contains **approximately 1300 medicines**.

---

# 🗃 Database Design

The dataset was imported into a **relational database system**.

Normalization was applied to structure the data efficiently.

Possible tables include:

- Medicines
- Active Ingredients
- Therapeutic Groups
- Clinical Information
- Side Effects

This structure allows efficient querying and analysis.

---

# 🔍 SQL Analysis

Several SQL queries were designed to analyze the dataset.

Examples include:

- medicines grouped by **equivalence group**
- most common **contraindications**
- medicines distribution by **ATC classification**
- most frequent **active ingredients**
- analysis of **side effects prevalence**

---

# 📊 Data Visualization

The dataset was imported into **Power BI** to create an analytical dashboard.

Key visualizations include:

- medicines distribution by **active ingredient**
- therapeutic indications frequency
- side effects distribution
- medicines grouped by ATC classification

These dashboards provide a high-level overview of the Italian medicines landscape.

---

# 🚀 Project Outcomes

This project demonstrates the full lifecycle of a **data engineering and analytics workflow**:

- raw data extraction
- dataset construction
- relational database design
- analytical querying
- dashboard visualization

It simulates the type of workflow used in **healthcare data management and regulatory data analysis**.

---
