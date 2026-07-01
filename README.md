# Bayesian Statistics Explained for Marketers

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/joedom99/bayesian-stats-for-marketers/blob/main/bayesian_stats_for_marketers.ipynb)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![SciPy](https://img.shields.io/badge/SciPy-stats-8CAAE6?logo=scipy&logoColor=white)](https://scipy.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Blog](https://img.shields.io/badge/Blog-Marketing%20Data%20Science-teal)](https://blog.marketingdatascience.ai)

Companion notebook for the article **"Bayesian Statistics Explained for Marketers"** on the [Marketing Data Science blog](https://blog.marketingdatascience.ai) by Joe Domaleski.

## What This Is

Marketers ask a simple question: "Is the new campaign actually better, or did we just get lucky?" This notebook answers that question two ways using the same data.

The running example is the fictional Acme Shoes landing page:

- Historical conversion rate: **3.0%**
- New campaign: **36 conversions from 1,000 visitors** (3.6% observed)

The Bayesian analysis says there is an **84% probability** the new page genuinely beats the benchmark. The Frequentist analysis says the result is **not statistically significant** (p = 0.154). Both are correct. They answer different questions. The article explains why, and this notebook shows the math.

## What's Inside

The notebook walks through:

1. **Building a prior.** A weakly informative Beta(3, 97) prior centered on the 3.0% historical rate.
2. **The conjugate update.** Beta prior + binomial data = Beta posterior. One line of arithmetic, no MCMC needed.
3. **Answering the business question.** P(true rate > 3.0%) computed directly from the Beta(39, 1061) posterior.
4. **The Frequentist comparison.** A Wilson 95% confidence interval and a one-sided exact binomial test on the same data.
5. **Prior sensitivity analysis.** Three very different priors (flat, weak, skeptical) converge to similar posteriors. The data does most of the talking.
6. **Credible vs. confidence intervals.** Same data, two intervals, two very different interpretations.

The notebook also generates the Python figures used in the article at 300 DPI.

## Quick Start

**Option 1: Google Colab (easiest).** Click the "Open in Colab" badge at the top. Everything runs top to bottom with no installs.

**Option 2: Run locally.**

```bash
git clone https://github.com/joedom99/bayesian-stats-for-marketers.git
cd bayesian-stats-for-marketers
pip install numpy scipy matplotlib jupyter
jupyter notebook bayesian_stats_for_marketers.ipynb
```

Requires Python 3.9+ with NumPy, SciPy, and Matplotlib. No other dependencies.

## Key Results

| Quantity | Value |
|---|---|
| Historical benchmark | 3.0% |
| Campaign data | 36 conversions / 1,000 visitors (3.6%) |
| Frequentist 95% CI (Wilson) | 2.61% to 4.94% |
| One-sided exact p-value | 0.154 (not significant at 0.05) |
| Bayesian prior | Beta(3, 97), mean 3.0% |
| Bayesian posterior | Beta(39, 1061), mean 3.55% |
| 95% credible interval | 2.54% to 4.72% |
| P(new page > benchmark) | 83.6% |

## Related Articles

This notebook supports a series of articles on marketing data science:

- [Marketing Data Science blog](https://blog.marketingdatascience.ai) - the full article archive
- The Bayesian statistics article builds toward Marketing Mix Modeling with Google's Meridian, covered in earlier articles on the blog.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

**Joe Domaleski** - [Marketing Data Science](https://blog.marketingdatascience.ai) | [Medium](https://medium.com/@marketingdatascience) | [GitHub](https://github.com/joedom99)
