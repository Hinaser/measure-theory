# measure-theory

Docusaurus 上で『厳密な確率論のための測度論入門』を公開するための教材リポジトリです。

## 含まれるもの

- `AGENTS.md`：全サブエージェント共通の執筆規約。
- `docs/rigorous-probability/toc.md`：Docusaurus docs に置ける目次ページ。
- `instructions/`：並行執筆用の担当別インストラクション。
- `docusaurus.config.ts`：GitHub Pages 向け Docusaurus 設定。
- `.github/workflows/deploy.yml`：main ブランチへの push で GitHub Pages に自動デプロイする workflow。

## Install

```bash
npm install
```

## Local Development

```bash
npm run start
```

## Build

```bash
npm run build
```

静的サイトは `build/` に生成されます。

## Deployment

GitHub Actions で GitHub Pages にデプロイします。

GitHub 側で次を設定してください。

```text
Settings -> Pages -> Build and deployment -> Source: GitHub Actions
```

公開 URL は次を想定しています。

```text
https://hinaser.github.io/measure-theory/
```

## 執筆ワークフロー

1. `docs/rigorous-probability/toc.md` を Docusaurus の `docs/` 配下に置く。
2. `AGENTS.md` をリポジトリルートに置く。
3. `instructions/*.md` を各サブエージェントに渡す。
4. 各サブエージェントは `AGENTS.md` と担当 instruction を読んで、指定された章ファイルを作成する。
5. 最終統合作業者がリンク、章番号、front matter、用語統一、演習番号を確認する。

## 推奨並行執筆 wave

- Wave 1: `01-preface-foundations.md`, `02-sigma-measure-lebesgue.md`, `03-measurable-functions-integration.md`
- Wave 2: `04-lp-probability-random-variables.md`, `05-distributions-expectation.md`, `06-product-independence-radon-nikodym.md`
- Wave 3: `07-convergence-limit-theorems.md`, `08-conditioning-martingales.md`, `09-advanced-applications.md`, `10-appendices-solutions.md`
