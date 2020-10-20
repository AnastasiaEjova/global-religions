multi rate analysis with BEAST 2 and the MSBD package

xml: BEAST XML files for nested sampling analyses
results: summary trees + Bayes factors
figures: visualisations of results



# Methods

## Phylogenetic model description

The multi rate tree prior (Barido-Sottani et al, 2020) allows birth rates to change at arbitrary points along branches of a tree. Extinction rates are assumed to be constant, and estimated using a log-normal(-1,2) prior. Birth rates are estimated under a log-normal(-2,2) prior giving a wide range (95%HPD of 0.0027 - 6.82). For each of the three sets, we assume that 80% of the sects are included in the data set (reason for exclusions include lack of date of origin, or lack of other information about sects). For ancient sects, we assume 50% to be included in the data (though assuming we included only 10% did not substantially alter results). The prior on the rate of change was tuned for each of the three sets so that a priori about half the time there is no rate change and half the there is. A Poisson with mean 2 is used for the size of the pool of separate rates (potentially, there are more rates than rate changes, and some rates may remain unused). Furthermore, sampling times for the leaf nodes are used as prior. The likelihood consists of node calibrations encoding timing information and clade constraints based on manuscripts and other sources. 

Phylogenetic inference and model comparison is performed with BEAST v2.6.3 (Bouckaert et al, 2019) using nested sampling (Maturana et al, 2019). We compare the null hypothesis (H0) of no rate changes against the hypothesis at least one rate change was present (H1) by restricting to number of rate changes to 0 for H0 and to the range 1-10 for H1. We ran nested sampling with 500 points and 4 replicates to ensure convergence. Results and Bayes factors are in Table XXX. 

BEAST XML files are available as Supp Info XXX.



|Group|H0      |(SD)    |H1      |(SD)    |log BF  |BF 
|-----|--------:|--------:|--------:|--------:|--------:|------:
|Islam  | -185.37| 0.49    |-178.96| 0.48    |6.41    |607.89                          
|Indo-Iranian    |-430.27| 0.58    |-429.65| 0.58    |0.62       |1.86                            
|Judeo-Christianity |-532.34| 0.78    |-514.58| 0.76    |17.76   |51,649,961.08                           

Table XXX: marginal likelihood estimates from nested sampling for the two hypotheses H0: no rate changes, and H1: at least one rate change, and their standard deviations. Associated log Bayes factors (log BF) and Bayes factors (BF) in last two columns showing overwhelming support in favour of H1 for Islam and Judeo-Christianity, and no substantial difference for Indo-Iranian.



The tree in Figure XXX consists of the three MCC trees obtained by nested sampling. The dotted line near the centre are added to indicate an unknown common ancestry in the past.









Barido-Sottani J, Vaughan TG, Stadler T. A Multitype Birth–Death Model for Bayesian Inference of Lineage-Specific Birth and Death Rates. Systematic Biology. 2020 Feb 27.

Bouckaert R, Vaughan TG, Barido-Sottani J, Duchêne S, Fourment M, Gavryushkina A, Heled J, Jones G, Kühnert D, De Maio N, Matschiner M. BEAST 2.5: An advanced software platform for Bayesian evolutionary analysis. PLoS computational biology. 2019 Apr 8;15(4):e1006650.

Maturana Russel PM, Brewer BJ, Klaere S, Bouckaert RR. Model selection and parameter inference in phylogenetics using Nested Sampling. Systematic biology. 2019 Mar 1;68(2):219-33.
