=========================
回帰
=========================

準備
=========================

::

    from sklearn.datasets import load_boston
    boston = load_boston()
    X = boston.data
    y = boston.target


線形回帰
=========================

誤差関数に、最小二乗誤差を用いて、パラメータと重みを最適化する回帰モデル。

::

    from sklearn.linear_model import LinearRegression
    clf = LinearRegression()
    clf.fit(X, y)
    y_pred = clf.predict(X)
    print(y_pred[0:3])
    >>> [30.00384338 25.02556238 30.56759672]
    print('r2 score: %.2f' % clf.score(X, y))
    >>> r2 score: 0.74

Rigde回帰
=========================

訓練データによる過学習を防ぐために、誤差関数に正則化項を加えて、最小化する回帰モデル。

正則化項として、L2ノルム(係数のユークリッド長)を使う。

正則化については、https://tjo.hatenablog.com/entry/2015/03/03/190000 が参考になる。

::

    from sklearn.linear_model import Ridge
    clf = Ridge()
    clf.fit(X, y)
    y_pred = clf.predict(X)
    print(y_pred[0:3])
    >>> [30.25311604 24.80547336 30.53232402]
    print('r2 score: %.2f' % clf.score(X, y))
    >>> r2 score: 0.74

サポートベクター回帰
=========================

サポートベクターマシンを使った回帰モデル。

::

    from sklearn.svm import SVR
    clf = SVR()
    clf.fit(X, y)
    print('r2 score: %.2f' % clf.score(X, y))
    >>> r2 score: 0.37
