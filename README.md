# tsunagi-site

個人用ツール tsunagi のホームページとプライバシーポリシーを GitHub Pages で配信するためのリポジトリ。

- ホームページ: https://oekazuma.github.io/tsunagi-site/
- プライバシーポリシー: https://oekazuma.github.io/tsunagi-site/privacy.html

## 何のためにあるか

tsunagi は YouTube Data API を使うので、Google の OAuth 同意画面にホームページとプライバシーポリシーの URL を登録する必要がある。この 2 ページはその登録先になっている。

そのため、次の点に注意する。

- リポジトリを非公開にしたり、ページを消したり、URL を変えたりしない。同意画面の設定が無効になり、tsunagi から YouTube にアップロードできなくなるおそれがある
- URL を変える場合は、先に Google Cloud コンソールの「ブランディング」で新しい URL と承認済みドメインを登録する
- tsunagi が扱う情報の範囲を変えたとき(API のスコープを増やしたときなど)は、`privacy.html` の記述と最終更新日も合わせて直す

## 構成

| ファイル | 内容 |
|---|---|
| `index.html` | ホームページ |
| `privacy.html` | プライバシーポリシー |
| `.nojekyll` | Jekyll の変換を止め、ファイルをそのまま配信する |

ビルドは無い。`main` ブランチのルートがそのまま配信される。

両ページとも `noindex, nofollow, noarchive` を指定していて、検索結果には載せない。`robots.txt` で巡回を拒否すると、クローラーがこの指定を読めなくなるので置いていない。
