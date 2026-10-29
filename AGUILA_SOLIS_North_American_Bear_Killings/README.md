# North American Bear Killings — Data Cleaning and Visualization

## 1. Group Information

- **Group Name:** Aguila_Solis_North_American_Bear_Killings
- **Members:** Aguila; Solis
- **Assigned Theme:** Data Cleaning and Visualization
- **Topic:** North American Bear Killings

## 2. Project Overview

- **Dataset Title:** North American Bear Killings
- **Source (URL or reference):** See `data/DATA_SOURCE.txt`. The actual CSV was not included with the uploaded notebook.
- **License/Attribution:** Confirm and add the dataset's original license/attribution before submission.
- **Objective:** Clean and validate the North American bear-killings dataset, prepare a model-ready version where appropriate, and create 10 visualizations to explore incident patterns by bear type, time, age, gender, and incident flags.

## 3. Flowchart

- **Flowchart image:** `flowchart/North_American_Bear_Killings_Flowchart_AGUILA_SOLIS.png`
- **PDF version:** `flowchart/North_American_Bear_Killings_Flowchart_AGUILA_SOLIS.pdf`

### Decisions in our flowchart

1. **Missing values or blank text fields?** If yes, trim/standardize text and fill missing `gender` values with `Unknown`. Other missing values are retained rather than inventing information. If no, keep values unchanged and record the check.
2. **Exact duplicate rows?** If yes, remove exact duplicate rows and record the before/after row counts. If no, keep all rows and record the count.
3. **Potential age outliers?** Use the IQR rule (1.5 × IQR). Flag potential outliers for review and retain the rows rather than automatically deleting valid extreme values.
4. **All 10 visualizations created?** If no, create the next plot and repeat. If yes, review titles, labels, legends, scales, and captions before ending.

### Changes we made

The flowchart represents the uploaded notebook's workflow. If the code changes, update this flowchart and this section so both remain consistent.

## 4. Preprocessing Summary

1. Load `north_america_bear_killings.csv`.
2. Inspect the dataset's shape, columns, data types, summary statistics, unique values, missing values, and duplicate count.
3. Standardize whitespace and blank text fields; fill missing `gender` with `Unknown`.
4. Detect and remove exact duplicate rows.
5. Standardize column labels; convert `age` to numeric; parse `Date`; correct `Month` and `Year` from valid dates; convert numeric flags to nullable integer types.
6. Use the IQR rule to flag potential `age` outliers without automatically deleting rows.
7. Derive `incident_month`, `incident_year`, `incident_decade`, and `incident_season` from valid dates.
8. One-hot encode `gender`, `Type`, and `Type of bear` in the model-ready dataset. Exclude `Name`, `Location`, `Description`, and raw `Date` from the model-ready feature matrix.
9. Create `age_scaled` using `StandardScaler` when enough valid age values are available; preserve the original `age`.
10. Save `cleaned_north_america_bear_killings.csv` and `model_ready_bear_killings.csv`.
11. Reload and validate the cleaned CSV, checking shape, duplicates, missing values, and selected data types.

## 5. Visualizations

Total: **10**

1. **Recorded incidents by bear type** — compares incident counts across bear types.
2. **Incidents by month** — shows the distribution of incidents across months.
3. **Incidents by year** — shows how recorded incidents vary over time.
4. **Age distribution** — shows the distribution of recorded ages.
5. **Age by bear type** — compares age distributions across bear types.
6. **Wild versus captive incidents** — compares recorded wild and captive incidents.
7. **Recorded incidents by gender** — compares records by gender category.
8. **Monthly incidents by bear type** — compares monthly patterns among bear types.
9. **Age and incident year** — explores the relationship between age and incident year.
10. **Incident flags** — summarizes the selected incident indicator fields.

Add a short, data-based caption below each plot in the notebook. Only report insights supported by the generated plot and data.

## 6. Key Insights

Complete this section after running the notebook. Add **3–5 findings** supported by the actual plots and dataset; do not guess results before execution.

## 7. How to Run

1. Obtain the dataset using the source details in `data/DATA_SOURCE.txt` and upload `north_america_bear_killings.csv` to Google Colab when prompted.
2. Open the notebook in Google Colab.
3. Run cells from top to bottom.
4. Install dependencies from `requirements.txt` if needed.
5. Check that both output CSV files are generated and that all 10 visualizations and captions are present.
