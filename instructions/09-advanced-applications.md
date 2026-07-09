# Instruction 09 — 第24章〜第27章：発展的話題と応用

## 担当範囲

- 第24章　確率過程の基礎
- 第25章　弱収束と測度の収束
- 第26章　情報理論への接続
- 第27章　暗号理論のための確率論

## 出力ファイル

```text
docs/rigorous-probability/09-advanced/chapter-24-stochastic-processes.md
docs/rigorous-probability/09-advanced/chapter-25-weak-convergence.md
docs/rigorous-probability/09-advanced/chapter-26-information-theory.md
docs/rigorous-probability/09-advanced/chapter-27-cryptographic-probability.md
```

## 役割

本編で学んだ測度論的確率論が、確率過程・統計・機械学習・情報理論・暗号理論にどう現れるかを見せる。発展章なので、完全な証明よりも「どの概念がどこで使われるか」の地図を作る。

## 第24章で必ず扱うこと

### 中心メッセージ

確率過程は、時間で添字づけられた確率変数の族である。有限次元分布とパス空間の考え方により、過程全体を測度として扱える。

### 必須セクション

1. 確率過程とは何か
2. 離散時間と連続時間
3. 有限次元分布
4. パス空間
5. Kolmogorov 拡張定理
6. 独立増分過程
7. Poisson 過程
8. Brown 運動への導入

### 注意

Kolmogorov 拡張定理と Brown 運動は完全構成をしなくてよい。定理の役割と必要な整合性条件を説明する。

## 第25章で必ず扱うこと

### 中心メッセージ

確率測度そのものの収束を扱うには、弱収束・tightness・Portmanteau定理が必要になる。これは分布収束の一般化でもある。

### 必須セクション

1. 確率測度列の弱収束
2. 有界連続関数による定義
3. Portmanteau 定理
4. Tightness
5. Prokhorov の定理
6. 経験分布
7. 統計学・機械学習との接続

### 証明方針

Portmanteau と Prokhorov は主張と使い方を中心にする。完全証明は不要。

## 第26章で必ず扱うこと

### 中心メッセージ

情報量は確率測度の関数として定義される。特に相対エントロピーや KL ダイバージェンスは Radon-Nikodym 微分を使うと自然に書ける。

### 必須セクション

1. エントロピー
2. 連続分布での注意
3. 相対エントロピー
4. KLダイバージェンス
5. 相互情報量
6. Radon-Nikodym 微分としての尤度比
7. 確率測度間の距離
8. 暗号理論における negligible probability への接続

### 注意

- 離散エントロピーと微分エントロピーを混同しない。
- KL ダイバージェンスは距離ではないことを明示する。
- 絶対連続性の条件が必要であることを明示する。

## 第27章で必ず扱うこと

### 中心メッセージ

暗号理論では多くの場合、有限確率空間で十分であり、測度論そのものは前面に出ない。しかし、ランダム変数、分布、統計距離、coupling、negligible probability などは測度論的確率論の言葉で整理できる。

### 必須セクション

1. 有限確率空間と一様分布
2. 確率的アルゴリズムの出力を確率変数として見る
3. ランダム変数としての実験
4. negligible function
5. statistical distance
6. coupling
7. hybrid argument
8. random oracle model の確率論的見方
9. 測度論が必要な場面・不要な場面

### 必須注意

- 暗号理論では漸近的な安全性が中心なので、確率測度よりも分布族・セキュリティパラメータが重要になる。
- negligible probability は単なる「とても小さい確率」ではなく、任意の多項式の逆数より速く小さくなる関数である。
- random oracle model は理想化モデルであることを明示する。

## 例の要件

- ランダムウォークを確率過程として見る。
- Poisson過程の直感。
- 経験分布の弱収束への言及。
- KLダイバージェンスの離散例。
- Statistical distance の有限分布での計算。
- Hybrid argument の簡単な図式説明。

## 演習要件

各章 5〜8 問以上。発展章なので、証明問題より概念確認・応用問題を多めにする。

必須演習:

- 有限次元分布を具体例で書く。
- 弱収束の定義を使って簡単な収束を確認する。
- KLダイバージェンスを計算する。
- Statistical distance を計算する。
- negligible function かどうかを判定する。

## 完成条件

- 読者が測度論的確率論の応用地図を得られる。
- 発展概念を本編のどの概念に接続すればよいか分かる。
- 暗号理論では測度論が常に必要なわけではない、というバランスが取れている。
