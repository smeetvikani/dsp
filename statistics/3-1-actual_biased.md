[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

Q2 - 3-1-actual_biased.md

*Exercise 1  Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample.

Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household.

Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.

Plot the actual and biased distributions, and compute their means. As a starting place, you can use chap03ex.ipynb.*

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

    [logo]: https://raw.githubusercontent.com/smeetvikani/dsp/master/statistics/Figure_1.png "Logo Title Text 2"
Q2 - 3-1-actual_biased.md

*Exercise 1  Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample.

Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household.

Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.

Plot the actual and biased distributions, and compute their means. As a starting place, you can use chap03ex.ipynb.*

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

    [logo]: https://raw.githubusercontent.com/smeetvikani/dsp/master/statistics/Figure_1.png	"Logo Title Text 2"

    ![image text](https://cloud.githubusercontent.com/assets/711743/25648417/57cd2c0c-2fe9-11e7-8753-b60ea2656faf.png)

