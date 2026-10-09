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

This plot is used to explore how tip amount varies with the total bill
and to compare the displayed groups by sex and smoking status.

### 2. Bar Plot --- Titanic Fare by Passenger Class and Sex

**Variables:** `Pclass` vs. `Fare`, grouped by `Sex`.

This visualization compares fares across passenger classes and sex
categories. It helps inspect differences in the average fare represented
by each group.

### 3. Box Plot --- Age by Sex and Survival

**Variables:** `Sex` vs. `Age`, with `Survived` as the hue.

The box plot compares age distributions across sex and survival groups,
showing the median, spread, and potential outliers.

### 4. Age Distribution --- Survivors vs. Non-survivors

The notebook overlays age-density curves for passengers with
`Survived = 0` and `Survived = 1`.

**Insights recorded in the notebook:** - The author notes that children
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

### 7. Survival Rate by Sex

The notebook calculates survival percentage by sex.

  Sex        Survival rate
  -------- ---------------
  Female            74.20%
  Male              18.89%

**Insight:** the notebook's results show a much higher survival rate
among female passengers than male passengers in this dataset.

### 8. Survival Rate by Embarkation Port

The notebook plots the mean of `Survived` by `Embarked`.

  Embarkation code     Survival rate
  ------------------ ---------------
  `C`                         55.36%
  `Q`                         38.96%
  `S`                         33.70%

**Insight:** among the embarkation groups shown, `C` has the highest
observed survival rate and `S` the lowest. This is a descriptive
association and does not establish that embarkation port caused the
difference.

### 9. Pair Plot --- Iris Dataset

Before plotting, the notebook selects the first three columns of the
Iris dataset and computes their correlation matrix. It then creates a
pair plot of the Iris features, using `species` as the hue.

This allows pairwise feature relationships and species-level separation
to be explored visually.

### 10. Line Plot --- Annual Flight Passenger Totals

The notebook groups the `flights` dataset by `year`, sums monthly
passenger counts, and plots the annual totals.

The displayed totals increase from **1,520 in 1949** to **5,714 in
1960**, showing an upward trend across the years covered by the dataset.

### 11. Pivot Table and Heatmap --- Monthly Flight Passengers by Year

The notebook creates a pivot table with: - **Rows:** month -
**Columns:** year - **Values:** passenger count

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

*This README follows the order of the analysis and charts in the
notebook and preserves the observations written alongside them.*

## Plot Gallery

The following figures are extracted from the notebook outputs and displayed in the same order as they appear in `Bivariate.ipynb`.

### Scatter Plot — Tips Dataset

![Scatter Plot — Tips Dataset](plots/plot_01.png)

### Bar Plot — Titanic Fare by Passenger Class and Sex

![Bar Plot — Titanic Fare by Passenger Class and Sex](plots/plot_02.png)

### Box Plot — Age by Sex and Survival

![Box Plot — Age by Sex and Survival](plots/plot_03.png)

### Age Distribution — Survivors vs. Non-survivors

![Age Distribution — Survivors vs. Non-survivors](plots/plot_04.png)

### Heatmap — Passenger Class vs. Survival Counts

![Heatmap — Passenger Class vs. Survival Counts](plots/plot_05.png)

### Survival Rate by Passenger Class

![Survival Rate by Passenger Class](plots/plot_06.png)

### Survival Rate by Sex

![Survival Rate by Sex](plots/plot_07.png)

### Survival Rate by Embarkation Port

![Survival Rate by Embarkation Port](plots/plot_08.png)

### Pair Plot — Iris Dataset

![Pair Plot — Iris Dataset](plots/plot_09.png)

### Line Plot — Annual Flight Passenger Totals

![Line Plot — Annual Flight Passenger Totals](plots/plot_10.png)

### Heatmap — Monthly Flight Passengers by Year

![Heatmap — Monthly Flight Passengers by Year](plots/plot_11.png)

