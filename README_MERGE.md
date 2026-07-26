# fork 元からのマージ方法

## マージ方法

```bash
# リモートリポジトリに fork 元を追加 *以下は @node-saml/node-saml が fork 元
git remote add upstream https://github.com/node-saml/node-saml

# 現在登録されている「リモートリポジトリ（GitHubやGitLabなど）の接続先URL」を一覧表示
git remote -v

# タグと変更内容を取得
git fetch upstream --tags

# タグのコミットをマージ（コミットさせない） *以下 'v5.1.0^0" は v5.1.0 のコミット内容を現在のブランチに取り込む（マージする）という意味
git merge 'v5.1.0^0' --no-commit

# コミット *以下 -m のオプションはコメント
git commit -m "v5.1.0の変更内容をマージ"

# 競合の解消とプッシュ *コンフリクトが発生した場合は手動で修正する必要がある
git push origin <branch-name>
```

## github の内容を npm i で取り込む方法

```bash
# npm インストール *以下は dogharrycatpotter/node-saml リポジトリの feature_dogharrycatpotter ブランチを取得
npm i "github:dogharrycatpotter/node-saml#feature_dogharrycatpotter"
```
