---
title: "第22章 条件付き期待値"
sidebar_label: "第22章 条件付き期待値"
sidebar_position: 22
description: "条件付き期待値を部分σ-代数に関する可測な確率変数として定義し、Radon-Nikodym定理、塔性質、独立性、L2射影との関係を学ぶ。"
---

# 第22章 条件付き期待値

## この章で学ぶこと

条件付き期待値 $\mathbb{E}[X\mid\mathcal{G}]$ は、$X$ の平均を一つの数として返すものではない。部分 σ-代数 $\mathcal{G}$ が表す情報だけを使って $X$ を予測する、$\mathcal{G}$-可測な確率変数である。

この章では、有限分割の場合の計算から始め、Radon-Nikodym 定理による構成、一意性、基本性質、塔性質、独立性との関係、$L^2$ 射影としての意味、ベイズの定理との関係を扱う。

## 前提知識

確率空間 $(\Omega,\mathcal{F},P)$、可積分確率変数 $X\in L^1$、部分 σ-代数、第16章の[Radon-Nikodym 定理](../06-independence/chapter-16-radon-nikodym.md)、第9章の[$L^2$ 空間](../03-integration/chapter-09-lp-spaces.md)の内積を使う。

## 22.1 条件付き期待値の定義

$\mathbb{E}[X]$ は、情報を何も条件にしないときの $X$ の平均である。一方、$\mathbb{E}[X\mid\mathcal{G}]$ は、$\mathcal{G}$ に含まれる情報を知っている状態での $X$ の平均である。

:::tip[直感]
$\mathbb{E}[X\mid\mathcal{G}]$ は、$\mathcal{G}$ の情報だけを使って作れる $X$ の予測値である。  
したがって、それ自体が $\mathcal{G}$-可測な確率変数でなければならない。
:::

条件付き期待値は、次の二つの条件を同時に満たすものとして定義される。

1. $\mathcal{G}$ の情報だけで値が分かる。
2. $\mathcal{G}$ で見える任意の範囲 $G$ 上で、積分値が元の $X$ と一致する。

### 有限分割の場合

まず有限分割で具体的に見る。$\Omega$ が互いに素な事象 $C_1,\ldots,C_n$ に分割され、$P(C_i)>0$ とする。$\mathcal{G}=\sigma(C_1,\ldots,C_n)$ とおく。

$\mathcal{G}$-可測な確率変数は、各 $C_i$ 上で定数である。したがって $\mathbb{E}[X\mid\mathcal{G}]$ は

$$
\mathbb{E}[X\mid\mathcal{G}](\omega)
=\frac{1}{P(C_i)}\int_{C_i}X\,dP
\qquad(\omega\in C_i)
$$

となる。

### 例：サイコロで偶奇だけを知る

公平なサイコロの出目を $X(\omega)=\omega$ とする。偶奇だけを表す分割

$$
C_1=\{1,3,5\},\qquad C_2=\{2,4,6\}
$$

を考える。$\mathcal{G}=\sigma(C_1,C_2)$ とすると、

$$
\mathbb{E}[X\mid\mathcal{G}](\omega)=
\begin{cases}
3, & \omega\in C_1,\\
4, & \omega\in C_2.
\end{cases}
$$

奇数と分かれば候補は $1,3,5$ で平均は $3$、偶数と分かれば候補は $2,4,6$ で平均は $4$ である。

### 例：コイン二回投げ

公平なコインを二回投げ、表の回数を $X$ とする。第一投の結果だけを表す σ-代数を $\mathcal{G}$ とする。

第一投が表なら、第二投の表の期待値は $1/2$ なので

$$
\mathbb{E}[X\mid\mathcal{G}]=1+\frac{1}{2}
$$

である。第一投が裏なら

$$
\mathbb{E}[X\mid\mathcal{G}]=0+\frac{1}{2}
$$

である。条件付き期待値は、第一投の結果に応じて $3/2$ または $1/2$ を取る確率変数になる。

### 一般の定義

:::info[定義：条件付き期待値]
$(\Omega,\mathcal{F},P)$ を確率空間、$\mathcal{G}\subset\mathcal{F}$ を部分 σ-代数、$X\in L^1(\Omega,\mathcal{F},P)$ とする。

$\mathbb{E}[X\mid\mathcal{G}]$ とは、次を満たす $\mathcal{G}$-可測な確率変数 $Y$ のことである。

$$
\int_G Y\,dP=\int_G X\,dP
\quad (G\in\mathcal{G}).
$$

このような $Y$ を、$X$ の $\mathcal{G}$ に関する条件付き期待値という。
:::

この定義では、$Y$ は通常の関数として一点ごとに一意に決まるわけではない。$P$-ほとんど確実に等しい範囲で一意に決まる。

:::warning[注意：条件付き期待値は同値類である]
$\mathbb{E}[X\mid\mathcal{G}]$ は、厳密には $P$-ほとんど確実に等しい確率変数を同一視した同値類として扱う。  
一点ごとの値に意味を持たせるには、特定のバージョンを選んでいると考える。
:::

## 22.2 Radon-Nikodym定理による構成

条件付き期待値の存在は、Radon-Nikodym 定理から従う。

まず $X\ge 0$ の場合を考える。$\mathcal{G}$ 上の測度 $\nu$ を

$$
\nu(G)=\int_G X\,dP
\qquad(G\in\mathcal{G})
$$

で定める。$\nu$ は $\mathcal{G}$ 上の測度であり、$P|_{\mathcal{G}}$ に関して絶対連続である。なぜなら $P(G)=0$ なら $\int_G X\,dP=0$ だからである。

Radon-Nikodym 定理により、ある $\mathcal{G}$-可測関数 $Y\ge 0$ が存在して

$$
\nu(G)=\int_G Y\,dP
\qquad(G\in\mathcal{G})
$$

を満たす。この $Y$ が $\mathbb{E}[X\mid\mathcal{G}]$ である。

一般の $X\in L^1$ については、$X=X^+-X^-$ と分解し、

$$
\mathbb{E}[X\mid\mathcal{G}]
=\mathbb{E}[X^+\mid\mathcal{G}]
-\mathbb{E}[X^-\mid\mathcal{G}]
$$

で定める。

:::warning[注意]
ここで使う Radon-Nikodym 定理は、$\nu$ が $P|_{\mathcal{G}}$ に絶対連続であるという仮定のもとで適用している。条件なしに密度が存在するわけではない。
:::

## 22.3 条件付き期待値の一意性

:::info[命題：条件付き期待値の一意性]
$Y$ と $Z$ がともに $X$ の $\mathcal{G}$ に関する条件付き期待値ならば、

$$
Y=Z \quad P\text{-ほとんど確実に}
$$

である。
:::

### 証明

$Y$ と $Z$ は $\mathcal{G}$-可測であり、すべての $G\in\mathcal{G}$ に対して

$$
\int_G Y\,dP=\int_G X\,dP=\int_G Z\,dP
$$

が成り立つ。したがって

$$
\int_G (Y-Z)\,dP=0
\qquad(G\in\mathcal{G})
$$

である。

$H=\{Y>Z\}$ とおくと、$H\in\mathcal{G}$ である。もし $P(H)>0$ なら、$H$ 上で $Y-Z>0$ なので $\int_H(Y-Z)\,dP>0$ となり矛盾する。よって $P(Y>Z)=0$。同様に $P(Z>Y)=0$。したがって $Y=Z$ が $P$-ほとんど確実に成り立つ。

## 22.4 基本性質

以下では、すべての等号は特に断らない限り $P$-ほとんど確実な等号である。

:::info[命題：線形性]
$X,Y\in L^1$、$a,b\in\mathbb{R}$ ならば

$$
\mathbb{E}[aX+bY\mid\mathcal{G}]
=a\mathbb{E}[X\mid\mathcal{G}]
+b\mathbb{E}[Y\mid\mathcal{G}].
$$
:::

:::info[命題：単調性]
$X,Y\in L^1$ かつ $X\le Y$ が $P$-ほとんど確実に成り立つならば、

$$
\mathbb{E}[X\mid\mathcal{G}]
\le
\mathbb{E}[Y\mid\mathcal{G}]
$$

が $P$-ほとんど確実に成り立つ。
:::

:::info[命題：既に見えている量]
$X\in L^1$ が $\mathcal{G}$-可測ならば、

$$
\mathbb{E}[X\mid\mathcal{G}]=X.
$$
:::

:::info[命題：外に出せる因子]
$X\in L^1$、$Z$ が有界な $\mathcal{G}$-可測確率変数ならば、

$$
\mathbb{E}[ZX\mid\mathcal{G}]
=Z\mathbb{E}[X\mid\mathcal{G}].
$$
:::

### 証明スケッチ

いずれも定義の積分条件から示す。たとえば線形性では、任意の $G\in\mathcal{G}$ について積分の線形性を使う。単調性では、$X\le Y$ なら $\int_G X\,dP\le\int_G Y\,dP$ であることと、一意性を使う。

## 22.5 塔性質

条件付き期待値の最重要性質の一つが塔性質である。

:::info[定理：塔性質]
$\mathcal{H}\subset\mathcal{G}\subset\mathcal{F}$ を部分 σ-代数、$X\in L^1$ とする。このとき

$$
\mathbb{E}\left[\mathbb{E}[X\mid\mathcal{G}]\mid\mathcal{H}\right]
=\mathbb{E}[X\mid\mathcal{H}]
$$

が $P$-ほとんど確実に成り立つ。
:::

### 証明

左辺を $Y$ とおく。$Y$ は $\mathcal{H}$-可測である。任意の $H\in\mathcal{H}$ について、$H\in\mathcal{G}$ でもあるから

$$
\int_H Y\,dP
=\int_H \mathbb{E}[X\mid\mathcal{G}]\,dP
=\int_H X\,dP.
$$

したがって $Y$ は $\mathbb{E}[X\mid\mathcal{H}]$ の定義を満たす。一意性より主張が従う。

:::tip[直感]
細かい情報 $\mathcal{G}$ で一度予測し、それを粗い情報 $\mathcal{H}$ だけで見直すと、最初から粗い情報 $\mathcal{H}$ で予測したものと同じになる。
:::

## 22.6 独立性との関係

:::info[命題：独立な情報で条件づけても平均は変わらない]
$X\in L^1$ が部分 σ-代数 $\mathcal{G}$ と独立であるとする。このとき

$$
\mathbb{E}[X\mid\mathcal{G}]
=\mathbb{E}[X]
$$

が $P$-ほとんど確実に成り立つ。
:::

### 証明スケッチ

まず $X=1_A$ の場合を考える。$A$ と $\mathcal{G}$ が独立なら、任意の $G\in\mathcal{G}$ について

$$
\int_G 1_A\,dP=P(A\cap G)=P(A)P(G)=\int_G P(A)\,dP.
$$

よって $\mathbb{E}[1_A\mid\mathcal{G}]=P(A)$。単関数、非負可測関数、可積分関数へ標準的な近似で拡張する。

逆に、$X$ が $\mathcal{G}$-可測なら $\mathbb{E}[X\mid\mathcal{G}]=X$ である。つまり、既に知っている量はそのまま残り、独立で何も教えてくれない情報で条件づけると平均に戻る。

## 22.7 $L^2$ 射影としての条件付き期待値

$X\in L^2$ とする。このとき $\mathbb{E}[X\mid\mathcal{G}]$ は、$L^2(\Omega,\mathcal{G},P)$ への直交射影として理解できる。

$L^2(\Omega,\mathcal{G},P)$ は、$\mathcal{G}$-可測で二乗可積分な確率変数全体を、ほとんど確実な同値で割った閉部分空間である。

:::info[定理：$L^2$ 射影]
$X\in L^2(\Omega,\mathcal{F},P)$ とする。このとき $Y=\mathbb{E}[X\mid\mathcal{G}]$ は $L^2(\Omega,\mathcal{G},P)$ の元であり、任意の $Z\in L^2(\Omega,\mathcal{G},P)$ に対して

$$
\mathbb{E}[(X-Y)Z]=0
$$

を満たす。したがって $Y$ は $X$ の $L^2(\Omega,\mathcal{G},P)$ への直交射影である。
:::

### 確率論的な意味

$L^2$ の意味では、$\mathbb{E}[X\mid\mathcal{G}]$ は $\mathcal{G}$ の情報だけで作れる予測のうち、平均二乗誤差

$$
\mathbb{E}[(X-Z)^2]
$$

を最小にするものである。

:::tip[直感]
条件付き期待値は「部分情報のもとでの最良予測」である。この「最良」は、$L^2$ では直交射影として厳密に表される。
:::

## 22.8 ベイズの定理の測度論的理解

初等的なベイズの定理は

$$
P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}
$$

である。測度論的には、これは確率測度の密度、すなわち Radon-Nikodym 微分の変換として理解できる。

たとえばパラメータ $\Theta$ と観測 $X$ を考える。事前分布、尤度、周辺分布が適切に存在する場合、事後分布は

$$
\text{事後分布}
\propto
\text{尤度}\times\text{事前分布}
$$

という形になる。この比例関係は、分母にあたる周辺密度で正規化される。

ただし、密度が存在するとは限らない。一般には、条件付き分布や正則条件付き確率を用いて表す必要がある。

:::warning[注意]
ベイズの公式を密度の形で書けるのは、基準測度に関する密度が存在する場合である。測度論的には、密度の存在条件と、どの測度に関する Radon-Nikodym 微分かを明示する必要がある。
:::

## 確率論での意味

条件付き期待値は、測度論的確率論の中心的な道具である。

- 条件付き確率は $\mathbb{E}[1_A\mid\mathcal{G}]$ として定義できる。
- マルチンゲールは $\mathbb{E}[X_{n+1}\mid\mathcal{F}_n]=X_n$ によって定義される。
- 統計学の予測、フィルタリング、ベイズ推論は条件付き期待値の言葉で整理できる。
- 独立性は、条件付き期待値が通常の期待値へ戻る性質として現れる。

## よくある誤解

:::warning[注意：条件付き期待値は数ではない]
$\mathbb{E}[X\mid\mathcal{G}]$ は、一般には $\mathcal{G}$-可測な確率変数である。$\mathbb{E}[X\mid B]$ のような数値の条件付き平均とは区別する。
:::

:::warning[注意：一点ごとに一意ではない]
条件付き期待値は $P$-ほとんど確実に等しい範囲で一意である。零確率集合上の値は、定義だけでは決まらない。
:::

:::warning[注意：$\mathbb{E}[X\mid\mathcal{G}]$ は単なる $X$ の関数とは限らない]
$\mathcal{G}=\sigma(Z)$ の場合には $g(Z)$ と表せることがあるが、一般の部分 σ-代数では「ある観測変数の関数」として明示できるとは限らない。
:::

## この章の要点

- $\mathbb{E}[X\mid\mathcal{G}]$ は、$\mathcal{G}$-可測な確率変数である。
- 定義は $\int_G \mathbb{E}[X\mid\mathcal{G}]\,dP=\int_G X\,dP$ による。
- 存在は Radon-Nikodym 定理から従う。
- 一意性は $P$-ほとんど確実な意味で成り立つ。
- 塔性質は、情報を段階的に粗くする操作の整合性を表す。
- 独立な情報で条件づけると通常の期待値に戻る。
- $L^2$ では、条件付き期待値は部分情報で作れる最良の二乗平均予測である。

## 演習問題

1. ★ 有限分割 $C_1,\ldots,C_n$ が生成する $\mathcal{G}$ に対し、$\mathbb{E}[X\mid\mathcal{G}]$ が各 $C_i$ 上で定数になる理由を説明せよ。
2. ★ 公平なサイコロの出目を $X$ とする。$\mathcal{G}$ を「$X\le 3$ かどうか」を表す σ-代数とする。$\mathbb{E}[X\mid\mathcal{G}]$ を計算せよ。
3. ★ 公平なコインを三回投げる。$X$ を表の総数、$\mathcal{G}$ を第一投の結果が生成する σ-代数とする。$\mathbb{E}[X\mid\mathcal{G}]$ を計算せよ。
4. ★★ 定義から、$\mathbb{E}[\mathbb{E}[X\mid\mathcal{G}]]=\mathbb{E}[X]$ を示せ。
5. ★★ $X$ が $\mathcal{G}$-可測ならば $\mathbb{E}[X\mid\mathcal{G}]=X$ であることを、定義から示せ。
6. ★★ 線形性を、条件付き期待値の定義と一意性から証明せよ。
7. ★★ $\mathcal{H}\subset\mathcal{G}$ のとき、塔性質を簡単な有限分割の例で確認せよ。
8. ★★ $X\in L^1$ が $\mathcal{G}$ と独立ならば $\mathbb{E}[X\mid\mathcal{G}]=\mathbb{E}[X]$ であることを、$X=1_A$ の場合に証明せよ。
9. ★★★ $X\in L^2$ とする。$Y=\mathbb{E}[X\mid\mathcal{G}]$ が任意の有界な $\mathcal{G}$-可測 $Z$ に対して $\mathbb{E}[(X-Y)Z]=0$ を満たすことを示せ。
10. ★★★ 条件付き期待値が一点ごとに一意でないことを、零確率集合上で値を変える例によって説明せよ。
