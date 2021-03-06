# BG21_analysis
BG21を分析するツール

# 基本設定値
* スタート時の資本金は5,000,000円
* 仕入価格:50,000(円/台)
* 最低現金有高:期末に現金の残高が500,000円を下回る場合、自動的に500,000円になるように借り入れする。借り入れをすると返済はできない。
* 支払利息率:借り入れをした場合、毎期借入金の残高の6％の金額を支払う。利息は借入時にも支払う。
* マーケットサイズ
    * 第１期:800台
    * 第２期:1200台
    * 第３期:1600台
    * 第４期:1200台
* 役員の給料の合計:毎期3,000,000円
* 店舗家賃:毎期300,000円

# ルール
* 仕入れ数量:プラスの整数であれば、何代でも仕入れ可能。
* 販売価格：販売価格上限100,000円以下の正数。0円は不可。
* 広告費：正数。０円でも可。
* 広告費と販売価格の重みづけ係数:広告費:販売価格=50%:50％

# 計算
* 販売価格による受注割当比率
    * 自社値引額=販売価格上限 - 自社の販売価格
    * 受注割当比率 = 自社値引額 ÷ 全社の値引額
* 広告費による受注割当比率
    *受注割当比率 = 自社の広告費 ÷ 全社の広告費
* 利益
    利益=受注数量*販売価格-(広告+役員給料+店舗家賃+)-(借入金×0.06)
* 50万以下になった場合の期ごとの借入金額 = (最低現金有高+支払利息率×合計借入金額-所持金)/(1-支払利息率)


