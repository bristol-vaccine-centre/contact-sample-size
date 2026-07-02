# Sample size considerations in social contact surveys for epidemic modelling

**Brooks-Pollock E, Danon L** \| University of Bristol

Code and data supporting the paper: *Sample size considerations in social contact surveys for epidemic modelling, worldwide, 2008–2025*

Social contact surveys are widely used to parameterise infectious disease transmission models, yet sample sizes are rarely formally justified. We reviewed 107 published surveys and quantified how sample size affects uncertainty in the reproduction number (R). We recommend a minimum of 1,000 participants for general-purpose contact surveys; above \~2,000, additional recruitment yields limited gains in precision.

------------------------------------------------------------------------

## Repository structure

```         
.
├── analysis.qmd                        # Main analysis (Quarto)
├── rapidreviewdata_update.csv          # Rapid review data (107 surveys)
├── contactsperson_withkids6.Rdata      # UK Social Contact Survey (pre-processed)
├── 3874557/                            # POLYMOD data (Zenodo record 3874557)
│   ├── 2008_Mossong_POLYMOD_participant_common.csv
│   └── 2008_Mossong_POLYMOD_contact_common.csv
├── Figure1.png                         # Distribution of survey sample sizes
└── Figure2.png                         # Eigenvalue and R_t estimates vs sample size (4 panels)
```

------------------------------------------------------------------------

## Data

**Rapid review:** `rapidreviewdata_update.csv` contains sample sizes and country/setting for 57 studies identified through a PubMed search for social contact surveys published between January 2008 and March 2025.

**UK Social Contact Survey:** `contactsperson_withkids6.Rdata` contains pre-processed data from 5,861 participants across Great Britain. Source: [Danon et al. 2012/2013](http://wrap.warwick.ac.uk/54273/).

**POLYMOD:** Raw data from [Zenodo record 3874557](https://zenodo.org/record/3874557) (Mossong et al. 2008). Place the two CSVs in a subdirectory called `3874557/`.

------------------------------------------------------------------------

## Reproducing the analysis

Requires R (≥ 4.2) and [Quarto](https://quarto.org) (≥ 1.3).

``` r
install.packages(c("tidyverse", "boot", "furrr", "patchwork"))
```

``` bash
quarto render analysis.qmd
```

Simulation chunks are cached. On first render, parallel processing uses all available cores minus one via `furrr`. Figures are written to the working directory at 600 dpi.

------------------------------------------------------------------------

## References

-   Danon et al. *J R Soc Interface*. 2012;9:2826–2833
-   Danon et al. *Proc R Soc B*. 2013;280:20131037
-   Mossong et al. *PLoS Medicine*. 2008;5:e74
-   Brooks-Pollock et al. *Phil Trans R Soc B*. 2021;376:20200276

------------------------------------------------------------------------

## Funding

EBP: NIHR HPRU in Evaluations and Behavioural Science. LD: UKRI EPSRC EP/Y028392/1. Both: Health Protection Research Focus Award in Vaccines, University of Bristol.

------------------------------------------------------------------------

Code: [MIT](LICENSE)
