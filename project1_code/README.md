# Neuropixels Poisson Model Project

## What this is

This project models the number of detectable neurons per recording site using a one-parameter Poisson model.

It is based on the paper:

> Jun et al. (2017), *Fully integrated silicon probes for high-density recording of neural activity*, Nature.

The paper reports an average of **6.9 ± 5.1 detectable neurons per recording site**.

We define `X_i` as the number of detectable neurons at recording site `i`, and assume:

`X_i ~ Poisson(theta)`

where `theta` is the expected number of detectable neurons per site.

The notebook tests this model in both directions:

- **Forward:** set `theta = 6.9`, simulate recording-site counts with Monte Carlo, and compare the predicted spread with the paper.
- **Backward:** estimate `theta` from the paper's reported mean and SD using negative log-likelihood and Monte Carlo parameter searches.
- **Uncertainty:** repeat simulated experiments to see how much the fitted value of `theta` varies.

## What it found

The Poisson model reproduces the paper's **mean of about 6.9 neurons/site**, but predicts an SD of only about **2.6**, compared with the paper's reported SD of **5.1**.

Fitting the model to the mean gives:

`theta_hat(mean) ≈ 6.9`

while matching the reported SD requires approximately:

`theta_hat(SD) ≈ 26`

Therefore, no single Poisson parameter can reproduce both the mean and SD. The paper's variance is about **3.8 times the mean**, showing substantial overdispersion relative to a Poisson model.

The uncertainty analysis shows that the estimate of the mean is very stable under the model. Repeated simulations give estimates close to 6.9, with an SD of about **0.04** and an approximate 95% interval of **6.82–6.98**.

The main conclusion is that a single-rate Poisson model is a useful baseline, but it does not capture all of the variation in the recordings. Possible reasons include differences between brain regions or recording depths and non-independent detections at nearby recording sites.

## How to run it

### Requirements

- Python 3
- Jupyter Notebook
- `matplotlib`

### Run

1. Open `project.ipynb`.
2. Run all cells from top to bottom.

From a terminal, the notebook can be run with:

```bash
jupyter notebook
