# econ3916-lab08-hypothesis-testing
# Hypothesis Testing — Is Job Training Worth It?

## Objective

I tested whether the National Supported Work (NSW) job training program raised participants' 1978 earnings, and how large and reliable that effect is.

## Methodology

- I loaded the LaLonde NSW job training experiment, which has 445 people: 185 trainees and 260 controls.
- I ran a one-sample t-test and a two-sample Welch's t-test on 1978 earnings.
- I wrote Welch's t-statistic as my own function, `welch_t()`, and checked its output against scipy on the full sample and on five subgroups.
- I computed Cohen's d to judge the size of the effect, not only whether it is statistically significant.
- I ran a power analysis to find the power of this study and the sample size needed to detect an effect of d = 0.3.
- I tested the treatment effect in 5 overlapping demographic subgroups, then applied Bonferroni and Benjamini-Hochberg corrections for multiple comparisons.
- I simulated p-value distributions under two conditions: when the null hypothesis is true and when it is false.

## Key Findings

Trainees earned $1,794.34 more in 1978 than controls. The difference is statistically significant (Welch's t = 2.6741, p = 0.0079). The Cohen's d of 0.2727 shows a small effect: the program helped, but the gap between groups is modest relative to the spread in earnings.

The subgroup results show why multiple testing matters. Before correction, 2 of the 5 subgroup effects were significant. After the Bonferroni correction, only 1 remained significant. Because the subgroups overlap and I ran several tests, I treat the uncorrected subgroup results with caution.
