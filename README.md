# ⚽ Women's vs Men's FIFA World Cup: Goal-Scoring Hypothesis Test

A hypothesis testing project built with Python, completed as part of the **DataCamp Data Analyst in Python** track.

## Research Question

**Do women's FIFA World Cup matches have higher goal-scoring values than men's matches?**

## Hypotheses

- **Null hypothesis (H₀):** The number of goals scored per match is the same for women's and men's FIFA World Cup matches.
- **Alternative hypothesis (H₁):** Women's FIFA World Cup matches have higher goals per match than men's matches (one-sided test).
- **Significance level (α):** 0.10

## Data

Two datasets of international football results were provided by DataCamp:

| File | Description |
|---|---|
| `women_results.csv` | Women's international match results |
| `men_results.csv` | Men's international match results |

After filtering to **FIFA World Cup** matches played from **1 January 2002** onwards, the analysis used **584 matches**:

- **200** women's matches
- **384** men's matches

> The datasets are not included in this repository because they were supplied through DataCamp. To rerun the notebook, place both CSV files in the project folder and update the file paths in the loading cell.

## Approach

1. **Data preparation:** loaded both datasets with Pandas and converted the `date` columns to datetime.
2. **Filtering:** kept only `FIFA World Cup` matches played on or after 2002-01-01.
3. **Feature engineering:** created `goals_scored` as home score plus away score for each match.
4. **Exploratory data analysis:** compared goal distributions with histograms, box plots and a bar chart of average goals.
5. **Normality check:** applied the Shapiro-Wilk test to each group.
6. **Hypothesis test:** applied the one-sided Mann-Whitney U test (`alternative="greater"`), using Pingouin and cross-checking with SciPy.
7. **Decision:** compared the p-value with α = 0.10.

## Results

| Metric | Value |
|---|---|
| Test | Mann-Whitney U (one-sided) |
| p-value | **0.0051** |
| Significance level | 0.10 |
| Decision | **Reject the null hypothesis** |

The p-value is below the chosen significance level, so there is statistical evidence that goals per match tend to be higher in women's FIFA World Cup matches than in men's matches since 2002.

**Why Mann-Whitney U?** Goals per match are count data, and the Shapiro-Wilk test was used to check normality. Because the data is not normally distributed, a non-parametric test for two independent groups was the appropriate choice instead of a t-test.

## Limitations

- The result describes a difference in goal-scoring distributions. It does not explain why the difference exists.
- The sample covers World Cup matches since 2002 only, and the numbers of men's and women's matches differ.
- Total goals per match is influenced by the number of teams, tournament format and the mix of fixtures, which this analysis does not control for.

## Tools and Libraries

- Python
- Pandas
- Matplotlib
- SciPy
- Pingouin

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
   cd YOUR-REPO-NAME
   ```
2. Install the dependencies:
   ```bash
   pip install pandas scipy matplotlib pingouin jupyter
   ```
3. Add `women_results.csv` and `men_results.csv` to the project folder and update the file paths in the notebook.
4. Open and run `Hypothesis_Testing_Project.ipynb`.

## What I Learned

- Writing null and alternative hypotheses, including choosing a one-sided test.
- Interpreting p-values and significance levels.
- Testing for normality and choosing between parametric and non-parametric tests.
- Communicating statistical findings clearly with visualisations.

## Author

**YOUR NAME**
[LinkedIn](https://www.linkedin.com/in/your-profile) | [GitHub](https://github.com/YOUR-USERNAME)
