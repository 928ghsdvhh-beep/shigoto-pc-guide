# 画像・記事入口の改善（2026年11月17日）

仕事PC：トップの大きなSVG概念図を、写実的なAI生成画像へ置換。幅は最大420px、スマホ320px。記事一覧の小さな左アイコン・右見出しの既存配置は継承。

## 画像

built-in imagegenで生成した900×600pxのWebP。AI生成のイメージと明示し、掲載商品の実写真や実測の根拠として扱わない。元生成は1536×1024px。無断の商品写真転用なし。

生成プロンプト：photorealistic natural unbranded charcoal business notebook on clean light wood desk beside plain checklist and pen, soft daylight, no people/logos/readable text, generic lifestyle setting, not a specific listing or product model.

## 検証

静的監査 issues 0。内部リンク・canonical・sitemap・JSON-LDを検証。全既存公開HTMLのA8アンカー・計測画像とCloudflare解析scriptを変更前と完全照合し一致。git diff --check成功。再ビルド差分0。画像のsource/dist一致。画像寸法属性で表示領域を確保。広告素材の寸法・コードは維持。公開版とブラウザの狭幅確認は別途実施。
