# Data

This project uses summary statistics reported in:

Jun et al. (2017), *Fully integrated silicon probes for high-density recording of neural activity*, Nature.

The analysis in the paper reports an average density of 6.9 ± 5.1 detectable neurons per recording site. The pooled density analysis contains 3898 site-level observations.

The raw neuron counts for individual recording sites were not available to us. Therefore, this project uses the published summary statistics rather than a raw dataset.

## Files

### `paper_summary.csv`

The file contains one row and the following columns:

| Column | Description |
|---|---|
| `mean_neurons_per_site` | Published mean number of detectable neurons per recording site (6.9) |
| `sd_neurons_per_site` | Published standard deviation across recording sites (5.1) |
| `n_site_observations` | Number of site-level observations represented in the pooled density analysis (3898) |

**Shape:** 1 row × 3 columns.
