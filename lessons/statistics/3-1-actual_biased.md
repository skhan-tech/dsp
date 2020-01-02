[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

Using the NSFG data i was able to create the distribution for the number of children under 18 in the household:

```python
num_kd = resp.numkdhh
num_kd_hist = thinkstats2.Hist(num_kd, label='number_kids')
thinkplot.Hist(num_kd_hist)
thinkplot.Config(xlabel='num_kids', ylabel='count')
```

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Distribution")
