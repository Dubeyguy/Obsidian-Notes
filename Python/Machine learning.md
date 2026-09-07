#python #machine-learning

In Machine Learning (and in mathematics) there are often three values that interests us:

- **Mean** - The average value
- **Median** - The mid point value
- **Mode** - The most common value

## Mean

```python

import numpy

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = numpy.mean(speed)

print(x)
```

## Median

```python
import numpy

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = numpy.median(speed)

print(x)
```

## Mode

```python
from scipy import stats

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = stats.mode(speed)

print(x)

```

# Standard Deviation

- Standard deviation is a number that describes how spread out the values are.
- A low standard deviation means that most of the numbers are close to the mean (average) value.
- A high standard deviation means that the values are spread out over a wider range.

```python
import numpy

speed = [86,87,88,86,87,85,86]

x = numpy.std(speed)

print(x)
```

# Variance

- Variance is another number that indicates how spread out the values are.
- In fact, if you take the square root of the variance, you get the standard deviation!
- Or the other way around, if you multiply the standard deviation by itself, you get the variance!

```python
import numpy

speed = [32,111,138,28,59,77,97]

x = numpy.var(speed)

print(x)
```

# Percentiles

- Percentiles are used in statistics to give you a number that describes the value that a given percent of the values are lower than.

```python
import numpy

ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]

x = numpy.percentile(ages, 75)

print(x)
```

# Data Distribution

- To create big data sets for testing, we use the Python module NumPy, which comes with a number of methods to create random data sets, of any size.

```python
import numpy

x = numpy.random.uniform(0.0, 5.0, 250)

print(x)
```

# Normal Data Distribution

-  values are concentrated around a given value.

```python
import numpy
import matplotlib.pyplot as plt

x = numpy.random.normal(5.0, 1.0, 100000)

plt.hist(x, 100)
plt.show()
```

# Scatter Plot

A scatter plot is a diagram where each value in the data set is represented by a dot.

![](Media/Pasted%20image%2020251016234239.png)

```python
import matplotlib.pyplot as plt

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

plt.scatter(x, y)
plt.show()

```

# Regression

The term regression is used when you try to find relationship between variables. in machine learning and in statistical modeling, that relationship is used to predict the outcome of future events

## Linear Regression

Linear regression uses the relationship between data points to draw a straight line through all of them. This line can be used to predict future values

![](Media/Pasted%20image%2020251017000409.png)

```python
import matplotlib.pyplot as plt
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()
```

## Relationship

Relationship brings value to linear regression, linear regression is only useful when the variables have a relationship. ( 0 is bad, 1 & -1 are good )

```python
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

print(r)
```

## Predicting future values

```python
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

speed = myfunc(10)

print(speed)
```

## Polynomial Regression

Works the same way as linear regression, the line is not straight though

![](Media/Pasted%20image%2020251017001915.png)

```python
import numpy
import matplotlib.pyplot as plt

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

myline = numpy.linspace(1, 22, 100)

plt.scatter(x, y)
plt.plot(myline, mymodel(myline))
plt.show()
```

## R Squared

R squared is used to measure the relationship between x and y axis.

```python
import numpy
from sklearn.metrics import r2_score

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

print(r2_score(y, mymodel(x)))
```
