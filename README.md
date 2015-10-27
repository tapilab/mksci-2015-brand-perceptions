Replication code for the paper "Mining Brand Perceptions from Twitter Social Networks," by Aron Culotta and Jennifer Cutler, published in *Marketing Science*. (The latest version of this documentation is at <https://github.com/tapilab/mksci-2015-brand-perceptions/>). 

In this paper, we estimate how consumers rate brands along three *perceptual attributes*: eco-friendliness, luxury, and nutrition. To do so, we analyze each brand's Twitter follower network, and compare it to the followers of an automatically identified set of exemplar accounts (e.g., `@Greenpeace` is one of the exemplar accounts for the eco-friendliness attribute). We compare our estimates to primary survey data of consumer perceptions, finding strong correlations across all three attributes.

We have made available all of our primary data (Twitter network and survey results), as well as Python code to replicate our results.

## Data

All requisite data is downloadable here (333M):

<https://www.dropbox.com/s/rvzn98l3a3278v9/mksci-data.tgz?dl=1>

(Note that if you run the Python code, this data will automatically be downloaded and unzipped for you.)

The contents of this archive are as follows: 
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
- **survey/**: A subfolder with the average survey ratings for this perceptual attribute, separated by brand category (e.g., Cars, Apparel, ...)


## Code

All analysis is done in Python3, using a single iPython notebook:
**[MKSCI-Replication.ipynb](Mksci-Replication.ipynb)** 

The IPython notebook replicates the figures and tables from the paper. To learn more about iPython Notebooks, see the documentation here: <http://ipython.org/notebook.html>. Notebooks are increasingly being used for replicability, as the notebook integrates Python code, its output, and documentation in one file (for an overview, see http://www.nature.com/news/interactive-notebooks-sharing-the-code-1.16261). 

It can take some effort to get iPython installed locally. If this is an issue, a static version of the notebook can be viewed here:
[Mksci-Replication.html](Mksci-Replication.html)

Additionally, we have integrated our code with Binder (http://mybinder.org/), which is a pretty amazing tool that provides a web interface to run iPython notebooks on a remote server. This allows one to reproduce our analysis without installing or configuring anything. This is now available here:
<http://mybinder.org/repo/tapilab/mksci-2015-brand-perceptions>


[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/tapilab/mksci-2015-brand-perceptions)

If you wish to run the code locally, there are a few external Python libraries you will need to install. First, be sure you've installed [pip](https://pypi.python.org/pypi/pip/), which is the Python package manager. Then, from the command-line, you can run:

`pip install -r requirements.txt`

This will install all required libraries. 

Finally, you can launch the notebook with:

`ipython notebook Mksci-Replication.ipynb`

