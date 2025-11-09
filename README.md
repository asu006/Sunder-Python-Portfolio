# Adithya Sunder – Python Portfolio

This is my portfolio of Python code created during **BISC 450C (Python for Bioinformatics)**. 
Each section below represents the projects and topics we covered throughout the quarter.

---

## Jupyter notebooks 1 & 2
Learned to write, save, and run Python code using JupyterLab.

```python
%matplotlib inline
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
sns. set(style = "darkgrid")
```


```python
df = pd.read_csv('/home/student/Desktop/classroom/myfiles/notebooks/fortune500.csv')
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>25495</td>
      <td>2005</td>
      <td>496</td>
      <td>Wm. Wrigley Jr.</td>
      <td>3648.6</td>
      <td>493</td>
    </tr>
    <tr>
      <td>25496</td>
      <td>2005</td>
      <td>497</td>
      <td>Peabody Energy</td>
      <td>3631.6</td>
      <td>175.4</td>
    </tr>
    <tr>
      <td>25497</td>
      <td>2005</td>
      <td>498</td>
      <td>Wendy's International</td>
      <td>3630.4</td>
      <td>57.8</td>
    </tr>
    <tr>
      <td>25498</td>
      <td>2005</td>
      <td>499</td>
      <td>Kindred Healthcare</td>
      <td>3616.6</td>
      <td>70.6</td>
    </tr>
    <tr>
      <td>25499</td>
      <td>2005</td>
      <td>500</td>
      <td>Cincinnati Financial</td>
      <td>3614.0</td>
      <td>584</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns = ['year', 'rank', 'company', 'revenue', 'profit'] 
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
len(df)
```




    25500




```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit      object
    dtype: object




```python
non_numeric_profits = df.profit.str.contains('[^0-9.-]')
df. loc[non_numeric_profits].head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>228</td>
      <td>1955</td>
      <td>229</td>
      <td>Norton</td>
      <td>135.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>290</td>
      <td>1955</td>
      <td>291</td>
      <td>Schlitz Brewing</td>
      <td>100.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>294</td>
      <td>1955</td>
      <td>295</td>
      <td>Pacific Vegetable Oil</td>
      <td>97.9</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>296</td>
      <td>1955</td>
      <td>297</td>
      <td>Liebmann Breweries</td>
      <td>96.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>352</td>
      <td>1955</td>
      <td>353</td>
      <td>Minneapolis-Moline</td>
      <td>77.4</td>
      <td>N.A.</td>
    </tr>
  </tbody>
</table>
</div>




```python
set(df.profit[non_numeric_profits])
```




    {'N.A.'}




```python
len(df. profit[non_numeric_profits])
```




    369




```python
bin_sizes, _, _ = plt.hist(df.year[non_numeric_profits], bins= range(1955, 2006) )
```


![png](output_11_0.png)



```python
df = df. loc[-non_numeric_profits]
df. profit = df.profit.apply(pd.to_numeric)
```


```python
len(df)
```




    25131




```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit     float64
    dtype: object




```python
group_by_year = df. loc[:, ['year','revenue','profit']].groupby('year')
avgs = group_by_year.mean()
x = avgs. index
y1 = avgs.profit
def plot(x, y, ax, title, y_label):
    ax.set_title(title)
    ax.set_ylabel(y_label)
    ax.plot(x, y)
    ax.margins (x = 0, y = 0)
```


```python
fig, ax = plt.subplots()
plot(x, y1 , ax, 'Increase in mean Fortune 500 company profits from 1955 to 2005', 'Profit (millions)')
```


![png](output_16_0.png)



```python
y2 = avgs.revenue
fig, ax = plt. subplots()
plot(x, y2, ax, 'Increase in mean Fortune 500 company revenues from 1955 to 2005', 'Revenue (millions)')
```


![png](output_17_0.png)



```python
def plot_with_std(x, y, stds, ax, title, y_label):
    ax.fill_between(x, y - stds, y + stds, alpha = 0.2)
    plot(x, y, ax, title, y_label)
fig, (ax1, ax2) = plt.subplots(ncols= 2)
title = 'Increase in mean and std fortune 500 company %s from 1955 to 2005'
stds1 = group_by_year.std().profit.values
stds2 = group_by_year.std().revenue.values
plot_with_std(x, y1.values, stds1, ax1, title % 'profits', 'Profit (millions)' )
plot_with_std(x, y2.values, stds2, ax2, title % 'revenues', 'Revenue (millions)')
fig.set_size_inches (14,4)
fig.tight_layout()
```


![png](output_18_0.png)



```python

```

## Python Fundamentals
Practiced basic syntax, data types, and variable operations.
```python
# Any python interpreter can be used as a calculator
3 + 5 * 4
```




    23




```python
# Let's save a value to a variable
weight_kg = 60
print(weight_kg)
```

    60



```python
# Weight0 = valud
# weight = invalid
# weight and Weight are different
```


```python
# Types of data
# There are three common types of data:
# 1. Integer numbers
# 2. Floating point numbers
# 3. Strings
```


```python
# Floating point number
weight_kg = 60.3
```


```python
# String comprised of letters
patient_name = "Jon Smith"
```


```python
# String comprised of numbers
patient_id = '001'
```


```python
# Use variables in Python
weight_lb = 2.2 * weight_kg
print(weight_lb)
```

    132.66



```python
# Let's add a prefix to our patient id
patient_id = 'inflam_' + patient_id
print(patient_id)
```

    inflam_001



```python
# Combine print statements
print(patient_id, 'weight in kilograms:', weight_kg)
```

    inflam_001 weight in kilograms: 60.3



```python
# We can call a function inside another function
print(type(60.3))
print(type(patient_id))
```

    <class 'float'>
    <class 'str'>



```python
# We can also do calculations inside the print function
print('weight in lbs:', 2.2 * weight_kg)
```

    weight in lbs: 132.66



```python
print(weight_kg)
```

    60.3



```python
weight_kg = 65.0
print('weight in kilograms is now:', weight_kg)
```

    weight in kilograms is now: 65.0



```python

```

## Analyzing Patient Data
In this analysis, we looked at inflammation data for multiple patients.

```python
import numpy
```


```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

print(data)
```

    [[0. 0. 1. 3. 1. 2. 4. 0. 1. 2.]
     [0. 1. 2. 4. 2. 3. 5. 1. 2. 2.]
     [1. 1. 3. 2. 1. 2. 3. 2. 3. 1.]
     [2. 1. 2. 3. 3. 3. 4. 2. 2. 3.]
     [3. 2. 4. 3. 2. 4. 5. 3. 4. 2.]]



```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')
```


```python
print(data)
```

    [[0. 0. 1. 3. 1. 2. 4. 0. 1. 2.]
     [0. 1. 2. 4. 2. 3. 5. 1. 2. 2.]
     [1. 1. 3. 2. 1. 2. 3. 2. 3. 1.]
     [2. 1. 2. 3. 3. 3. 4. 2. 2. 3.]
     [3. 2. 4. 3. 2. 4. 5. 3. 4. 2.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (5, 10)



```python
print('first value in data:', data[0, 0])
```

    first value in data: 0.0



```python
print('middle value in data:', data[2, 5])
```

    middle value in data: 2.0



```python
print(data[0:4, 0:10])  
```

    [[0. 0. 1. 3. 1. 2. 4. 0. 1. 2.]
     [0. 1. 2. 4. 2. 3. 5. 1. 2. 2.]
     [1. 1. 3. 2. 1. 2. 3. 2. 3. 1.]
     [2. 1. 2. 3. 3. 3. 4. 2. 2. 3.]]



```python
print(data[1:4, 2:7])
```

    [[2. 4. 2. 3. 5.]
     [3. 2. 1. 2. 3.]
     [2. 3. 3. 3. 4.]]



```python
small = data[:3, 6:]
```


```python
print('small is:')
```

    small is:



```python
print(small)
```

    [[4. 0. 1. 2.]
     [5. 1. 2. 2.]
     [3. 2. 3. 1.]]



```python
print(numpy.mean(data))
```

    2.24



```python
maxval = numpy.amax(data)
minval = numpy.amin(data)
stdval = numpy.std(data)
```


```python
print(maxval)
print(minval)
print(stdval)

```

    5.0
    0.0
    1.2419339757008019



```python
print('maximum inflammation:', maxval)
print('minimum inflammation:', minval)
print('standard deviation:', stdval)
```

    maximum inflammation: 5.0
    minimum inflammation: 0.0
    standard deviation: 1.2419339757008019



```python
# Sometimes we want to look at variation in statistical values
# such as maximum inflammation per patient
patient_0 = data[0, :]
print('maximum inflammation for patient 0:', numpy.amax(patient_0))

```

    maximum inflammation for patient 0: 4.0



```python
print('maximum inflammation for patient 2:', numpy.amax(data[2, :]))
```

    maximum inflammation for patient 2: 3.0



```python
print(numpy.mean(data, axis=0))
```

    [1.2 1.  2.4 3.  1.8 2.8 4.2 1.6 2.4 2. ]



```python
print(numpy.mean(data, axis=0).shape)
```

    (10,)



```python
print(numpy.mean(data, axis=1))
```

    [1.4 2.2 1.9 2.5 3.2]



```python

```
##  Storing Values in Lists
Created lists and practiced indexing, slicing, and appending items.

##  Using Loops
Worked with for-loops and while-loops to repeat operations efficiently.

##  Using Multiple Files
Imported and combined multiple `.csv` data files in Python.

##  Making Choices
Used if/else statements for conditional logic and decision making.

##  Functions (1, 2, 3, and 4)
Defined and called functions to make code reusable and organized.

##  Defensive Programming
Handled errors safely with try/except blocks.

##  Transcribing DNA into RNA
Converted DNA sequences into RNA using `.replace("T", "U")`.

##  Translating RNA into Protein
Translated RNA codons into amino acids using a codon dictionary.

---

##  Conclusion
This portfolio demonstrates what I learned in **BISC 450C**, combining coding skills with biological data applications.

---

**Instructor:** Dr. Joshua Vandenbrink 
**Quarter:** Fall 2025
