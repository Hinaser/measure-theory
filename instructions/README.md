# 執筆インストラクション一覧

各ファイルを 1 人のサブエージェントに渡して、担当範囲を並行執筆させる。

## 共通ファイル

- `../AGENTS.md`：全エージェント共通の執筆ルール。
- `../docs/rigorous-probability/toc.md`：全体目次。章タイトル・節タイトル・推奨ファイル名はこれに合わせる。

## 担当分割

1. `01-preface-foundations.md`  
   第1章〜第2章。素朴な確率論の限界、集合・写像・実数の復習。

2. `02-sigma-measure-lebesgue.md`  
   第3章〜第5章。σ-代数、測度、外測度、ルベーグ測度。

3. `03-measurable-functions-integration.md`  
   第6章〜第8章。可測関数、非負関数の積分、一般のルベーグ積分。

4. `04-lp-probability-random-variables.md`  
   第9章〜第11章。$L^p$ 空間、確率空間、確率変数。

5. `05-distributions-expectation.md`  
   第12章〜第13章。分布を測度として扱う見方、期待値と基本不等式。

6. `06-product-independence-radon-nikodym.md`  
   第14章〜第16章。積測度、Fubini、独立性、Radon-Nikodym定理。

7. `07-convergence-limit-theorems.md`  
   第17章〜第20章。確率変数列の収束、大数の法則、特性関数、中心極限定理。

8. `08-conditioning-martingales.md`  
   第21章〜第23章。条件付き確率、条件付き期待値、マルチンゲール入門。

9. `09-advanced-applications.md`  
   第24章〜第27章。確率過程、弱収束、情報理論、暗号理論への接続。

10. `10-appendices-solutions.md`  
    付録A〜E。集合論、位相、解析、不等式、演習問題のヒントと解答。

## 並行執筆の推奨順序

完全な依存関係を待たずに並行執筆してよい。ただし、後続章のエージェントは未確定定義への参照に TODO コメントを残す。

- Wave 1: 01, 02, 03
- Wave 2: 04, 05, 06
- Wave 3: 07, 08, 09, 10

## 最終統合時の必須確認

- `toc.md` の章・節と各章本文が一致しているか。
- front matter の `sidebar_position` が重複・欠落していないか。
- 章間リンクが壊れていないか。
- 用語が統一されているか。
- 演習番号と付録Eの解答番号が対応しているか。
