# Bivariate Analysis with Seaborn

This project explores relationships between variables using **Pandas**,
**Seaborn**, and **Matplotlib**. The notebook uses the Titanic training
dataset and Seaborn's built-in `tips`, `iris`, and `flights` datasets to
practise bivariate and multivariate visualization.

## Objectives

-   Explore relationships between numerical and categorical variables.
-   Compare Titanic passenger survival across passenger class, sex, age,
    and embarkation port.
-   Practise scatter plots, bar plots, box plots, distribution plots,
    crosstabs, heatmaps, pair plots, and line plots.
-   Summarize patterns observed in the charts and tables.

## Requirements

-   Python
-   Pandas
-   Seaborn
-   Matplotlib
-   Jupyter Notebook

Install the main libraries with:

``` bash
pip install pandas seaborn matplotlib jupyter
```

## Dataset Setup

The notebook loads: - `tips` --- Seaborn sample data for restaurant
bills and tips. - `iris` --- Seaborn sample data for flower measurements
and species. - `flights` --- Seaborn sample data for monthly passenger
counts by year. - `train.csv` --- the Titanic dataset, expected to be
available in the same directory as the notebook.

Open `Bivariate.ipynb` in Jupyter Notebook and run the cells in order.
The notebook calls `sns.load_dataset(...)` for the built-in datasets, so
an internet connection may be required if they are not already cached.

## Analysis and Visualizations

The sections below follow the order in which the plots and analyses
appear in the notebook.

### 1. Scatter Plot --- Tips Dataset

**Variables:** `total_bill` vs. `tip`\
**Encodings:** `sex` is shown with colour (`hue`) and `smoker` with
marker style.
<img width="563" height="433" alt="plot_01" src="https://github.com/user-attachments/assets/2e49ce00-0048-4d1e-924d-59105772eef1" />


This plot is used to explore how tip amount varies with the total bill
and to compare the displayed groups by sex and smoking status.

### 2. Bar Plot --- Titanic Fare by Passenger Class and Sex

**Variables:** `Pclass` vs. `Fare`, grouped by `Sex`.
<img width="571" height="432" alt="plot_02" src="https://github.com/user-attachments/assets/3796441c-28cf-4b9a-bb88-919d92220cee" />

This visualization compares fares across passenger classes and sex
categories. It helps inspect differences in the average fare represented
by each group.

### 3. Box Plot --- Age by Sex and Survival

**Variables:** `Sex` vs. `Age`, with `Survived` as the hue.
<img width="563" height="432" alt="plot_03" src="https://github.com/user-attachments/assets/bb6d539a-54d4-48df-a127-70cf7040044d" />


The box plot compares age distributions across sex and survival groups,
showing the median, spread, and potential outliers.

### 4. Age Distribution --- Survivors vs. Non-survivors

The notebook overlays age-density curves for passengers with
`Survived = 0` and `Survived = 1`.
<img width="585" height="432" alt="plot_04" src="https://github.com/user-attachments/assets/2eafa25f-d624-4bc8-b0e2-e9419f3743c1" />


**Insights recorded in the notebook:** - The  children
younger than 15 appear to have had higher survival. - The author notes
that deaths appear prominent among passengers aged 20--30. - The author
notes that passengers aged 60 and above appear to have had higher
mortality.

The explanations in the notebook about why these age groups had
different outcomes are interpretations, not conclusions established by
the plot alone.

### 5. Crosstab and Heatmap --- Passenger Class vs. Survival

A crosstab counts survival outcomes within each passenger class:

  Passenger class     Did not survive (`0`)   Survived (`1`)
  ----------------- ----------------------- ----------------
  1st class                              80              136
  2nd class                              97               87
  3rd class                             372              119

The heatmap visualizes these counts.
<img width="539" height="432" alt="plot_05" src="https://github.com/user-attachments/assets/7e8d4416-0f5b-4934-95a1-7edf5c5cd3a0" />


**Insight recorded in the notebook:** third-class passengers had
substantially more deaths, while first-class passengers had fewer
deaths. These are counts; they should not be confused with within-class
survival percentages.

### 6. Survival Rate by Passenger Class

The notebook calculates the mean of `Survived` by `Pclass` and
multiplies it by 100.

  Passenger class     Survival rate
  ----------------- ---------------
  1st class                  62.96%
  2nd class                  47.28%
  3rd class                  24.24%

**Insight:** the recorded survival rate is highest for first class and
lowest for third class.
<img width="543" height="432" alt="plot_06" src="https://github.com/user-attachments/assets/6af84f86-9bf9-43b4-851d-6c3dc3f6479b" />


### 7. Survival Rate by Sex

The notebook calculates survival percentage by sex.

  Sex        Survival rate
  -------- ---------------
  Female            74.20%
  Male              18.89%
  
  <img width="543" height="466" alt="plot_07" src="https://github.com/user-attachments/assets/dc9f0529-741e-46fe-beed-81bb8977f9dd" />


**Insight:** the notebook's results show a much higher survival rate
among female passengers than male passengers in this dataset.

### 8. Survival Rate by Embarkation Port

The notebook plots the mean of `Survived` by `Embarked`.

  Embarkation code     Survival rate
  ------------------ ---------------
  `C`                         55.36%
  `Q`                         38.96%
  `S`                         33.70%
  <img width="547" height="429" alt="plot_08" src="https://github.com/user-attachments/assets/53a5384c-2b78-43db-8367-bdfc4a78e023" />


**Insight:** among the embarkation groups shown, `C` has the highest
observed survival rate and `S` the lowest. This is a descriptive
association and does not establish that embarkation port caused the
difference.

### 9. Pair Plot --- Iris Dataset

Before plotting, the notebook selects the first three columns of the
Iris dataset and computes their correlation matrix. It then creates a
pair plot of the Iris features, using `species` as the hue.
<img width="1112" height="986" alt="plot_09" src="https://github.com/user-attachments/assets/aed454ae-2958-4812-8dc4-ade861447466" />


This allows pairwise feature relationships and species-level separation
to be explored visually.

### 10. Line Plot --- Annual Flight Passenger Totals

The notebook groups the `flights` dataset by `year`, sums monthly
passenger counts, and plots the annual totals.
<img width="580" height="432" alt="plot_10" src="https://github.com/user-attachments/assets/f1c300dc-f840-499d-a234-203a972607df" />


The displayed totals increase from **1,520 in 1949** to **5,714 in
1960**, showing an upward trend across the years covered by the dataset.

### 11. Pivot Table and Heatmap --- Monthly Flight Passengers by Year

The notebook creates a pivot table with: - **Rows:** month -
**Columns:** year - **Values:** passenger count
<img width="539" height="454" alt="plot_11" src="https://github.com/user-attachments/assets/ccba2cb9-0519-4f8d-bee3-dd510ab6d7e0" />


A heatmap then visualizes the monthly passenger counts across years,
making seasonal patterns and changes over time easier to compare.

## Key Takeaways

-   The notebook demonstrates several ways to examine relationships
    between two or more variables.
-   In the Titanic data shown, survival differs substantially by
    passenger class and sex.
-   The embarkation-port and age plots show descriptive patterns that
    should be interpreted cautiously; visualization alone does not prove
    causation.
-   The Iris pair plot demonstrates pairwise feature exploration, while
    the Flights line plot and heatmap show time-related trends and
    monthly variation.

## Project Files

-   `Bivariate.ipynb` --- notebook containing the analysis and
    visualizations.
-   `train.csv` --- Titanic dataset required by the notebook.

## How to Run

1.  Place `Bivariate.ipynb` and `train.csv` in the same project
    directory.
2.  Install the required Python libraries.
3.  Open the notebook in Jupyter.
4.  Run the cells from top to bottom to reproduce the tables and
    visualizations.

------------------------------------------------------------------------


