[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

# Cohen's d

Exercise 4   *Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s* d *to quantify the difference between the groups. How does it compare to the difference in pregnancy length?*

In order to compute Cohen's D, I had to get means of the two data sets. Two Groups "Firsts" and "Others". Found their Means and SD in order to compute Cohen's D. The difference came out to be very small.

Output: .028 

Note: Cohen's distance varies from 0-2. Differnece above is very small. 

```python
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    avg_std_div=((group1.std()+group2.std())/2)
    d = diff / avg_std_div
    print(d)

CohenEffectSize(firsts.prglngth,others.prglngth)
```




