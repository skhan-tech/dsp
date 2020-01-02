[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

In order to determine the percentage of men in the US that meet the Blue Man Group criteria we will first need to filter the dataset by men and generate the PMF:

```python
df = brfss.ReadBrfss()
male = df[df.sex==1]
pmf_male = thinkstats2.Pmf(male.htm3)
```

To get a quick glimpse of the height distributions we can plot it like this:
```python
thinkplot.Pmf(pmf_male)
thinkplot.Show(xlabel='height', ylabel='value')
print("Mean: ", pmf_male.Mean())
print("Std: ", pmf_male.Std())
```

Then we need to filter out the men that are between 5'10" and 6'1":
```python
blue_man_criteria = []
for index, row in male.iterrows():
    if ((row['htm3']>(70*2.54)) and (row['htm3']<(73*2.54))):
        blue_man_criteria.append(x)
  
```

Then we can do some simple math and arrive at our answer which is 4.7%:
```python
percent = len(blue_man_criteria)/len(male)
print(len(blue_man_criteria))
print(len(male))
print(percent)
```



