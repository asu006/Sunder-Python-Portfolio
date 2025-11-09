# Sunder-Python-Portfolio
This is the portfolio of python code that I learned during Bisc450C


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
