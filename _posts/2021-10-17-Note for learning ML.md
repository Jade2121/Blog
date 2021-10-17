## Note for learning ML

### 1. StandardScaler before and after splitting data

Use standardscaler after splitting data like that:

```python
>>> from sklearn.datasets import make_classification
>>> from sklearn.linear_model import LogisticRegression
>>> from sklearn.model_selection import train_test_split
>>> from sklearn.pipeline import make_pipeline
>>> from sklearn.preprocessing import StandardScaler

>>> X, y = make_classification(random_state=42)
>>> X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=42)
>>> pipe = make_pipeline(StandardScaler(), LogisticRegression())
>>> pipe.fit(X_train, y_train)  # apply scaling on training data
Pipeline(steps=[('standardscaler', StandardScaler()),
                ('logisticregression', LogisticRegression())])

>>> pipe.score(X_test, y_test)  # apply scaling on testing data, without leaking training data.
0.96
#From sklearn documents
```

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

   



