New Sites Model
================
Waleed Idrees (Data Scientist) ,Ben Neffendorf (Head of Insight)
2023-02-19

# link to the code:

<https://github.com/WaleedIdrees/DataStory/blob/main/dis_reg.Rmd>

# Introduction to Model

This model is build to understand the relationship between distance
traveled and number of tests figure out where to install new RHC sites.
Model takes the data from existing customers from out data base for all
RHC sites. to start building a predictive model we need a target
variable that we are trying to predict. We want to find out what
location will yield good sales. So we use total sales as a target
variable which will tell us if a certain location will yield good sales.

We use the data only for only RHC sites for this analysis as airport
sites have different attributes compared to RHC sites. Target measure is
total no of tests used as a measure of total sales. Its created by
grouping data by Site postcode, customer postcode sector and month. So
we get number of tests on each site from different postcode sector every
month.

# Data Collection

Explanatory variables is distance traveled in minutes and its pulled
from f_master_tests_data. We then connect this data with the distance
traveled table to get average distance traveled to site in mins. This
information can be useful to help us figure out how much customers are
willing to travel and how far two sites should be to avoid
cannibalization.

Total population variable is taken from Office of national statistics
website. Population data is collected from 2011 census from office of
national statistics website. Its not been updated since past 10 years
but that’s the only info we can collect at the moment for free.

# Descriptive Statistics

Final data used in this model has 24147 conversations. Average test from
each sector is 8, with a max of 463 tests. Average time travelled to
site is 69 mins and the max time traveled is 933 mins.

|             | vars |     n |      mean |       sd |   median |   min |      max |    range |
|:------------|-----:|------:|----------:|---------:|---------:|------:|---------:|---------:|
| No_of_tests |    2 | 14194 |  9.608496 | 21.23177 |  3.00000 | 1.000 | 462.0000 | 461.0000 |
| Avg_time    |    3 | 14194 | 68.974240 | 77.32510 | 41.79583 | 1.325 | 933.4167 | 932.0917 |

Descriptive Statistics of no of tests and explanatory variables

## Model

Graphs below shows a people getting tested within different time
buckets. the relationship between the average time and no of tests is
given in each bucket using a regression equation.

our constant for people who live within 0-10 mins distance explains that
1% of people who live from 0-10 mins distance get the test regardless of
the avg time travel. However, as the time increases by 1 min we may
loose there 0.04 test.

The constant decreases as the average time traveled increases from 1.04
in 0-10 zone to .014 in 69-137 zone. Also the coefficient of effect gets
smaller as we move from a smaller time zone to larger time zone.

![](dis_reg_files/figure-gfm/unnamed-chunk-15-1.png)<!-- -->
