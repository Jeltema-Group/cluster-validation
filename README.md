# Cluster Validation Pipeline
Assess the performance of optical cluster finders for sanity checks on LSST data 

## Installation

The cluster validation code is structured within a Jupyter notebook and combines several different pieces of code across multiple libraries

Most of the required packages are standard and pip-installable, however there are three packages that will need to be installed separately:
- ClEvaR (0.14.1), [`installation`](http://lsstdesc.org/clevar/source/installation.html)
- Linmix (0.1.0), [`installation`](http://lsstdesc.org/clevar/source/installation.html](https://linmix.readthedocs.io/en/latest/install.html))
- CluStR, [`installation`](https://github.com/sweverett/CluStR?tab=readme-ov-file)
    - Installation of CluStR is not strictly necessary, as the code already has pieces of it built in, but for more detailed plots and statistics for scaling relations, installation of CluStR may be desired and can be run in the notebook via an iPython environment.

A anaconda environment with all of the dependencies has also been provided.


## Usage

The cluster validation pipeline compares/matches an input optical catalog to a well-centered x-ray cluster catalog and the SPT 2500d SZ cluster catalog then performs the following:

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


