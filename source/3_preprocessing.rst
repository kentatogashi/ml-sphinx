=========================
3. 前処理
=========================

sklearnのdatasetsをDataFrameへ変換
====================================

::

    import numpy as np
    import pandas as pd
    from sklearn.datasets import load_iris, load_boston,load_breast_cancer
    iris = load_iris()
    df = pd.DataFrame(np.c_[iris.data, iris.target], columns=iris.feature_names + ['species'])
    >>>    sepal length (cm)  sepal width (cm)  petal length (cm)  petal width (cm)  species
    0                5.1               3.5                1.4               0.2      0.0
    1                4.9               3.0                1.4               0.2      0.0
    2                4.7               3.2                1.3               0.2      0.0
    3                4.6               3.1                1.5               0.2      0.0
    4                5.0               3.6                1.4               0.2      0.0
    boston = load_boston()
    df = pd.DataFrame(np.c_[boston.data, boston.target], columns=np.append(boston.feature_names, 'PRICE'))
    >>>    CRIM    ZN  INDUS  CHAS    NOX     RM  ...    RAD    TAX  PTRATIO       B  LSTAT  PRICE
    0  0.00632  18.0   2.31   0.0  0.538  6.575  ...    1.0  296.0     15.3  396.90   4.98   24.0
    1  0.02731   0.0   7.07   0.0  0.469  6.421  ...    2.0  242.0     17.8  396.90   9.14   21.6
    2  0.02729   0.0   7.07   0.0  0.469  7.185  ...    2.0  242.0     17.8  392.83   4.03   34.7
    3  0.03237   0.0   2.18   0.0  0.458  6.998  ...    3.0  222.0     18.7  394.63   2.94   33.4
    4  0.06905   0.0   2.18   0.0  0.458  7.147  ...    3.0  222.0     18.7  396.90   5.33   36.2
    
    [5 rows x 14 columns]
    df = pd.DataFrame(np.c_[breast_cancer.data, breast_cancer.target], columns=np.append(breast_cancer.feature_names, ['has_cancer']))
    >>>   mean radius  mean texture     ...      worst fractal dimension  has_cancer
    0        17.99         10.38     ...                      0.11890         0.0
    1        20.57         17.77     ...                      0.08902         0.0
    2        19.69         21.25     ...                      0.08758         0.0
    3        11.42         20.38     ...                      0.17300         0.0
    4        20.29         14.34     ...                      0.07678         0.0
    
    [5 rows x 31 columns]


任意の条件に合致する列の値を更新
========================================

参考: https://www.kaggle.com/ash316/eda-to-prediction-dietanic

::

    data = pd.read_csv('titanic/train.csv')
    # AgeがNaNの場合は、30を挿入
    data.loc[data['Age'].isnull(), 'Age'] = 30
    # Ageが20以上40未満であれば、Age_Catに2を挿入
    data.loc[(data['Age'] > 20) & (data['Age'] <= 40), 'Age_Cat'] = 2




