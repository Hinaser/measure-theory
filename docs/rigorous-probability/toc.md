---
title: "厳密な確率論のための測度論入門"
sidebar_label: "目次"
sidebar_position: 1
slug: /
description: "測度論を土台にして確率空間、確率変数、期待値、独立性、極限定理、条件付き期待値まで学ぶための目次。"
---

# 厳密な確率論のための測度論入門

この教材は、素朴な確率論から一歩進んで、確率論を測度論の言葉で厳密に理解することを目標にする。

中心となる問いは次である。

- 事象とは何か。
- 確率とは何を測っているのか。
- 確率変数はなぜ可測関数なのか。
- 期待値はなぜルベーグ積分なのか。
- 独立性、条件付き期待値、収束は測度論でどう定式化されるのか。

## 第0部　準備：なぜ測度論が確率論に必要なのか

### [第1章　素朴な確率論の限界](./00-preface/chapter-01-naive-probability.md)

1. 有限集合上の確率
2. サイコロ・コイン投げ・離散確率空間
3. 連続確率分布で何が困るのか
4. 「すべての集合に確率を与える」は可能か
5. 確率とは「長さ・面積・体積」の一般化である
6. 本書のゴール：確率空間・確率変数・期待値を厳密に定義する

### [第2章　集合・写像・実数の復習](./01-foundations/chapter-02-sets-functions-reals.md)

1. 集合演算
2. 可算集合と非可算集合
3. 上限・下限
4. 実数の完備性
5. 数列・級数・極限
6. 写像、逆像、像
7. 指示関数
8. 集合列の上極限・下極限

## 第1部　測度論の基礎

### [第3章　σ-代数と可測空間](./02-measure-theory/chapter-03-sigma-algebras.md)

1. 代数とσ-代数
2. σ-代数の直感：観測可能な事象の集まり
3. 生成されるσ-代数
4. ボレル集合族
5. 可測空間
6. 写像の可測性
7. 確率論における「事象」とσ-代数

### [第4章　測度](./02-measure-theory/chapter-04-measures.md)

1. 測度の定義
2. 有限加法性と可算加法性
3. 零測度集合
4. 測度空間
5. 確率測度
6. 測度の連続性
7. Borel-Cantelli補題への導入
8. 測度論的確率の最初の例

### [第5章　外測度とルベーグ測度](./02-measure-theory/chapter-05-lebesgue-measure.md)

1. 長さをどう定義するか
2. 外測度
3. Carathéodoryの可測性条件
4. ルベーグ外測度
5. ルベーグ可測集合
6. ボレル集合とルベーグ可測集合
7. 零集合と完備化
8. 非可測集合の存在
9. 「ほとんど至るところ」の考え方

### [第6章　可測関数](./02-measure-theory/chapter-06-measurable-functions.md)

1. 可測関数の定義
2. 実数値可測関数
3. ボレル可測関数
4. 単関数
5. 可測関数の演算
6. 可測関数列の極限
7. ほとんど至るところで等しい関数
8. 確率変数はなぜ可測関数なのか

## 第2部　ルベーグ積分と期待値

### [第7章　非負可測関数の積分](./03-integration/chapter-07-nonnegative-integration.md)

1. 単関数の積分
2. 非負可測関数のルベーグ積分
3. 積分の基本性質
4. 単調収束定理
5. Fatouの補題
6. 積分と面積の直感
7. 確率論における非負確率変数の期待値

### [第8章　一般の可測関数の積分](./03-integration/chapter-08-integrable-functions.md)

1. 正部分・負部分
2. 可積分性
3. ルベーグ積分の線形性
4. 絶対可積分性
5. 支配収束定理
6. 積分と極限の交換
7. 期待値の厳密な定義
8. 分散・モーメント・絶対モーメント

### [第9章　$L^p$ 空間](./03-integration/chapter-09-lp-spaces.md)

1. $L^1, L^2, L^p$ の定義
2. ほとんど至るところ等しい関数の同一視
3. Hölderの不等式
4. Minkowskiの不等式
5. $L^p$ ノルム
6. $L^2$ と内積
7. 完備性
8. 確率変数の空間としての $L^p$

## 第3部　確率空間と確率変数

### [第10章　確率空間](./04-probability-space/chapter-10-probability-spaces.md)

1. 確率空間 $(\Omega, \mathcal{F}, P)$
2. 標本空間
3. 事象
4. 確率測度
5. 離散確率空間
6. 連続確率空間
7. 事象列と極限事象
8. ほとんど確実に起こる事象

### [第11章　確率変数](./04-probability-space/chapter-11-random-variables.md)

1. 確率変数の定義
2. 離散確率変数
3. 実数値確率変数
4. ベクトル値確率変数
5. 確率変数が生成するσ-代数
6. 分布
7. 分布関数
8. 確率変数の変換
9. 同分布と同一視してよいもの・いけないもの

### [第12章　分布と測度](./05-distributions/chapter-12-distributions-as-measures.md)

1. 確率変数の分布は押し出し測度である
2. Pushforward measure
3. 分布関数と確率測度の対応
4. 離散分布
5. 絶対連続分布
6. 密度関数
7. 特異分布
8. Radon-Nikodym微分への導入
9. 「密度が存在する」とはどういうことか

### [第13章　期待値](./05-distributions/chapter-13-expectation.md)

1. 期待値の定義
2. 分布による期待値の計算
3. LOTUS：無意識の統計学者の法則
4. 指示関数と確率
5. 分散・共分散
6. モーメント
7. 確率母関数・モーメント母関数・特性関数への導入
8. Jensenの不等式
9. Markovの不等式
10. Chebyshevの不等式

## 第4部　積分の発展と独立性

### [第14章　積測度とFubiniの定理](./06-independence/chapter-14-product-measures-fubini.md)

1. 直積σ-代数
2. 積測度
3. 確率空間の直積
4. Tonelliの定理
5. Fubiniの定理
6. 重積分と期待値
7. 独立な確率変数の構成
8. 同時分布と周辺分布

### [第15章　独立性](./06-independence/chapter-15-independence.md)

1. 事象の独立性
2. σ-代数の独立性
3. 確率変数の独立性
4. 有限族・無限族の独立性
5. 独立性と積測度
6. 独立確率変数の期待値
7. 独立確率変数の和
8. Borel-Cantelli補題
9. Kolmogorovの0-1法則への導入

### [第16章　Radon-Nikodym定理](./06-independence/chapter-16-radon-nikodym.md)

1. 絶対連続性
2. 特異性
3. Radon-Nikodym定理
4. 密度関数の一般化
5. 確率測度の変換
6. 尤度比
7. 条件付き確率への準備
8. 情報量・KLダイバージェンスへの接続

## 第5部　収束概念と極限定理

### [第17章　確率変数列の収束](./07-limits/chapter-17-convergence-of-random-variables.md)

1. 各点収束
2. ほとんど確実収束
3. 確率収束
4. $L^p$ 収束
5. 分布収束
6. 収束概念の関係
7. 反例で理解する収束の違い
8. 一様可積分性への導入

### [第18章　大数の法則](./07-limits/chapter-18-laws-of-large-numbers.md)

1. 標本平均
2. 弱法則
3. 強法則
4. Chebyshevによる証明
5. Borel-Cantelliによる証明
6. 独立同分布列
7. 測度論的に見る「頻度は確率に近づく」

### [第19章　特性関数と分布収束](./07-limits/chapter-19-characteristic-functions.md)

1. Fourier変換としての特性関数
2. 特性関数の基本性質
3. 一意性定理
4. Lévyの連続性定理
5. 分布収束の判定
6. 正規分布の特性関数
7. 和の分布と畳み込み

### [第20章　中心極限定理](./07-limits/chapter-20-central-limit-theorem.md)

1. 正規分布
2. 標準化
3. 独立同分布の場合の中心極限定理
4. Lindeberg条件
5. Lyapunov条件
6. 特性関数による証明
7. 中心極限定理の意味
8. 暗号・統計・機械学習への応用例

## 第6部　条件付き確率と条件付き期待値

### [第21章　条件付き確率の再定義](./08-conditioning/chapter-21-conditional-probability.md)

1. 初等的な条件付き確率
2. $P(A \mid B)$ の限界
3. σ-代数で条件づける
4. 情報としてのσ-代数
5. 条件付き確率の直感
6. 正則条件付き確率への導入

### [第22章　条件付き期待値](./08-conditioning/chapter-22-conditional-expectation.md)

1. 条件付き期待値の定義
2. Radon-Nikodym定理による構成
3. 条件付き期待値の一意性
4. 基本性質
5. 塔性質
6. 独立性との関係
7. $L^2$ 射影としての条件付き期待値
8. ベイズの定理の測度論的理解

### [第23章　マルチンゲール入門](./08-conditioning/chapter-23-martingales.md)

1. フィルトレーション
2. 適合過程
3. マルチンゲール
4. サブマルチンゲール・スーパーマルチンゲール
5. 停止時刻
6. 任意停止定理の直感
7. Doobの不等式
8. 確率過程への入口

## 第7部　発展的話題

### [第24章　確率過程の基礎](./09-advanced/chapter-24-stochastic-processes.md)

1. 確率過程とは何か
2. 有限次元分布
3. パス空間
4. Kolmogorov拡張定理
5. 独立増分過程
6. Poisson過程
7. Brown運動への導入

### [第25章　弱収束と測度の収束](./09-advanced/chapter-25-weak-convergence.md)

1. 確率測度列の弱収束
2. Portmanteau定理
3. Tightness
4. Prokhorovの定理
5. 経験分布
6. 統計学・機械学習との接続

### [第26章　情報理論への接続](./09-advanced/chapter-26-information-theory.md)

1. エントロピー
2. 相対エントロピー
3. KLダイバージェンス
4. 相互情報量
5. Radon-Nikodym微分としての尤度比
6. 確率測度間の距離
7. 暗号理論における negligible probability

### [第27章　暗号理論のための確率論](./09-advanced/chapter-27-cryptographic-probability.md)

1. 有限確率空間と一様分布
2. ランダム変数としてのアルゴリズムの出力
3. 確率的アルゴリズム
4. negligible function
5. statistical distance
6. coupling
7. hybrid argument
8. random oracle modelの確率論的見方
9. 測度論が必要な場面・不要な場面

## 第8部　付録

### [付録A　集合論の補足](./10-appendices/appendix-a-set-theory.md)

1. 選択公理
2. Zornの補題
3. 非可測集合と選択公理
4. 濃度
5. 実数直線の構造

### [付録B　位相空間の基礎](./10-appendices/appendix-b-topology.md)

1. 開集合・閉集合
2. 連続写像
3. コンパクト性
4. 距離空間
5. Borel集合族
6. Polish空間への導入

### [付録C　解析学の補足](./10-appendices/appendix-c-analysis.md)

1. Riemann積分とLebesgue積分
2. 単調収束と支配収束の比較
3. 関数列の収束
4. Fourier解析の基礎
5. 畳み込み

### [付録D　よく使う不等式](./10-appendices/appendix-d-inequalities.md)

1. Jensenの不等式
2. Hölderの不等式
3. Minkowskiの不等式
4. Markovの不等式
5. Chebyshevの不等式
6. Cauchy-Schwarzの不等式
7. Chernoff bound
8. Hoeffding bound

### [付録E　演習問題のヒントと解答](./10-appendices/appendix-e-solutions.md)

1. 第1部の解答
2. 第2部の解答
3. 第3部の解答
4. 第4部の解答
5. 第5部の解答
6. 第6部の解答
7. 発展問題の解答

## 推奨読書ルート

### 最短復習ルート

第3章 → 第4章 → 第6章 → 第7章 → 第8章 → 第10章 → 第11章 → 第13章

### 測度論ベースの確率論ルート

第3章 → 第4章 → 第5章 → 第6章 → 第7章 → 第8章 → 第10章 → 第11章 → 第12章 → 第13章 → 第15章 → 第17章 → 第18章 → 第20章

### 発展ルート

第14章 → 第16章 → 第21章 → 第22章 → 第23章 → 第24章 → 第25章

### 暗号・情報理論ルート

第10章 → 第11章 → 第13章 → 第15章 → 第17章 → 第26章 → 第27章
