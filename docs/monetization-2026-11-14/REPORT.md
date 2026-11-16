# shigoto-pc-guide 収益化改善報告（2026年11月14日）

## 2026年11月16日 横断確認追補

確認対象main：`6aba15d5ce7f375bdbb323eb6819312cb7fc2902`。11月14日の改善PR #1 はマージ済み。本番公開の成否はマージから推定せず未確認とします。以下の旧本文にある「未マージ・未公開」は作業当時の記録です。

A8アンカー12件を確認。広告コード保持。個体在庫・構成・保証、提携・掲載URL・成果条件は管理画面との照合が必要。

優先確認：1. Cloudflare配信コミット・出力先と公開HTML/robots/sitemap/404の照合。2. 商品一致・広告管理画面の有効条件。3. Search Console取得・除外理由と広告クリック記録の比較。GitHub上の静的検証は公開応答や成果計測の保証ではありません。


作業ブランチ：`improve/monetization-2026-11-14`。以下は2026年11月14日の作業時点の記録です。現在の状態は冒頭の追補を参照。
既存サイトの修正です。公開中のデザイン、広告コード、Tracking ID、解析IDを保持。順位・AIO引用・成果発生は検証できていません。

## 優先問題と変更

販売店比較・5万円予算記事を充実。構成・状態・総額・保証を同じ条件で比較する表を追加。7記事のスマホ横はみ出しを修正し、404にnoindexと正しいhead/bodyを設定。

Qualit・PC WRAPの既存正規広告とads.jsonを保持。本文の比較から既存の販売一覧広告へ進む構成を維持。全生成ファイルの再現性を確認。

## 本文を充実した既存記事

文字数はHTMLからscript/styleと空白を除いた概算で、評価指標ではありません。文字数のための水増しはしていません。

| 記事（公開ディレクトリからの相対パス） | 本文概算・改善前 → 改善後 |
| --- | --- |
| `budget-50000/index.html` | 1931 → 2324 |
| `shop-comparison/index.html` | 1701 → 2235 |

パンくずを追加した記事は、その表示内容に合うBreadcrumbListを設定。既存のArticleとcanonicalは照合済みです。架空のReview・AggregateRating・Offerは新設していません。購入者レビュー10本文以上を個別確認できた商品は0件で、レビュー要約は追加していません。価格・仕様の古い確認日を一律に新しくしていません。

比較・判断の補足は既存の広告より前に配置し、説明を読んでから購入先へ進める順序にしています。配置変更後も全ページの静的検証と3画面幅の検証を再実行し、エラー0でした。

## 検証結果

- 静的検証：13ページ（404含む）、エラー0。タイトル・description・h1、canonical、サイトマップ、内部リンク・アンカー・参照資産、JSON-LD、重複タイトル・canonical、トップからの到達性を点検。
- サイトマップ：12URL。noindexとの整合を検証。robots.txtは既存のクロール許可と本番Sitemap指定を維持。
- ブラウザ：360・390・1440pxの39ケース。ページ横はみ出し0。外部広告・解析への通信は遮断。画像の実配信や計測通信の成功を意味しません。
- 改善前の横はみ出し：14ケース → 改善後0ケース。
- 広告保全：リンク・広告画像のHTML断片24個をSHA-256照合、一致。`scripts/affiliate-baseline.json`が修正前の基準です。既存Tracking ID：実リンクなし。
- 外部参照先：11URLをHTTP GETで点検。未確認・差し替え前404を含む応答記録は`external-links.json`参照。403/503はリンク切れと断定しません。
- 公開状態：本番の既存ページ・robots・sitemapは200、無効URLは404。ブランチの改善は本番未反映です。
- 表示速度：メダカでは外部画像6リクエストを除去。他サイトを含む本番CWV・Lighthouse・実ユーザーLCP/INP/CLSは未測定。高速化の数値効果は主張しません。

生成サイトはビルド成功、2回目のビルドによる配信ファイル差分0。

既存ツールの動作確認：関心別の記事案内。すべて成功。

## 未確認事項・公開前の判断

A8の実際の提携承認、掲載URL登録、現在の在庫と成果承認は管理画面で未確認。Microsoft・Dellの参照先は403のため仕様再確認に制約があります。販売一覧のリンクを個別のL13・5310在庫があるという表現に変更していません。

共通：Amazonの商品ページの現在の表示・レビュー本文10件、A8管理画面の提携・成果対象・掲載URL、Search Consoleのクエリ別表示回数・CTR・順位、Cloudflare実測速度、実際の成果計測は未確認。広告をテスト購入・申込する検証は行っていません。既存の商品画像は、A8バナー・イメージ・メーカー参照を区別。新しい未許諾写真を追加していません。

## 全ページの診断台帳

`page-audit.json`にtitle/h1/description/canonical・index可否・サイズ・リンク数・構造化データ・到達性を保存。全ページに一律のタイトル変更はせず、検索意図が重なる販売年違いを区別し、問題のある記事とUIを優先しました。トップから到達できないindex許可ページ・内部リンク切れ・完全なタイトル重複は検証後0件。記事の統合・削除はしていません。

| ページ | 検索設定 | 本文概算 | 内部リンク先数 | 広告リンク・画像数 | 構造化データ |
| --- | --- | ---: | ---: | ---: | --- |
| `index.html` | index許可 | 1365 | 12 | 3 | WebPage |
| `404.html` | noindex | 59 | 1 | 0 |  |
| `budget-50000/index.html` | index許可 | 2324 | 12 | 4 | Article |
| `battery-warranty/index.html` | index許可 | 1666 | 12 | 2 | Article |
| `thinkpad-l13-vs-latitude-5310/index.html` | index許可 | 2565 | 12 | 4 | Article |
| `privacy/index.html` | index許可 | 849 | 6 | 0 | WebPage |
| `memory-8gb-16gb/index.html` | index許可 | 1687 | 12 | 2 | Article |
| `advertising/index.html` | index許可 | 629 | 6 | 0 | WebPage |
| `shop-comparison/index.html` | index許可 | 2235 | 12 | 8 | Article |
| `latitude-5310/index.html` | index許可 | 1729 | 12 | 2 | Article |
| `thinkpad-l13/index.html` | index許可 | 1689 | 12 | 2 | Article |
| `contact/index.html` | index許可 | 501 | 6 | 0 | WebPage |
| `about/index.html` | index許可 | 603 | 6 | 0 | WebPage |

## 再実行・差分の確認

- `python scripts/check_site.py .`（Python標準ライブラリのみ）
- 全差分：`git diff main...improve/monetization-2026-11-14`
- 本番へのマージ・デプロイは別途承認後。プレビュー環境が自動生成されても本番とは区別。
- 公開後はcanonical・サイトマップの実応答、Search Consoleの除外理由、記事→広告クリック→成果を確認。変更前後で同じ期間・クエリを比較してください。
