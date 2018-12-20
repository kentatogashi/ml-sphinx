=========================
1. データセット
=========================

kaggleからデータセット取得
====================================

$HOME/.kaggle/kaggle.jsonにAPIキーを記載する。

$HOME/.kaggle/kaggle.json::

    {"username":"********","key":"*******************************"}

データセットが取得可能なコンペ一覧を確認する。

::

    $ kaggle competitions list
    ref                                            deadline             category            reward  teamCount  userHasEntered
    ---------------------------------------------  -------------------  ---------------  ---------  ---------  --------------
    digit-recognizer                               2030-01-01 00:00:00  Getting Started  Knowledge       2755            True
    titanic                                        2030-01-01 00:00:00  Getting Started  Knowledge      10732            True
    house-prices-advanced-regression-techniques    2030-01-01 00:00:00  Getting Started  Knowledge       4707           False
    imagenet-object-localization-challenge         2029-12-31 07:00:00  Research         Knowledge         31           False
    competitive-data-science-predict-future-sales  2019-12-31 23:59:00  Playground           Kudos       1981            True
    histopathologic-cancer-detection               2019-03-30 23:59:00  Playground       Knowledge        252           False
    microsoft-malware-prediction                   2019-03-13 23:59:00  Research           $25,000        397           False
    humpback-whale-identification                  2019-02-28 23:59:00  Featured           $25,000        689            True
    elo-merchant-category-recommendation           2019-02-26 23:59:00  Featured           $50,000       1533           False
    ga-customer-revenue-prediction                 2019-02-15 23:59:00  Featured           $45,000       1104           False
    reducing-commercial-aviation-fatalities        2019-02-12 23:59:00  Playground            Swag          1           False
    quora-insincere-questions-classification       2019-02-05 23:59:00  Featured           $25,000       2374            True
    pubg-finish-placement-prediction               2019-01-30 23:59:00  Playground            Swag       1125           False
    20-newsgroups-ciphertext-challenge             2019-01-16 23:59:00  Playground            Swag         64           False
    human-protein-atlas-image-classification       2019-01-10 23:59:00  Featured           $37,000       1849           False
    traveling-santa-2018-prime-paths               2019-01-10 23:59:00  Featured           $25,000       1421           False
    NFL-Punt-Analytics-Competition                 2019-01-09 23:59:00  Analytics          $80,000          0           False
    two-sigma-financial-news                       2019-01-08 23:59:00  Featured          $100,000       2432            True
    PLAsTiCC-2018                                  2018-12-17 23:59:00  Featured           $25,000       1094           False
    quickdraw-doodle-recognition                   2018-12-04 23:59:00  Featured           $25,000       1316           False


ダウンロードする。 -c にコンペの名前、-pにダウンロードしたデータを置きたいディレクトリを指定する。

::

    $ kaggle competitions download -c titanic -p titanic
