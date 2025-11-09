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
##   Storing Lists
Created lists and practiced indexing, slicing, and appending items.
```python
odds = [1, 3, 5, 7]
print('odds are:', odds )
```

    odds are: [1, 3, 5, 7]



```python
print('first element:', odds[0])
print('last element:', odds [3])
print('"-1" element:', odds [-1])

```

    first element: 1
    last element: 7
    "-1" element: 7



```python
names = ['Curie', 'Darwing', 'Turing'] # Typo in Darwin's name 
print ('names is orginally:', names)
names [1] = 'Darwin' # Correct the name
print ('final value of names:', names)
```

    names is orginally: ['Curie', 'Darwing', 'Turing']
    final value of names: ['Curie', 'Darwin', 'Turing']



```python
#names='Darwin'
#name[0] = 'd'
```


```python
odds.append (11)
print ('odds after adding a value', odds)
```

    odds after adding a value [1, 3, 5, 7, 11]



```python
removed_element= odds.pop(0)
print ('odds after removing the first element:', odds)
print('removed_element:', removed_element)
```

    odds after removing the first element: [3, 5, 7, 11]
    removed_element: 1



```python
odds.reverse()
print('odds after reversing', odds)
```

    odds after reversing [11, 7, 5, 3]



```python
odds = [3,5,7]
primes = odds
primes.append (2)
print('primes:',primes)
print('odds:',odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds = [3,5,7]
primes = list(odds)
primes.append(2)
print('primes:',primes)
print('odds:',odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name ="Drosophila melanogaster"
group = binomial_name[0:10]
print('group:', group)

species = binomial_name[11:23]
print ('species:', species)


chromosomes =['X', 'Y','2','3','4']
autosomes= chromosomes [2:5]
print('autosomes:', autosomes)
last = chromosomes[-1]
print ('last:', last)
```

    group: Drosophila
    species: melanogaster
    autosomes: ['2', '3', '4']
    last: 4



```python
date = 'Monday 4 January 2023'
day = date[0:6]
print('using 0 to begin range:', day)
day = date [:6]
print('Omitting beginning index:', day)
```

    using 0 to begin range: Monday
    Omitting beginning index: Monday



```python
months = ['jan','feb','mar','april','may','jun','jul','aug','sep','oct','nov','dec']
sond = months [8:12]
print('With known last position:', sond)

sond = months[8:len(months)]
print('Using len()to get last entry:', sond)

sond = months [8:]
print('Omitting ending index:', sond)
```

    With known last position: ['sep', 'oct', 'nov', 'dec']
    Using len()to get last entry: ['sep', 'oct', 'nov', 'dec']
    Omitting ending index: ['sep', 'oct', 'nov', 'dec']



```python

```

##  Using Loops
Worked with for-loops and while-loops to repeat operations efficiently.
```python
odds = [1,3,5,7]
```


```python
print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5
    7



```python
odds = [1,3,5]
print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-01ba67d8a9e5> in <module>
          3 print(odds[1])
          4 print(odds[2])
    ----> 5 print(odds[3])
    

    IndexError: list index out of range



```python
odds =[1, 3, 5, 7,9,11,13,15,17,19]

for num in odds:
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19



```python
length = 0
names = ['Curie','Darwin', 'Turing']
for value in names:
    length = length + 1
print('There are', length, 'names in the list.')
```

    There are 3 names in the list.



```python
name = "Rosalind"
for name in ['Curie','Darwin','Turing']:
    print(name)
print('after the loop, name is',name) 
```

    Curie
    Darwin
    Turing
    after the loop, name is Turing



```python
print(len([0,2,2,3]))
```

    4



```python
name = ['Curie','Darwin','Turing']

print(len(name))
```

    3


## Using Multiple Files
Imported and combined multiple `.csv` data files in Python.

```python

```ly.



```python
import glob
```


```python
print(glob.glob('inflammation* .csv'))
```

    []



```python
import glob
import numpy
import matplotlib.pyplot

filenames = sorted(glob.glob('inflammation*.csv'))
filenames = filenames[0:3]

for filenames in filenames: 
    print(filename)
    
    data = numpy.loadtxt(fname=filename, delimiter=', ')
    
    fig=matplotlib.pyplot.figure(figsize = (10.0, 3.0))
    
    axes1= fig.add_subplot(1,3,1)
    axes2= fig.add_subplot(1,3,2)
    axes3= fog.add_subplot(1,3,3)
    
    axes1.set_ylabel ('average')
    axes1.plot(numpy,mean(data, axis=0))
    
    axes2.set_ylabel('min')
    axes2.plot(numpy.amax(data,axis=0))
    
    axes3.set_ylabel('min')
    axes3.plot(numpy.amin(data,axis=0))
    
    fig.tight_layout()
    matplotlib.pyplot.show()
    
```


```python

```

##  Making Choices
Making Choices

```python
num = 37
if num > 100:
    print ('greater')
else:
    print( 'not greater')
print( 'done')
```

    not greater
    done



```python
num = 53
print('before conditional...')
if num > 100:
    print(num, 'is greater than 100')
print('...after conditional')
```

    before conditional...
    ...after conditional



```python
num = 14

if num > 0:
    print(num, 'is positive')
elif num == 0:
    print(num, 'is zero')
else:
    print(num, 'is negative')
```

    14 is positive



```python
if (1 > 0) and (-1 >= 0):
    print('both parts are true')
else:
    print('at least one part if false')
```

    at least one part if false



```python
if (1 > 0) or (-1 >= 0):
    print('at least one part is true')
else:
    print('both of these are false')
```

    at least one part is true



```python

```
##  Functions (1, 2, 3, and 4)
Defined and called functions to make code reusable and organized.


Functions Pt 1

```python
fahrenheit_val = 99
celsius_val = ((fahrenheit_val - 32) * (5/9))
print(celsius_val)
```

    37.22222222222222



```python
fahrenheit_val2 = 43
celsius_val2 = ((fahrenheit_val2 - 32) * (5/9))
print(celsius_val2)
```

    6.111111111111112



```python
def explicit_fahr_to_celsius(temp):
    # Assign the converted value to a variable
    converted = ((temp - 32) * (5/9))
    # Return the values of the new variable
    return converted
```


```python
def fahr_to_celsius(temp):
    # Return converted values more efficiently
    # using the return function without creating a new variable
    return ((temp - 32) * (5/9))
```


```python
fahr_to_celsius(32)
```




    0.0




```python
explicit_fahr_to_celsius(32)
```




    0.0




```python
print('Freezing point of water:', fahr_to_celsius(32), 'C')
print('Boiling point of water:', fahr_to_celsius(212), 'C')
```

    Freezing point of water: 0.0 C
    Boiling point of water: 100.0 C



```python
def celsius_to_kelvin(temp_c):
    return temp_c + 273.15

print('Freezing point of water in Kelvin:', celsius_to_kelvin(0.))
```

    Freezing point of water in Kelvin: 273.15



```python
def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

print('Boiling point of water in Kelvin:', fahr_to_kelvin(212.0))
```

    Boiling point of water in Kelvin: 373.15



```python
temp_kelvin = fahr_to_kelvin(212.0)
print('Temperature in Kelvin was:', temp_kelvin)
```

    Temperature in Kelvin was: 373.15



```python
temp_kelvin
```




    373.15




```python
def print_temperatures():
    print('Temperature in Fahrenheit was:', temp_fahr)
    print('Temperature in Kelvin was:', temp_kelvin)

temp_fahr = 212.0
temp_kelvin = fahr_to_kelvin(temp_fahr)

print_temperatures()

```

    Temperature in Fahrenheit was: 212.0
    Temperature in Kelvin was: 373.15



```python

```
```python
import numpy
import matplotlib
import matplotlib.pyplot
import glob
```


```python
def visualize(filename):
    data = numpy.loadtxt(fname=filename, delimiter=',')

    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean(data, axis=0))

    axes2.set_ylabel('max')
    axes2.plot(numpy.amax(data, axis=0))

    axes3.set_ylabel('min')
    axes3.plot(numpy.amin(data, axis=0))

    fig.tight_layout()
    matplotlib.pyplot.show()
```


```python
def detect_problems(filename):
    data = numpy.loadtxt(fname=filename, delimiter=',')

    if numpy.amax(data, axis=0)[0] == 0 and numpy.amax(data, axis=0)[20] == 20:
        print('Suspicious looking maxima!')
    elif numpy.sum(numpy.amin(data, axis=0)) == 0:
        print('Minima add up to zero!')
    else:
        print('Seems ok!')
```


```python
filenames = sorted(glob.glob('inflammation*.csv'))

for filename in filenames[:3]:
    print(filename)
    visualize(filename)
    detect_problems(filename)
```

    inflammation-01.csv



![png](output_3_1.png)


    Seems ok!



```python
def offset_mean(data, target_mean_value):
    return (data - numpy.mean(data)) + target_mean_value
```


```python
z = numpy.zeros((2, 2))
print(offset_mean(z, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')
print(offset_mean(data, 0))
```

    [[-2.24 -2.24 -1.24  0.76 -1.24 -0.24  1.76 -2.24 -1.24 -0.24]
     [-2.24 -1.24 -0.24  1.76 -0.24  0.76  2.76 -1.24 -0.24 -0.24]
     [-1.24 -1.24  0.76 -0.24 -1.24 -0.24  0.76 -0.24  0.76 -1.24]
     [-0.24 -1.24 -0.24  0.76  0.76  0.76  1.76 -0.24 -0.24  0.76]
     [ 0.76 -0.24  1.76  0.76 -0.24  1.76  2.76  0.76  1.76 -0.24]]



```python
print('original min, mean and max are:', numpy.amin(data), numpy.mean(data), numpy.amax(data))
offset_data = offset_mean(data, 0)
print('min, mean, and max of offset data are:',
      numpy.amin(offset_data),
      numpy.mean(offset_data),
      numpy.amax(offset_data))
```

    original min, mean and max are: 0.0 2.24 5.0
    min, mean, and max of offset data are: -2.24 -2.1316282072803005e-16 2.76



```python
print('std dev before and after:', numpy.std(data), numpy.std(offset_data))
```

    std dev before and after: 1.2419339757008019 1.2419339757008019



```python
print('difference in standard deviation before and after:',
      numpy.std(data) - numpy.std(offset_data))
```

    difference in standard deviation before and after: 0.0



```python
def offset_mean(data, target_mean_value):
   return (data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
    



```python
def offset_mean(data, target_mean_value):
    """Return a new array containing the original data with its mean offset to match the desired value.

    Examples
    --------
    >>> offset_mean([1, 2, 3], 0)
    array([-1.,  0.,  1.])
    """
    return (data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original data with its mean offset to match the desired value.
        
        Examples
        --------
        >>> offset_mean([1, 2, 3], 0)
        array([-1.,  0.,  1.])
    



```python

```
##  Defensive Programming
Handled errors safely with try/except blocks.

```python
numbers = [1.5, 2.3, 0.7, -0.001, 4.4]
total = 0.0

for num in numbers:
    assert num > 0.0, 'Data should only contain positive values'
    total += num

print('total is:', total)
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-1-dbdebae53991> in <module>
          3 
          4 for num in numbers:
    ----> 5     assert num > 0.0, 'Data should only contain positive values'
          6     total += num
          7 


    AssertionError: Data should only contain positive values



```python
def normalize_rectangle(rect):
    """Normalizes a rectangle so that it is at the origin and 1.0 units long on its longest axis.
    Input should be of the format (x0, y0, x1, y1).
    (x0, y0) and (x1, y1) define the lower left and upper right corners of the rectangle respectively.
    """
    assert len(rect) == 4, 'Rectangles must contain 4 coordinates'
    x0, y0, x1, y1 = rect
    assert x0 < x1, 'Invalid X coordinates'
    assert y0 < y1, 'Invalid Y coordinates'

    dx = x1 - x0
    dy = y1 - y0

    if dx > dy:
        scaled = dx / dy
        upper_x, upper_y = 1.0, scaled
    else:
        scaled = dx / dy
        upper_x, upper_y = scaled, 1.0

    assert 0 < upper_x <= 1.0, 'Calculated upper x coordinate invalid'
    assert 0 < upper_y <= 1.0, 'Calculated upper y coordinate invalid'

    return (0, 0, upper_x, upper_y)
```


```python
print(normalize_rectangle((0.0, 1.0, 2.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-3-a81b6ed7619a> in <module>
    ----> 1 print(normalize_rectangle((0.0, 1.0, 2.0)))
    

    <ipython-input-2-9025216ebfe6> in normalize_rectangle(rect)
          4     (x0, y0) and (x1, y1) define the lower left and upper right corners of the rectangle respectively.
          5     """
    ----> 6     assert len(rect) == 4, 'Rectangles must contain 4 coordinates'
          7     x0, y0, x1, y1 = rect
          8     assert x0 < x1, 'Invalid X coordinates'


    AssertionError: Rectangles must contain 4 coordinates



```python
print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-4-5e28a32bada1> in <module>
    ----> 1 print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
    

    <ipython-input-2-9025216ebfe6> in normalize_rectangle(rect)
          6     assert len(rect) == 4, 'Rectangles must contain 4 coordinates'
          7     x0, y0, x1, y1 = rect
    ----> 8     assert x0 < x1, 'Invalid X coordinates'
          9     assert y0 < y1, 'Invalid Y coordinates'
         10 


    AssertionError: Invalid X coordinates



```python
print(normalize_rectangle((0.0, 0.0, 1.0, 5.0)))
```

    (0, 0, 0.2, 1.0)



```python
print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-6-1337bef8f4bf> in <module>
    ----> 1 print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
    

    <ipython-input-2-9025216ebfe6> in normalize_rectangle(rect)
         20 
         21     assert 0 < upper_x <= 1.0, 'Calculated upper x coordinate invalid'
    ---> 22     assert 0 < upper_y <= 1.0, 'Calculated upper y coordinate invalid'
         23 
         24     return (0, 0, upper_x, upper_y)


    AssertionError: Calculated upper y coordinate invalid



```python

```

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
