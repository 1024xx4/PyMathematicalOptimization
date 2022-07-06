# Python ではじめる数理最適化

---

## 数理 Model とは

- 対象を数学によって記述した Model.
- 「模型」と「見本」という２つの意味がある。
- 現実の問題を簡略化した模型を通して現象を理解し、見本に倣って意思決定につなげるという一連の使い方をする。
- 現実世界に数里 Model を適用する際には、現実世界と数里 Model との Gap を認識することが重要。
  現実への適用可否の塩梅が実務において成否を決める。

### 数理最適化 Model

- 「複数の選択肢から特定の基準のもとで最適な選択肢を選ぶ」という特徴がある。
- 選択の際に組み合わせや trade-off の難しさが含まれる。

## 数理最適化 Model の Class について

Libray を利用して数理最適化 Model を解く場合、数理最適化問題にあった Library を選択する必要がある。  
※ 全ての数理最適化 Model が既存の Library で解けるわけではない。  
※ 解けたとしても現実的な時間内に解けるわけではない。

---

### 数理最適化 Model の Class 例

#### 線形計画問題

変数が実現値をとる問題。生産量（0.3kg などを許す）を決める場合等。

#### 整数計画問題

変数が整数値をとる問題。個数（0.5個などは許されない）を決める場合等。

#### 混合整数計画問題

整数計画問題の一部が実現値をとる問題。個数（0.5などは許されない）と同時に生産量（0.3kg などを許す）を決める場合など。

#### 0-1 整数計画問題

変数が 0 か 1 をとる問題。割り当て（1 で割り当てる、0 で割り当てない）を決める場合など

#### 凸二次計画問題

目的関数に凸な二次関数が現れる問題。二乗誤差を最小化する場合など。

---

## 学校の Class 編成の数理最適化問題を解くことで学習したこと
- さまざまな要件が数理 Model で表現できること
- 入力 Data の基礎的な統計量を確認できること
- 出力 Data（最適化結果）を検証すること
- 課題に気づき、解決方法を考え、数理 Model を Brush up すること

### 実務における最適化 Model の実装のコツ
#### 可能なかぎり少しずつ進め、制約式を定義するたびに最適化を実行し、意図した解が正しく得られているか確認して実装していく。
- 実務で対象とする問題は非常に複雑になる傾向がある。
- 制約式が数十個を超える場合に全て実装してから意図した解が得られなかった時、不具合の箇所の特定が困難になる。
- 制約式が追加されるたびに解の振る舞いがどのように変化するか観察しておくことで、自分が解こうとしている問題の特性を理解できる。