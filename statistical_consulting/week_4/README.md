# Week 4: Descriptive Analysis Report

## 1. Project Summary
This project performs an initial descriptive analysis on a customer dataset to assess baseline comparability between Control and Treatment groups. It automates data loading (with dynamic separator detection), generates a demographic summary table including Standardised Mean Differences (SMDs), and produces visualisations to check for outliers in Average Order Value (AOV). The goal is to determine if the dataset supports a defensible narrative for decision-making.

## 2. Data Description
The analysis uses CSV files located in `week_4/data/raw/`.

* **Unit of Analysis:** Each row represents a single **customer**.
* **Key Variables:**
    * `group` (Group Variable): The experimental assignment (Control vs. Treatment).
    * `avg_order_value_gbp` (Target Variable): The average order value in GBP.
    * `customer_type`: Categorical indicator (e.g., Existing vs. New).
    * `web_sessions_last_30d`: Behavioral metric for recent activity.
    * `customer_id`: Unique identifier (excluded from summary statistics).

## 3. Dependencies
This project uses `renv` for dependency management to ensure the analysis is reproducible.

**Core R Libraries used:**
* `ggplot2`, `gtsummary`, `gt`, `smd` (Visualization, Tables, and Balance Checks)
* `dplyr`, `janitor`, `readr` (Data Wrangling)
* `here` (Relative file paths)

**How to restore the environment:**
1.  Open the project in RStudio and ensure the `.Rproj` file is active.
2.  Run the following command in the console to install the exact package versions used in this analysis:

    ```r
    renv::restore()
    ```

## 4. Run Steps
To replicate the analysis:

1. **Verify Directory Structure:** Ensure your project has the following structure relative to the project root:

    ```r
    week_4
    ├── data
    │   ├── processed
    │   └── raw
    │       ├── week4_dataset.csv
    │       └── week4_dataset_updated.csv
    ├── DATA_DICTIONARY.md
    ├── outputs
    │   ├── figures
    │   │   ├── boxplot_original.png
    │   │   ├── boxplot_updated.png
    │   │   ├── boxplot__updated.png
    │   │   └── histogram_updated.png
    │   └── tables
    │       ├── table_1_original.html
    │       └── table_1_updated.html
    ├── README.md
    ├── reports
    │   ├── week_4_activity.html
    │   └── week_4_activity.Rmd
    └── src
    ```
   
2. **Execute via R Console**:
You can generate the HTML report and outputs for a specific dataset version by running the `rmarkdown::render` command in your RStudio Console. Below are example use cases for each version of the data. Please note that you can change the following parameters in the YAML header in the top of the report `.Rmd` file to suit your own preferences.

Make sure to change the `data_version` parameter as needed ("original" or "updated"):

```r
params:
  data_version: "original"
  group_var: "group"
  target_var: "avg_order_value_gbp"
```

```r
# Example: Render the report using the Original Dataset
rmarkdown::render("week_4/week_4_activity.Rmd", 
                  params = list(data_version = "original"))
```
```r
# Example: Render the report using the Updated Dataset
rmarkdown::render("week_4/week_4_activity.Rmd", 
                  params = list(data_version = "updated"))
```

## 5. Expected Outputs
Upon successful execution, the following files will be generated in week_4/outputs/. Filenames are dynamically suffixed based on the data version used.

* **Tables**:

    * tables/table_1_original.html: A formatted baseline summary table including SMDs to quantify group balance.

* **Figures**:

    * figures/boxplot_original.png: A box-plot of Average Order Value by Group to visualise skewness and outliers.

## 6. Assumptions and Limitations
**Assumptions**: The script assumes that if `data_version` is set to "original", the file is named `week4_dataset.csv`. For any other version (e.g., "updated"), it assumes the filename format `week4_dataset_{version}.csv`.

**Limitations**: The analysis is purely descriptive. While SMDs are used to check for balance, they only assess observed covariates and cannot account for unmeasured confounding variables. The presence of outliers in AOV suggests that mean-based comparisons may be sensitive to extreme values.
