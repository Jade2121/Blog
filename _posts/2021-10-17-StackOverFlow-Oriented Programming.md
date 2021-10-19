# StackOverFlow-Oriented Programming

![image](https://user-images.githubusercontent.com/39907449/137663134-c3918d63-94fc-4c99-9f77-f578a6509b0d.png)


## Note for ML

### 1. StandardScaler before or after splitting data

###### 2021-10-17

The test set should ideally not be preprocessed with the training data. This will ensure no 'peeking ahead'. 

To avoid test set be polluted by train, just split the data then carry out standardscaler  to train set. Then you can build your model as test set does not exist. When the model is done, standardscaler the test set using ```X_test_std = sc.transform(X_test)```. 

Use standardscaler after splitting data like that:

```python
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split

#standardizing after splitting
X_train, X_test, y_train, y_test = train_test_split(data, target)
sc = StandardScaler().fit(X_train)
X_train_std = sc.transform(X_train)
X_test_std = sc.transform(X_test)
#From stackexchange
```

#### Reference:

1. [Difference between preprocessing train and test set before and after splitting](https://stats.stackexchange.com/questions/267012/difference-between-preprocessing-train-and-test-set-before-and-after-splitting)

2. [StandardScaler before and after splitting data](https://datascience.stackexchange.com/questions/38395/standardscaler-before-and-after-splitting-data)

3. [Is it correct to use a single StandardScaler before splitting data?](https://stackoverflow.com/questions/63037248/is-it-correct-to-use-a-single-standardscaler-before-splitting-data)

4. [Preprocessing data](https://scikit-learn.org/stable/modules/preprocessing.html)

5. [数据预处理的归一化手段应该如何应用到训练集，测试集和验证集中？](https://www.zhihu.com/question/60490799)

   

### 2. Different algorithms:

###### 2021-10-17

#### 1. KNN

[Creating a K Nearest Neighbors Classifier from scratch](https://pythonprogramming.net/programming-k-nearest-neighbors-machine-learning-tutorial/)

#### 2. Nearest Centroid

[`sklearn.neighbors`.NearestCentroid](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.NearestCentroid.html#)



### 3. Jupyter Notebook generate PDF without code

###### 2021-10-17

Make sure you are working with Qt Console (anaconda):

Install Jupiter extensions:

```py
!pip install jupyter_contrib_nbextensions

!jupyter contrib nbextension install --user 
```

Enable nbextension:

```py
!jupyter nbextension enable codefolding/main
```

Install pyppeteer:

```py
!python -m pip install -U notebook-as-pdf

!pyppeteer-install
```
Then type this command in your shell, remember in your working directory.

```shell
!jupyter-nbconvert Untitled.ipynb --no-input --no-prompt --to pdfviahtml
```

#### Reference:

[Generate pdf from jupyter notebook without code](https://datascience.stackexchange.com/questions/77352/generate-pdf-from-jupyter-notebook-without-code)

### 4. How to delete an element in numpy array

###### 2021-10-17

I want to delete point from dataSet, what should I do?

At first, you need to get the index of the element you want to delete, such as point, using the following code```np.where(condition[, x, y])```. The argument is a condition like x>5 or x == 10.

Then, you should find the index of the element, point. Use this code: ```array[index][index] ```, we can process it to get the index.

At last, using ```np.delete(x,y,axis=)``` to delete x from y.

E.G.

x =np.array([[0,0],[1,1],[2,2]]) we want to delete [0,0]

```python
x = np.array([[0,0],[1,1],[2,2]])
print(x)
tup = np.where(x==[0,0])#Return a tuple
print(tup)
x1 = np.delete(x,tup[0][0],axis=0)
print(x1)
```
The output:
```python
[[0 0]
 [1 1]
 [2 2]]
(array([0, 0], dtype=int64), array([0, 1], dtype=int64))
[[1 1]
 [2 2]]
```


#### Reference

[numpy.where](https://numpy.org/doc/stable/reference/generated/numpy.where.html#numpy-where)

[numpy.delete](https://numpy.org/doc/stable/reference/generated/numpy.delete.html#)

[python - 一次删除numpy数组中某个值的元素](https://www.coder.work/article/3220238)



### 5. How to change data type in Numpy

###### 2021-10-18

Use ```.dtype``` to see data type. Then use ```.astype(np.type)``` to change data type.

#### Reference

[Data type objects(`dtype`)](https://numpy.org/doc/stable/reference/generated/numpy.dtype.html#numpy.dtype)



