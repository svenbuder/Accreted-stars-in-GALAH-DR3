# Repository for the paper on "Accreted Stars in GALAH+ DR3"

This repository includes all code to recreate the research presented in the publication  
**The GALAH Survey: Chemical tagging and chrono-chemodynamics of accreted halo stars with GALAH+ DR3 and *Gaia* eDR3**
by Sven Buder et al. (2021b), submitted to MNRAS and accessible via the [arXiv:2109.04059](https://arxiv.org/abs/2109.04059).

## Abstract

Since the advent of *Gaia* astrometry, it is possible to identify massive accreted systems within the Galaxy through their unique dynamical signatures. One such system, *Gaia*-Sausage-Enceladus (GSE), appears to be an early "building block" given its virial mass <img src="https://render.githubusercontent.com/render/math?math=> 10^{10}\,\mathrm{Msun}"> at infall (<img src="https://render.githubusercontent.com/render/math?math=z\sim 1-3">). In order to separate the progenitor population from the background stars, we investigate its chemical properties with up to 30 element abundances from the GALAH+ Survey Data Release 3 (DR3). To inform our choice of elements for purely chemically selecting accreted stars, we analyse 4164 stars with low-<img src="https://render.githubusercontent.com/render/math?math=\alpha"> abundances and halo kinematics. These are most different to the Milky Way stars for abundances of Mg, Si, Na, Al, Mn, Fe, Ni, and Cu. Based on the significance of abundance differences and detection rates, we apply Gaussian mixture models to various element abundance combinations. We find the most populated and least contaminated component, which we confirm to represent GSE, contains 1049 stars selected via [Na/Fe] vs. [Mg/Mn] in GALAH+ DR3. We provide tables of our selections and report the chrono-chemodynamical properties (age, chemistry, and dynamics). Through a previously reported clean dynamical selection of GSE stars, including <img src="https://render.githubusercontent.com/render/math?math=30 < \sqrt{J_R / \text{kpc km / s}} < 55">, we can characterise an unprecedented 24 abundances of this structure with GALAH+ DR3. Our chemical selection allows us to prevent circular reasoning and characterise the dynamical properties of the GSE, for example mean <img src="https://render.githubusercontent.com/render/math?math=\sqrt{J_R / \text{kpc km / s}} = 26_{-15}^{+9}"> We find only <img src="https://render.githubusercontent.com/render/math?math=(29 \pm 1)">% of the GSE stars within the clean dynamical selection region. We thus discuss chemodynamic selections (such as eccentricity and upper limits on [Na/Fe]).

## Questions we want to answer:

1. How can we best select accreted stars chemically within GALAH+ DR3 data?
2. Avoiding circular arguments, what dynamical space do the chemically selected GSE stars occupy and what are the chemical properties of the dynamically selected GSE stars?
3. Are the dynamically and chemically selected substructures truly the same, that is what is the quantitative overlap?
4. What can we learn from the stars of the chemical and dynamical selection that do and do not overlap?

## Key plot

There are 19 figures in the manuscript, but this one might be the most important one, as it compare the chemical and dynamical selections (left and right panels, respectively). Plotted are the selection planes in chemical space (top panels, [Na/Fe] vs. [Mg/Mn]) and dynamical space (bottom panels
properties, radial and azimuthal actions).

![Comparison of chemical and dynamical selections in their respective planes, [Na/Fe] vs. [Mg/Mn] (top panels) and L_Z vs. \sqrt{J_R}, respectively. Left panels (a and d):} Chemical selection (orange). Middle panels (b and e):} Overlap of chemical and dynamical selection (purple). Right panels (c and f):} Dynamical selection (red). Black background contours show the GALAH+ DR3 sample.](https://github.com/svenbuder/Accreted-stars-in-GALAH-DR3/blob/main/figures/chemdyn_selection_plane.png "Chemodynamic Selection Plane")

## Data and Reproducability

### Accessing the data used in this study
This study uses the main catalogues and value-added-catalogs of GALAH+ DR3. These are presented in [Buder et al., 2021a](https://ui.adsabs.harvard.edu/abs/2020arXiv201102505B).  
The catalogue filed are publically available via [DataCentral](https://cloud.datacentral.org.au/teamdata/GALAH/public/GALAH_DR3/).
To be able to rerun the scripts, please checkout this repository and copy the 5 VACs from GALAH+ DR3 into the directory *data/*.  

### Recreating the research
You can then rerun the 3 IPYNB notebooks provided in *figures/*
1. *chemical_differences.ipynb* to identify which elements are the telltale elements of accretion in GALAH+ DR3
2. *gaussian_mixture_models.ipynb* to apply Gaussian Mixture Models (GMMs) to select accreted stars chemically
3. *chronochemodynamic_comparison.ipynb* to compare the chrono-chemodynamic properties (stellar ages, chemisty, and dynamics) of the chemically and dynamically selected accreted stars

### Recreating our exact results
We note that to be able to reproduce our exact results, we have fixed the random seeding in numpy and saved our outcome of the GMMs for you to continue exploring.
Gaussian Mixture Models used to explore which combination of abundances is most promising can be found in *gmm_sampling/*.
Final extreme deconvolution Gaussian Mixture Models used for the final modelling can be found in *xdgmm/*.

