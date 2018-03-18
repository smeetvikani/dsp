[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> # **5-1-blue_men.md**

*Exercise 1   In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women.
In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.*

In order to do that, we need to calculate the male population between 5'10 and 6'1. As a result 35% of the population can join the Blue Man Group. 

```python

import scipy.stats
import thinkplot
import thinkstats2

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)

low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"
print(high,low)
percentage=high-low
print(percentage)
#output: .345 / 35% are between 5'10 and 6'1


```
