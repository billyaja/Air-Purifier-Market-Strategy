# 🛠️ Technical Development Log

**Date:** 2026-02-15

**Analyst:** Billy Erickson Samosir

## 1. Directory & Environment Scaffolding

To ensure portability and clear separation of concerns, the project follows a standard data science taxonomy:

- `/data/raw/`: Immutable source datasets.
- `/data/metadata/`: Business context and problem statements.
- `/docs/`: General guides and presentation assets (Excluded from Git tracking).

**Environment Manager:** `uv` (Python 2026 standard) was used to ensure a deterministic environment with pandas, seaborn, and scipy.

## 2. Data Standardization (ETL)

Source filenames were converted to snake_case to simplify Power Query (M) and Python ingestion scripts, preventing pathing errors across different OS environments.

| Original Long Filename | New Standardized Filename |
|--------------------------|---------------------------|
| day-wise-state-wise-air-quality-index...csv | aqi_daily_india.csv |
| master-data-state-district-and-disease...csv | health_outbreaks_india.csv |
| master-data-state-vehicle-class...csv | vehicle_registrations_india.csv |
| population-projection-of-india...xlsx | population_projections_india.xlsx |

## 3. Power BI Architecture: Multi-Grain Star Schema

To ensure high performance and accurate filtering across disparate time-scales, we implemented a Star Schema with specialized "Grain Bridges":


![data_model](/docs/images/data_model.png)

- **Fact Tables:** `stg_aqi` (Daily), `stg_health` (Weekly), `stg_vehicles` (Monthly), `stg_population` (Monthly).
- **Dimension Tables:** `Dim_State` (Geography Master) and `Dim_Date` (Temporal Master).
- **Surrogate Keys:** Engineered YearMonth and YearWeek keys to resolve Many-to-Many relationship traps between the master calendar and monthly/weekly datasets.

## 4. Data Integrity & Normalization

- **Geography Normalization:** Used an in-line M-code dictionary to resolve truncated state names (e.g., "Madhya" → "Madhya Pradesh") ensuring 100% join coverage.
- **Surgical Auditing:** Identified and filtered "Footer" metadata rows in the health datasets (labeled "0" or "1") that caused critical data type conversion errors during load.
- **Case Sensitivity:** Applied Proper Case transformations to all regional attributes to prevent relationship breakage in Power BI.

## 5. Python-to-BI Integration

- Developed automated ingestion scripts to perform cross-dataset correlation analysis.

- Exported processed feature sets to `../data/processed/` to enhance the Power BI model with advanced analytical attributes derived during EDA.
