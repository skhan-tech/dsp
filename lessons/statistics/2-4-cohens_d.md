[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

# Investigation of NSFG Cycle 6 Data
By: Saleem Khan

# Table of Contents

[1. Are first babies heavier or lighter than subsequent babies?](#section-a)  
[2. Computation of Cohen's *d* to quantify differences between groups](#section-b)  
[3. How does the Cohen's *d* for weight comare to pregnancy length?](#section-c) 

## <a name="section-a"></a>1.  Are first babies heavier or lighter than subsequent babies?
In order to test this idea we will need to calculate the mean weight for first babies and for all subsequent babies. We will then compare the two mean weights. The code for testing this is below: 

```python
firsts_wgt = firsts.totalwgt_lb.mean()
others_wgt = others.totalwgt_lb.mean()

print("First Child Weight Mean: ", firsts_wgt)
print("Subsequent Child Weight Mean: ", others_wgt)

if(firsts_wgt < others_wgt):
    print("First children are lighter than subsequent.")
else:
    print("First children are heavier than subsequent.")
```
The output from running this against the NFSG data is:

```
First Child Weight Mean:  7.201094430437772
Subsequent Child Weight Mean:  7.325855614973262
First children are lighter than subsequent.
```

## <a name="section-b"></a>2.  Computation of Cohen's *d* to quantify differences between groups

Cohen's *d* allows us to understand the difference in standard deviations between two groups. The code for calculating this is below:

```python
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1*var1 + n2*var2) / (n1+n2)
    d = diff / math.sqrt(pooled_var)
    return d
```

The ouptut of running mean of the first child's weight against all others is: 
```python
print(CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb))
```
```
  -0.088672927072602
```
This outcome tells us that there is a minimal effect size when it comes to birth weight.

## <a name="section-c"></a>3.  How does the Cohen's *d* for weight comare to pregnancy length?
```python
  print(CohenEffectSize(firsts.prglngth, others.prglngth))
```
```
0.028879044654449883
```
This outcome tells us that there is a minimal effect size when it comes to pregnancy length
