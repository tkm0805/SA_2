# システムアーキテクト 午後Ⅱ 過去問レビュー（GitHub Pages公開用）

2015〜2019・2021〜2025年度の過去問原文画像、実務を基にした回答ドラフト、根拠解説を閲覧する静的サイトです。

## 公開手順（GitHubサイト上で操作）

1. GitHubで新しい **Public** リポジトリ（例: `sa-gogo2-study`）を作成する。
2. このZIPを**解凍**し、中身の `index.html`、`sources` フォルダ、`.nojekyll`、`README.md` をリポジトリの最上位（ルート）に追加してコミットする。ZIPファイルそのものをアップロードするのではありません。
3. リポジトリの **Settings → Pages** を開く。
4. **Build and deployment → Source: Deploy from a branch** を選択し、**Branch: main / (root)** にして **Save** を押す。
5. 公開後、通常 `https://<GitHubのユーザー名>.github.io/<リポジトリ名>/` にアクセスする。設定ページ内の **Visit site** からも確認できます。

※GitHub無料プランでは公開（Public）リポジトリでGitHub Pagesを利用できます。

## ファイル構成

```text
index.html          サイト本体（問題画像・回答案データを内蔵）
.nojekyll           GitHub PagesでJekyll処理を行わないためのファイル
sources/
  2025_questions.pdf
  2025_examples.pdf
  2025_commentary.pdf
  ... 各年度の原本PDF
README.md           この説明書
```

`index.html` は単独でも問題文画像・回答案・解説の表示に対応していますが、解説画面内の原本PDFへのリンクを機能させるには `sources/` フォルダが必要です。

## 注意事項

- **公開前に必ず内容を確認してください。** サイトの論述案には実務案件の情報（顧客業務、システム構成、業務上の規模等）が含まれています。所属組織・顧客との秘密保持や公開ルールに照らして問題がないか確認し、必要に応じて匿名化・削除してください。
- GitHub Pagesのページは、URLを知る人だけに限定した安全な非公開ページではありません。公開リポジトリのファイルは誰でも閲覧・取得できます。
- 「論文回答案の編集内容」「復習済み状態」「メモ」はアクセスしている**ブラウザのlocalStorage**に保存されます。GitHubへの同期や複数端末での同期はありません。ブラウザデータを消去すると消える場合があります。
- 問題文は原本PDFのページ画像を埋め込んでいます。画面表示はできますが、画像内の文字のコピー・全文検索には対応していません。
- 原本PDFの利用・再配布についてもIPAの利用条件を事前に確認してください。

## Gitコマンドでアップロードする場合（任意）

```sh
git init
git branch -M main
git add index.html .nojekyll README.md sources/
git commit -m "Publish SA afternoon II study site"
git remote add origin https://github.com/<GitHubのユーザー名>/<リポジトリ名>.git
git push -u origin main
```
