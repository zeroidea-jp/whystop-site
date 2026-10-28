# whystop-site

whystop (無線・ネットワーク起因の「原因不明の停止」の出張診断) の公開サイトのソース。GitHub Pages で `https://whystop.zeroidea.co.jp/` に公開する。

- 生成: [Hugo](https://gohugo.io/) extended **0.167.0** (CI と同じ版。Blowfish v3.9.0 が対応を宣言している範囲 0.164〜0.167。`config/_default/hugo.toml` の `module.hugoVersion.min` 参照)
- テーマ: [Blowfish](https://github.com/nunocoracao/blowfish) v3.9.0 (`themes/blowfish`、git submodule)。トップは landing レイアウト。ヘッダーと冒頭は `layouts/partials/` で上書き
- ビルドと公開: `.github/workflows/hugo.yaml` (push to main → GitHub Actions → Pages)
- 外部 CDN・Web フォント・解析スクリプトは使わない

## ローカル確認

```bash
git clone --recurse-submodules git@github.com:zeroidea-jp/whystop-site.git site
cd site
hugo server          # http://localhost:1313/
```

## 編集する場所

| 何 | どこ |
|---|---|
| トップの文面 (冒頭、症状、何をするか、進め方、料金、問い合わせ) | `content/_index.md` (Markdown + Blowfish の shortcode) |
| 冒頭の見出し・リード・ボタン・図 | `content/_index.md` の front matter (`headline` / `heroLead` / `heroButtons` / `heroFigure`) |
| 事例 | `content/cases/*.md` (front matter の `symptom` / `cause` / `result` / `summary` がトップのカードと一覧に出る) |
| メニュー | `config/_default/menus.ja.toml` |
| 色・ヘッダー・フッターの設定 | `config/_default/params.toml` |
| 見た目の上書き | `assets/css/custom.css`、`layouts/partials/header/basic.html`、`layouts/partials/home/landing.html` |
| 図・ロゴ | `static/images/` |

## 権利

© 2026 株式会社ゼロアイデア (zeroidea)。サイトの文面・図・ロゴの無断転載・再利用はご遠慮ください。テーマ Blowfish は MIT ライセンス (`themes/blowfish/LICENSE`)。

## 書いてはいけないもの

顧客名・現場名・SSID/BSSID/IP/MAC・クレデンシャル・写真。事例は匿名化した技術的内容のみ。
