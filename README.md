Statistical Inference with Excel — Luggnagg Population

Excel portfolio project by **Claudio Lombardi**, developed for the Statistical Inference with Excel course in the ProfessionAI Master in Data Analytics.

The project explores a simulated population of 250 individuals from the fictional country of Luggnagg. It covers subgroup selection, descriptive statistics, an approximate confidence interval, a two-sided Z test, Pearson correlation and simple linear regression.

## Workbook structure

| Worksheet | Content |
| --- | --- |
| Parameters | Recorded generation settings: probability 0.95, mean age 40 and standard deviation 12 |
| Data | 250 simulated ages and group assignments from 1 to 4 |
| Sample | IF-based selection of Group 2, containing 66 individuals |
| Statistical Insight | Sample statistics, 95% confidence interval, Z statistic and two-sided p-value |
| (Un)correlated Variables | Correlation of age with simulated sleep hours and shoe size |
| Linear Regression | Age versus census order, a scatterplot and prediction for index 160 |

The workbook uses Italian and English labels. The ages and group assignments are stored as fixed values in the portfolio version. Changing the Parameters sheet does not regenerate them.

## Verified results

| Metric | Saved result |
| --- | ---: |
| Population records | 250 |
| Group 2 sample size | 66 |
| Sample mean age | 42.9697 years |
| Sample standard deviation | 10.2477 years |
| Confidence level | 95% |
| Approximate Z confidence interval | 40.1626–45.7768 years |
| Two-sided Z-test p-value | 0.0120 |
| Pearson correlation: age and sleep hours | −0.0676 |
| Pearson correlation: age and shoe size | 0.0083 |
| Predicted age at census index 160 | 39.2457 years |

## Statistical approach

### Sample selection

The Sample sheet retains ages belonging to Group 2 using IF formulas. Other rows contain text placeholders, which the statistical functions ignore.

### Confidence interval and hypothesis test

The interval is centered on the sample mean and uses CONFIDENCE.NORM with the standard deviation calculated from the full simulated population. Its confidence level is linked to cell D2 in Statistical Insight.

The Z test compares the subgroup mean with the full simulated population mean. The one-sided Excel result is converted to a two-sided p-value using:

```text
Two-sided p-value = 2 × MIN(one-sided p-value, 1 − one-sided p-value)
```

At a 5% significance level, the saved result rejects equality under the approximation used. It does not establish a systematic or causal difference between the randomly assigned groups.

This is an educational Z approximation: the subgroup belongs to the same finite population used to obtain the reference mean and standard deviation, and no finite-population correction is applied. The interval and p-value should be interpreted within that simplified approach. The full population mean is already observable in this exercise.

### Correlation

Pearson correlations are close to zero for both simulated variable pairs. They describe weak observed linear associations; they do not establish independence or rule out nonlinear relationships. The workbook does not include significance tests for these correlations.

### Linear regression

The regression uses census order as X and age as Y. The prediction uses FORECAST.LINEAR directly on all 250 observations rather than manually entered, rounded coefficients.

Census order has no inherent explanatory meaning for age. This section demonstrates the regression workflow rather than a validated age-prediction model.

## Portfolio improvements

- Separated the 95% confidence level from the margin of error.
- Converted the Z test to a two-sided test.
- Linked confidence bounds to the confidence-level cell and aligned the standard deviation with the Z test.
- Standardized the sample ranges used for descriptive statistics.
- Replaced a manually calculated regression prediction with FORECAST.LINEAR.
- Revised the statistical commentary to explain assumptions and interpretation limits.

## Opening the workbook

Download `Statistical_Insight_Population_Luggnagg - Portfolio.xlsx` and open it in Microsoft Excel. Start with Parameters and Data, then follow the remaining worksheets.

The current workbook is a saved simulation snapshot. Some downstream data, including the correlation inputs and regression observations, are stored as values rather than linked dynamically to Data. If you replace the simulation, update those datasets and the written commentary as well as checking the analytical formulas and chart.

## Validation

The revised formulas and their saved results were inspected. The confidence bounds and the regression prediction were independently recomputed from the saved data and matched. No Excel error values were found in the saved cells. This verification does not constitute a visual layout review in desktop Excel.

## Skills demonstrated

Microsoft Excel · Statistical inference · Descriptive statistics · Confidence intervals · Hypothesis testing · Pearson correlation · Linear regression · Conditional formulas · Simulated data analysis

## Author

**Claudio Lombardi** — [GitHub portfolio](https://github.com/PsyClaudio)
