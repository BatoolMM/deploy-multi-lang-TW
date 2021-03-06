(cl-github-novice-features)=
# もっとGitHubの機能を使う

リポジトリが設定されたので、より多くのものを追加し、その便利な機能を使用する準備ができました。

## フォルダ（ディレクトリ）、ファイル、コミットを追加する

* 「ファイルを追加」ボタンをクリックしてファイルをアップロードするか、新しいファイルを作成することで、リポジトリにさらにファイルを追加できます。
* 新しいファイルを作成したり、ファイルをアップロードするたびに、 {ref}`コミットメッセージ<rr-vcs-commit-messages>` を追加して、変更内容を覚えやすくする必要があります。
* git (および GitHub ) はフォルダ/ディレクトリを追跡しないので、空のフォルダを作成することはできません。


**新しいファイルを追加して新しいフォルダを作成します:**

* 「ファイルを追加」ボタンをクリックし、新しいファイルを作成します。
* これにより、空白のファイルを編集できます。
* ファイルに名前を付けるときは、最初にフォルダの名前(既存または新規)を入力し、次にスラッシュを入力します。 次にファイルの名前を付けます: "folder-name/file-name. xt".
* ファイルのコンテンツを編集します。
* "コミット"ボタンを使用して変更を保存します。 {ref}`コミットメッセージ<rr-vcs-commit-messages>` を入力してください。変更内容を覚えておくと便利です。

このファイルは、指定したフォルダに表示されます。 ランディングページにフォルダが表示されます。 青いフォルダシンボルをクリックすると、そのフォルダ内のファイルが表示されます。

## GitHubの「Insight」機能をご覧ください

* GitHub で、リポジトリのメインランディングページに移動します。
* リポジトリ名で「Insights」をクリックします。
* 左のサイドバーで、「コミュニティ」をクリックします。
  * ここでは、リポジトリに含める推奨ファイルがあります。 これらのファイルは、コミュニティ内の共同編集者やメンバーと作業する場合に特に便利です。
  * "License" ファイルは最も重要なものの一つです。なぜなら、リポジトリ内のマテリアルをどのように使用することができる(またはできない)かを他の人に伝えるからです。
  * コラボレーションについては、必ず「貢献」と「説明」を参照してください。
  * 可能な限り、「行動規範」を追加して、あなたのプロジェクトを他の人を歓迎し、包含するようにしましょう。
* 他の興味深い点は「貢献者」（プロジェクトに貢献する人）です 「トラフィック」（プロジェクトページにアクセスし、いつそれを行うか）と「コミット」（プロジェクトで行われたコミットのタイムラインと数）。

## GitHubの「プロジェクト」機能を探索する
GitHubのプロジェクトボードは、作業の整理と優先順位付けに役立ちます。 To-do、進行中、完了した列でタスクを追跡するためのかんばん機能です。 各項目は特定の課題やプルリクエストにリンクして、進捗状況を追跡することができます。 この機能は、他の人があなたのリポジトリに貢献したり、あなたが計画していることを知らせるのに役立つ素晴らしい方法です。


## GitHub 機能を使用してコラボレーションを促進する
これは、リポジトリがこれらの機能の多くを含めるように設定されている場合のように見えるものであり、歓迎された共同作業スペースになります。

```{figure} ../../figures/github-project.jpg
---
name: github-project
alt: 共同プロジェクト・リポジトリの注釈付きダイアグラム。 キャプションで説明します。
align: left
---
共同プロジェクト・リポジトリの注釈付きダイアグラム。
- 画像の左側のラベル:
  - **1. プロジェクト:** このリポジトリのプロジェクトボードを表示します。
  - **2. Issues:** このリポジトリで発生したすべてのタスク。
  - **3. ファイル:** リポジトリ内のすべてのファイルです。
  - **4. ランディングページまたは README.md ファイル:** あなたのREADME.md ファイルは自動的にあなたのサイトのランディングページとしてレンダリングされます。
- 画像の右側のラベル:
  - **5. Insights:** リポジトリで起きたすべてのアクティビティを表示します。 
  - **6. リポジトリの詳細を編集:** プロジェクトの簡単な説明を書いてラベルを追加できます。
  - **7. リポジトリの説明。**
  - **8. GitHub ページへのリンク:** このリポジトリによって生成されたウェブサイト。
  - **9. トピックラベル:** リポジトリに関連するトピックラベルは、他の人があなたのプロジェクトを見つけるのに役立ちます。
  - **10. ライセンス:** リポジトリに付けたライセンス。
```
