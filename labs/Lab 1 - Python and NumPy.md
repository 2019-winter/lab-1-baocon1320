---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**BAO NGUYEN And KUSH UPADHYAY**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


**YOUR ANSWER HERE**


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
import numpy as np
# YOUR SOLUTION HERE
a = np.full((6, 4), 2)
a
```

## Exercise 2

```python
# YOUR SOLUTION HERE
b = np.eye(6,4) * 2 + np.full((6,4),1)
b
```

## Exercise 3

```python
# YOUR SOLUTION HERE
a*b
print('We can multiply these two matrices A * B because it will multiply row by row and column by column,' 
      'but we cannot do dot(a,b) because the size of row in A must equal to size of column in B and size of column'
      'in A must be equal size of row in B. ')
```

## Exercise 4


# YOUR SOLUTION HERE
Due to the nature of dot function, the result of dot function have the row's size of first arg, 
the column's take the column's size of second arg. 


## Exercise 5

```python
# YOUR SOLUTION HERE
print('hello')
```

## Exercise 6

```python
# YOUR SOLUTION HERE
c = np.random.rand(2,3)
c_sum = c.sum()
c_mean = c.mean()
print(c)
print(c_sum)
print(c_mean)
```

## Exercise 7

```python
def count_1(input):
    count = 0
    for i in input.flatten():       
        if i == 1:
            count += 1
    return count
        

# YOUR SOLUTION HERE
test = np.array((2,1,2,3,1,21,1,1,1,1,2,3)).reshape(3,2,2)
d = np.where(test == 1, 1, 0)
print(d.sum())
print(count_1(test))
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
import pandas as pd
# YOUR SOLUTION HERE
a = np.full((6, 4), 2)
a = pd.DataFrame(a)
a
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
b = np.full((6,4),1)
b = pd.DataFrame(b)
b.iloc[range(4),range(4)] = 3
b
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
a*b
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
def pd_count_1(input):
    count = 0
    for i in range(input.shape[0]):
        for j in range(input.shape[1]):
            if input.iloc[i,j] == 1:
                count += 1
    return count

# YOUR SOLUTION HERE
print(b[b==1].count().sum())
print(pd_count_1(b))

```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE
titanic_df["name"]
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
titanic_df.loc['female']
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
titanic_df.reset_index(inplace = True)
titanic_df
```

```python

```

```python

```
