# Survivor-Complier-Effects-in-the-Presence-of-Selection-on-Treatment-With-Application-to-a-Study-of-

# Author Contributions Checklist Form

## Data

### Abstract 

The data in our study are from the SPOTlight study (Harris 2015) which collected data on a prospective cohort of patients with deteriorating health referred for assessment for ICU admission in 48 UK National Health Service (NHS) hospitals between 1 November 2010 and 31 December 2011. Data for the simulation is generated in the code.

### Availability 

The data we use are not yet publically available. We have provide a pseudo-version of the data. The pseudo version of the data is a resample of the original data sampled with replacement. The resample is close to the original version of the data.

### Additional Information

Unique identifier / DOI: [doi:10.7910/DVN/UOJGJK](doi:10.7910/DVN/UOJGJK).

## Code

### Abstract

The included R code produces all results and figures in the paper.

### Description 

* Download from Dataverse: [doi:10.7910/DVN/UOJGJK](doi:10.7910/DVN/UOJGJK).

* Licensing information: MIT License.

## Instructions for Use

### Reproducibility 

R Packages needed for replication:

* library(foreign) 0.8-67
* library(AER) 1.2-4
* library(dplyr) 0.5.0
* library(multcomp) 1.4-6
* library(BSagri) 0.1-8
* require(geepack) 1.2-1
* library(sandwich) 2.3-4
* library(tmle) 1.2.0-4

Results produced using R 3.3.2.

### Replication Outline

**Data:** While we were unable to release the original data, we generated pseudo data by resampling from the original data with replacement. We resampled until we generated a resample that was close to the distribution of the original data.

**Code:** Produces the main results from the paper.

**/Section3.2:** These scripts produce all the results.
* ICU_Bounds - This script produces the estimated bounds dervied in the paper. It produces the bounds with and without covariates. This script also produces Figure 3, which reports the results from the sensitivity analysis.
* IV_Est - This script applies the Wald estimator via 2SLS to the data in the S=1 strata
* G-Est Method 1 - This script produces estimates of the ICU wait time effect using the g- estimation methods using IP weight
* G-Est Method 2 - This script produces estimates of the ICU wait time effect using the g- estimation methods using IP weight in the S=1 strata.

**./Section1.3:** 
* Figure_1.R - produces Figure 1 in the paper. 

**./Section4:**
* simulation_nocovs.R - produces the simulation results reported in Section 4 when there are no covariates.
* sim_summary_nocovs.R - produces the results in Figure 4 in Section 4 for when there are no covariates
* simulation_glm_low.R - produces the simulation results reported in Section 4 when there are low noise covariates.
* simulation_glm_high.R - produces the simulation results reported in Section 4 when there are high noise covariates.
* sim_summary_glm.R - produces the results in Figure 4 in Section 4 for when there are either high or low noise covariates

**./functions:**
* scate_funcs.R - Contains 3 functions used in the analysis. One generates simulated data used in the simulations. One generates bounds on the SCATE without using covariate information. The final one generates bounds bounds on the SCATE using covariate information.

**./routput:**
* iv_bounds.RData - results from the simulation. Forms the input for sim_summary_nocovs.R. -iv_bounds_covs_high.RData - results from the simulation with high noise covariates. Forms the input for sim_summary_glm.R.
* iv_bounds_covs_low.RData - results from the simulation with low noise covariates. Forms the
input for sim_summary_glm.R.

