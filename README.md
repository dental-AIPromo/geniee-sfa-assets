# geniee-sfa-assets

GENIEE SFAなどから参照する、公開可能な画像・静的アセットを管理するリポジトリです。

## GitHub Pages

公開URL:

<https://dental-aipromo.github.io/geniee-sfa-assets/>

`main` ブランチへCommit / Pushすると、GitHub Actionsが起動し、GitHub Pagesへ自動Deployします。

Pagesへ公開するのは、Workflowで明示的にコピーした `index.html` と `images/` のみです。READMEやWorkflowなどの管理用ファイルは公開artifactに含めません。

## 画像の追加方法

1. `images/` 以下に、公開して問題のない画像を追加します。
2. GitHub DesktopなどでCommitします。
3. `main` ブランチへPushします。
4. GitHub Actionsの完了後、公開URLから参照します。

例:

Repository上のファイル:

```text
images/geniee/logo.png
```

公開URL:

```text
https://dental-aipromo.github.io/geniee-sfa-assets/images/geniee/logo.png
```

ファイルパスの大文字・小文字を含めて、Repository上のパスをそのままURLに使用します。

## 公開対象の注意

GitHub Pagesに配置したファイルは、インターネットからアクセス可能な公開情報です。以下は配置しないでください。

- 個人情報、医療情報、患者情報
- 認証情報、API Key、Token、Password
- 社外秘資料
- その他、インターネット公開できない情報

## GitHub Pages設定

Repository Settings の **Pages** で、公開元を **GitHub Actions** に設定してください。初回のWorkflow実行時に `github-pages` Environmentが作成される場合があります。Environmentの保護ルールが必要な場合は、Repository管理者が設定してください。

`github-pages` Environmentでは、デプロイ対象ブランチを `main` に限定する保護ルールを設定してください。Workflowの手動実行も `main` 以外ではDeployされないようにしています。

対象Repository:

<https://github.com/dental-AIPromo/geniee-sfa-assets>
