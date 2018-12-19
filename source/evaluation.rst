=========================
決定係数
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
    print("RMSE: %.2f" % math.sqrt(mean_squared_error(y, y_pred)))
