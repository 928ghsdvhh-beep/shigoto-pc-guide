# しごとPCくらべ

仕事用中古ノートの購入ガイド。静的HTML・CSS・JavaScriptで構成。

## Cloudflare Pages設定
- ブランチ: main
- フレームワーク: None
- ビルドコマンド: 空欄（生成済みファイルを配信）
- ビルド出力ディレクトリ: dist
- プロジェクト名: shigoto-pc-guide

## 更新
python3 build.py
SITE_URL環境変数で公開URLを変更可能。公開先が標準URLと異なる場合は設定し直して再生成する。

## 公開前後の確認
6記事・運営情報・お問い合わせ・プライバシー・広告方針・サイトマップを含む。
QualitのA8正規広告を設置。ads.jsonの提供コードは改変しない。トップ320×50、販売店比較300×250、予算・L13・電池記事はテキスト広告。
お問い合わせはこのリポジトリの公開Issues。個人情報を投稿しない旨を表示。
価格・在庫のライブ更新なし。実機検証なし。公開URL確定後canonicalとsitemapを照合する。
Cloudflare Web Analyticsを全コンテンツページと404に設置。トークンはbuild.pyのBEACONに保存。Search Consoleの確認ファイルはdist/googled51db09eaf8187a0.htmlに配置済み。

PC WRAPの300×250正規バナーを販売店比較ページに追加。ads.jsonのpcwrapは提供コードを改変せず保存。
