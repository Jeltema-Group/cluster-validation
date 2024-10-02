# cluster-validation
Assess the performance of optical cluster finders for sanity checks on LSST data 

Compares/Matches an input Optical catalog to a well-centered X-Ray cluster catalog and the SPT 2500d SZ cluster catalog and performs the   following:

- Finds cross matches between the optical input and the two truth catalogs using ClEvaR
  - Matches are found based off of a specificed offset radius and redshift range
  - Completeness Plot for SPT/Optical
- Takes the sample of matched Optical/X-Ray Clusters and calculates the distance between the Optical and X-Ray centers
  - Fits a two-component gamma distribution model to the well-centered and miscentered clusters
  - Creates a corner plot of parameter constraint distributions
  - Plots histogram of X-Ray peak to input catalog position offsets
- Fit scaling relations using the matched clusters between X-Ray temperature and richness, as well as SZ signal-to-noise ratio and richness
  - Fit is created using linmix
  - Option to run CluStR package for more explicit statistics 
