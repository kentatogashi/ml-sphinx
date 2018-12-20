=========================
2. 探索的データ解析
=========================

モデルを構築する前に、データそのものを理解する過程。

データそのもの、統計量、相関などを見たり、可視化したりする。

準備
======

::

    data = pd.read_csv('titanic/train.csv')

各列の欠損値確認
================

欠損値を含む場合は、欠損値の補完、列の削除などの処理が必要になる。

::

    In [54]: data.isnull().sum()
    Out[54]:
    PassengerId      0
    Survived         0
    Pclass           0
    Name             0
    Sex              0
    Age            177
    SibSp            0
    Parch            0
    Ticket           0
    Fare             0
    Cabin          687
    Embarked         2
    dtype: int64

クロス集計
===================

::

    In [53]: pd.crosstab(data.Pclass, data.Survived, margins=True)
    Out[53]:
    Survived    0    1  All
    Pclass
    1          80  136  216
    2          97   87  184
    3         372  119  491
    All       549  342  891

