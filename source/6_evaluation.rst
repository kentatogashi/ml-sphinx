=========================
6. 評価
=========================

準備
======

::

    from sklearn.datasets import load_boston
    from sklearn.linear_model import LinearRegression
    boston = load_boston()
    X = boston.data
    y = boston.target
    clf = LinearRegression()
    clf.fit(X, y)
    y_pred = clf.predict(y, y_pred)

二乗平均平方誤差(RMSE)
==================

回帰分析の評価::

    import math
    from sklearn.metrics import mean_squared_error
    print('RMSE: %.2f' % math.sqrt(mean_squared_error(y, y_pred)))
    # RMSE: 4.68

決定係数
==================

参考: https://bellcurve.jp/statistics/course/9706.html

推定された回帰式の当てはまりの良さを表す。0 ~ 1の値を取り、1に近いほど実際のデータへの当てはまりが良いことを示す。

回帰分析の評価::

    from sklearn.metrics import r2_score
    print('r2 score: %.2f' % r2_score(y, y_pred))
    # r2 score: 0.74

