# Q2 - **3-1-actual_biased.md** 

*Exercise 1  Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample.*
*Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household.*
*Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.*

Answer: Both Biased and Non Biased are added to the same plot. 

```python
import nsfg
import thinkplot
import thinkstats2

def BiasPmf(pmf, label=''):
    """Returns the Pmf with oversampling proportional to value.
    If pmf is the distribution of true values, the result is the
    distribution that would be seen if values are oversampled in
    proportion to their values; for example, if you ask students
    how big their classes are, large classes are oversampled in
    proportion to their size.
    Args:
      pmf: Pmf object.
      label: string label for the new Pmf.
     Returns:
       Pmf object
    """
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
    new_pmf.Normalize()
    return new_pmf

resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp.numkdhh, label='biased')
unbiased=BiasPmf(pmf,label="unbiased")

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, unbiased])
thinkplot.Config(xlabel='Class size', ylabel='PMF')
thinkplot.show()
```

![alt text](https://raw.githubusercontent.com/smeetvikani/dsp/master/statistics/Figure_1.png)

