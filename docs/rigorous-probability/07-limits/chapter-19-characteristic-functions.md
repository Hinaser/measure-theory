---
title: "第19章 特性関数と分布収束"
sidebar_label: "第19章 特性関数と分布収束"
sidebar_position: 19
description: "特性関数をFourier変換として導入し、一意性定理とLévyの連続性定理を通して分布収束の判定へつなげる。"
---

# 第19章 特性関数と分布収束

## この章で学ぶこと

特性関数は、確率変数の分布を Fourier 変換で表す道具である。この章では次を扱う。

1. Fourier変換としての特性関数
2. 特性関数の基本性質
3. 一意性定理
4. Lévyの連続性定理
5. 分布収束の判定
6. 正規分布の特性関数
7. 和の分布と畳み込み

特に、特性関数は分布収束を調べる道具であることを強調する。確率収束やほとんど確実収束を直接判定する道具ではない。

## 前提知識

複素数値確率変数の期待値、独立性、分布、分布収束を使う。Fourier 解析の詳細は仮定しない。

## 19.1 Fourier変換としての特性関数

### 定義

:::info[定義：特性関数]
実数値確率変数 $X$ の特性関数 $\varphi_X:\mathbb{R}\to\mathbb{C}$ を

$$
\varphi_X(t)=E[e^{itX}]
$$

で定義する。ただし $i$ は虚数単位である。
:::

$|e^{itX}|=1$ なので、$E[e^{itX}]$ は常に存在する。したがって、特性関数は任意の実数値確率変数に対して定義できる。

確率変数 $X$ の分布を $\mu_X$ と書けば、

$$
\varphi_X(t)=\int_{\mathbb{R}} e^{itx}\,\mu_X(dx)
$$

である。これは確率測度 $\mu_X$ の Fourier 変換である。

:::tip[直感]
分布を直接見る代わりに、すべての波 $e^{itx}$ に対する平均を集めたものが特性関数である。十分たくさんの波に対する反応を知ると、元の分布を復元できる。
:::

### 例：Bernoulli 分布

$X\sim\operatorname{Bernoulli}(p)$ とする。このとき

$$
\varphi_X(t)=E[e^{itX}]
=(1-p)e^{it\cdot0}+pe^{it\cdot1}
=1-p+pe^{it}.
$$

### 例：定数

$X=c$ a.s. なら

$$
\varphi_X(t)=e^{itc}
$$

である。

## 19.2 特性関数の基本性質

:::info[命題：基本性質]
実数値確率変数 $X$ の特性関数 $\varphi_X$ は次を満たす。

1. $\varphi_X(0)=1$
2. $|\varphi_X(t)|\le1$
3. $\varphi_X$ は一様連続である
4. $a,b\in\mathbb{R}$ に対して、$\varphi_{aX+b}(t)=e^{itb}\varphi_X(at)$
5. $E[|X|^m]<\infty$ なら、$0$ の近くで適切な意味で微分でき、特に $\varphi_X'(0)=iE[X]$、$\varphi_X''(0)=-E[X^2]$ が成り立つ
:::

### 証明の一部

$\varphi_X(0)=E[1]=1$ である。また

$$
|\varphi_X(t)|=|E[e^{itX}]|\le E[|e^{itX}|]=1.
$$

線形変換については

$$
\varphi_{aX+b}(t)
=E[e^{it(aX+b)}]
=e^{itb}E[e^{i(at)X}]
=e^{itb}\varphi_X(at).
$$

一様連続性は、$e^{ihX}\to1$ a.s. と $|e^{ihX}-1|\le2$ から支配収束定理を使って示す。

:::warning[注意]
特性関数の微分とモーメントの対応には可積分性の仮定が必要である。特性関数は常に存在するが、平均や分散が常に存在するわけではない。
:::

## 19.3 一意性定理

:::info[定理：特性関数の一意性]
実数値確率変数 $X,Y$ について

$$
\varphi_X(t)=\varphi_Y(t)\quad \text{for all }t\in\mathbb{R}
$$

ならば、$X$ と $Y$ は同分布である。
:::

この定理は、特性関数が分布を完全に決めることを意味する。証明には Fourier 反転や測度の一意性を使うため、本章では省略する。

### 何が分かるか

同じ特性関数を計算できれば、分布が同じであると結論できる。たとえば独立な和の特性関数を計算して既知の分布の特性関数と一致すれば、和の分布が分かる。

## 19.4 Lévyの連続性定理

:::info[定理：Lévy の連続性定理]
$X_1,X_2,\ldots$ と $X$ を実数値確率変数とする。このとき

$$
X_n\xrightarrow{d}X
$$

であることと、すべての $t\in\mathbb{R}$ で

$$
\varphi_{X_n}(t)\to\varphi_X(t)
$$

が成り立つことは同値である。
:::

より一般には、特性関数列 $\varphi_n(t)$ が各点収束し、その極限が $0$ で連続ならば、その極限はある確率分布の特性関数であり、対応する分布へ弱収束する。

:::warning[注意]
Lévy の連続性定理が判定しているのは分布収束である。$X_n\xrightarrow{d}X$ から $X_n\xrightarrow{P}X$ が一般に出るわけではない。
:::

## 19.5 分布収束の判定

特性関数を使う分布収束の典型的な手順は次である。

1. $X_n$ の特性関数 $\varphi_{X_n}(t)$ を計算する。
2. 各 $t$ について極限 $\lim_n\varphi_{X_n}(t)$ を求める。
3. 極限が既知の確率変数 $X$ の特性関数 $\varphi_X(t)$ と一致することを確認する。
4. Lévy の連続性定理により $X_n\xrightarrow{d}X$ と結論する。

### 例：退化分布への収束

$X_n$ が $P(X_n=1/n)=1$ を満たす定数確率変数とする。特性関数は

$$
\varphi_{X_n}(t)=e^{it/n}\to1
$$

である。$1$ は定数 $0$ の特性関数なので、$X_n\xrightarrow{d}0$ である。この例では実際には確率収束も成り立つ。

### 例：Poisson 極限定理

$X_n\sim\operatorname{Binomial}(n,\lambda/n)$ とする。Bernoulli 分布の特性関数より

$$
\varphi_{X_n}(t)=\left(1-\frac{\lambda}{n}+\frac{\lambda}{n}e^{it}\right)^n
=\left(1+\frac{\lambda(e^{it}-1)}{n}\right)^n.
$$

したがって

$$
\varphi_{X_n}(t)\to \exp(\lambda(e^{it}-1)).
$$

これは Poisson 分布 $\operatorname{Poisson}(\lambda)$ の特性関数である。よって

$$
X_n\xrightarrow{d}\operatorname{Poisson}(\lambda)
$$

である。

## 19.6 正規分布の特性関数

:::info[命題：正規分布の特性関数]
$Z\sim N(0,1)$ なら

$$
\varphi_Z(t)=e^{-t^2/2}.
$$

一般に $X\sim N(\mu,\sigma^2)$ なら

$$
\varphi_X(t)=\exp\left(i\mu t-\frac{\sigma^2t^2}{2}\right).
$$
:::

### 証明の方針

標準正規密度を用いて

$$
\varphi_Z(t)=\frac{1}{\sqrt{2\pi}}\int_{\mathbb{R}}e^{itx}e^{-x^2/2}\,dx
$$

を計算する。平方完成により $e^{-t^2/2}$ が現れる。一般の正規分布は $X=\mu+\sigma Z$ と書けるため、線形変換の性質から従う。

### 重要性

中心極限定理では、標準化された和の特性関数が $e^{-t^2/2}$ に収束することを示す。Lévy の連続性定理により、それは標準正規分布への分布収束を意味する。

## 19.7 和の分布と畳み込み

### 独立和と積

:::info[命題：独立和の特性関数]
$X,Y$ が独立な実数値確率変数なら

$$
\varphi_{X+Y}(t)=\varphi_X(t)\varphi_Y(t)
$$

である。
:::

### 証明

独立性より $e^{itX}$ と $e^{itY}$ も独立である。したがって

$$
\varphi_{X+Y}(t)
=E[e^{it(X+Y)}]
=E[e^{itX}e^{itY}]
=E[e^{itX}]E[e^{itY}]
=\varphi_X(t)\varphi_Y(t).
$$

### 畳み込み

$X$ と $Y$ が独立で、分布をそれぞれ $\mu,\nu$ とする。このとき $X+Y$ の分布は $\mu$ と $\nu$ の畳み込み $\mu*\nu$ である。Borel 集合 $B$ に対して

$$
(\mu*\nu)(B)=\int_{\mathbb{R}}\mu(B-y)\,\nu(dy)
$$

と書ける。特性関数は畳み込みを積に変える。

$$
\widehat{\mu*\nu}(t)=\widehat{\mu}(t)\widehat{\nu}(t)
$$

この性質が、独立な和を扱う極限定理で特性関数が有効な理由である。

### 例：Bernoulli 和と二項分布

$X_1,\ldots,X_n$ が独立同分布で $X_k\sim\operatorname{Bernoulli}(p)$ なら、

$$
\varphi_{\sum_{k=1}^{n}X_k}(t)
=\prod_{k=1}^{n}(1-p+pe^{it})
=(1-p+pe^{it})^n.
$$

これは二項分布 $\operatorname{Binomial}(n,p)$ の特性関数である。

## 確率論での意味

特性関数は、独立な和の分布を解析するための道具である。独立和は分布では畳み込みになるが、特性関数では積になる。積は極限計算と相性がよい。そのため、大数の法則や中心極限定理の分布面の解析で特性関数が重要になる。

## よくある誤解

1. 特性関数の収束が示すのは分布収束である。
2. 特性関数が存在することと、モーメントが存在することは別である。
3. 密度がない分布にも特性関数は定義できる。
4. 独立でない和について、特性関数を単純に積にしてはいけない。

## この章の要点

- 特性関数は $\varphi_X(t)=E[e^{itX}]$ で定義される。
- 特性関数は常に存在し、分布を一意に決める。
- Lévy の連続性定理により、特性関数の各点収束で分布収束を判定できる。
- 標準正規分布の特性関数は $e^{-t^2/2}$ である。
- 独立な和の特性関数は各特性関数の積になる。
- 畳み込みは Fourier 変換で積に変わる。

## 演習問題

1. ★ $X\sim\operatorname{Bernoulli}(p)$ の特性関数を計算せよ。
2. ★ $X=c$ a.s. のとき、$\varphi_X(t)=e^{itc}$ を示せ。
3. ★ $|\varphi_X(t)|\le1$ と $\varphi_X(0)=1$ を示せ。
4. ★★ $a,b\in\mathbb{R}$ に対して $\varphi_{aX+b}(t)=e^{itb}\varphi_X(at)$ を示せ。
5. ★★ $X,Y$ が独立なら $\varphi_{X+Y}(t)=\varphi_X(t)\varphi_Y(t)$ を示せ。
6. ★★ $X\sim\operatorname{Poisson}(\lambda)$ の特性関数が $\exp(\lambda(e^{it}-1))$ であることを示せ。
7. ★★ $X_n\sim\operatorname{Binomial}(n,\lambda/n)$ が Poisson 分布に分布収束することを、特性関数で示せ。
8. ★★ $Z\sim N(0,1)$ の特性関数を認めて、$N(\mu,\sigma^2)$ の特性関数を求めよ。
9. ★★★ Lévy の連続性定理を用いて、$\varphi_{X_n}(t)\to e^{-t^2/2}$ なら $X_n\xrightarrow{d}N(0,1)$ であることを説明せよ。
10. ★★★ 独立性がない場合に $\varphi_{X+Y}=\varphi_X\varphi_Y$ が失敗する例を作れ。

