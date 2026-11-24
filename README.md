# QR Scanner 公式紹介サイト

無料・登録不要のオンラインQRコードリーダー「QR Scanner」の機能、使い方、プライバシー、FAQ、開発背景を紹介する日本語の静的サイトです。

- アプリ本体：<https://qr-scanner-green-pi.vercel.app/>
- 紹介サイトの公開先：<https://mondhi1120.github.io/qr-scanner-intro/>

## 構成

HTML・CSSだけで動作します。React、npm、ビルド、JavaScriptの実行は不要です。FAQはHTMLの`details` / `summary`を使用しています。外部フォント・解析タグ・外部ライブラリを読み込みません。

| ファイル | 内容 |
| --- | --- |
| [index.html](index.html) | 紹介ページ、meta情報、OGP、JSON-LD構造化データ |
| [style.css](style.css) | 緑色基調のデザイン、PC・スマートフォン対応 |
| [assets/](assets/) | アプリアイコン、アプリ画面、OGP画像 |
| [robots.txt](robots.txt) | クロール案内、サイトマップURL |
| [sitemap.xml](sitemap.xml) | 紹介サイトの正規URL |
| [docs/implementation_status.md](docs/implementation_status.md) | 実装内容、確認結果、制約 |

## ローカルで開く

[index.html](index.html)をダブルクリックして、ブラウザで開いてください。インストールやコマンド実行は不要です。UI用SVGもHTML内に埋め込み、ローカルファイルのまま表示できます。

公開時と同じHTTP配信で確認したい場合は、既存の静的HTTPサーバーやVS CodeのLive Serverも利用できます（任意）。

1. VS Codeでこのリポジトリを開く。
2. Live Serverがある場合は、[index.html](index.html)を右クリックして「Open with Live Server」を選ぶ。
3. ブラウザに表示されたローカルURLを開く。停止はVS Codeの「Port」表示から行う。

紹介ページ内の「QR Scannerを使う」は、公開中のアプリ本体に移動します。この紹介サイト自体はQR読み取りやカメラ利用を行いません。

## GitHub Pagesで公開する

ユーザーが変更を確認してPushしたあと、GitHubのリポジトリ設定で次を指定します。

1. **Settings → Pages → Build and deployment**を開く。
2. Sourceを**Deploy from a branch**にする。
3. 公開するブランチ（例：`main`）と**`/ (root)`**を選び、Saveする。
4. 配信完了後、紹介サイトの公開先を開いて確認する。

ビルドコマンドや環境変数の設定は不要です。CSS・画像は`./`からの相対パスを使用し、UI用SVGはHTMLに埋め込んでいるため、`/qr-scanner-intro/`配下で配信できます。紹介サイトのオフライン配信やホーム画面へのインストールは提供していません。紹介しているPWA機能はアプリ本体のものです。

## SEOと公開後の確認

- title、description、canonical、OGP、favicon、JSON-LD（WebSite・WebPage・WebApplication）を設定しています。
- 紹介ページのcanonicalは紹介サイト自身、WebApplicationのURLはアプリ本体です。
- 本文は静的HTMLにあり、JavaScriptを無効にしても読めます。
- OGP画像はローカルの1200×630 PNGです。評価・レビュー・未確認の対応バージョン等は構造化データに含めていません。
- 公開後はCSS・画像・アプリへのリンク、OGP画像URL、[sitemap.xml](sitemap.xml)の配信を再確認してください。
- Google Search Consoleを使う場合は、紹介サイトURLのプロパティを追加・所有権確認し、サイトマップを送信します。所有権確認やインデックス登録、順位は本実装だけでは完了・保証されません。

### robots.txtの制約

クローラーが参照するrobots.txtはホスト直下の`https://mondhi1120.github.io/robots.txt`です。このリポジトリの[robots.txt](robots.txt)は`/qr-scanner-intro/robots.txt`に配信されるため、ホスト全体のクロール規則にはなりません。ホスト直下のrobots.txtを管理している場合は、そちらへ本サイトのSitemap行を追加してください。この紹介サイトのサイトマップURLはSearch Consoleへ直接送信できます。

## 仕様と画像の更新

掲載内容はユーザー指定の機能一覧、アプリ本体の公開ページ、隣接するアプリ本体リポジトリのREADME・実装を照合しています。端末やブラウザごとの動作を一律には保証していません。アプリの仕様が変わった場合は本文・FAQ・構造化データをまとめて更新してください。

[assets/app-screen.png](assets/app-screen.png)はアプリ本体の本番ビルドから取得したライトモードの画面です。カメラ起動前の状態を掲載しています。アイコンは同じアプリ本体のロゴを使用しています。[assets/og-image.png](assets/og-image.png)はこの紹介サイト向けに制作した共有画像です。

実装・検証の詳細は[実装状況](docs/implementation_status.md)をご覧ください。本作業ではGitHubへのPush・公開設定変更・デプロイを行いません。
