Replication code for the paper "Mining Brand Perceptions from Twitter Social Networks," by Aron Culotta and Jennifer Cutler, published in *Marketing Science*.

## Contents

- **[MKSCI-Replication.ipynb](https://github.com/tapilab/mksci-2015-brand-perceptions/blob/master/Mksci-Replication.ipynb):** IPython notebook to replicate figures and tables from the paper. 

You can either clone this repository and run the iPython notebook file locally, or run it remotely using [Binder](http://mybinder.org/) by clicking the link below.

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/tapilab/mksci-2015-brand-perceptions)

## Data

All requisite data is downloadable here (333M):

<https://www.dropbox.com/s/rvzn98l3a3278v9/mksci-data.tgz?dl=1>

- **brands.txt**: A list of Twitter accounts for each of the 168 brands considered (after removing those without sufficient survey responses).
- **brands_followers.txt**: The follower ids for each brand, up to 500K. All follower files have one account per line. The first value is the time stamp for when the followers were collected, the second value is the screen_name of the account, the remaining values are the Twitter IDs of each follower.
- **brand_followers_unfiltered.txt**: The follower ids for each brand from the original 231 brands prior to filtering.

Subfolders contain information for each perceptual attribute:

- **eco**: Environmental friendliness attribute.
- **luxury**: Luxury attribute.
- **nutrition**: Nutrition attribute.
- **eco-nonprofit:** Same as **eco**, but uses manually collected exemplars from Charity Navigator (for Table 3).

Each of these subfolders contains the following:

- **default/**: A subfolder with the predicted ratings according to each of the 12 algorithm variants described in the paper (c.f. Table 4).
- **diagnose/**: A subfolder with the correlation between survey and prediction using a single exemplar at a time (for Figure 9).
- **exemplars.txt**: The exemplar Twitter accounts for this perceptual attribute.
- **exemplar_followers.txt**: The followers of each exemplar.
- **nexemplars/**: Results of correlation versus number of exemplars (Figure 7a)
- **survey/**: A subfolder with the average survey ratings for this perceptrual attribute, separated by brand category (e.g., Cars, Apparel, ...)

