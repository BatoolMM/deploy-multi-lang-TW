(pd-概要-version)=
# バージョン管理とドキュメント

プロジェクトが設計されたら、すべての変更を追跡することが重要です。 これはあなたに多くの時間を節約し、他の人があなたの研究を理解し、再利用するのを助けることができます - あなたは理由を理解するために最もよく働いたものと情報の記録を持っています。

(pd-overview-version-experiments)=
## 実験的な仕事

実験的な作業についての詳細を書き留める必要があります。 これにより、将来の読者、同僚、そして将来の自分がプロジェクトに関連するすべての実験的な作業を理解し、再現することができます。

これを行うのに便利なツールは {ref}`Electronic Lab Notebooks<rr-open-notebooks>` (ELN) です。 ELNは、検索性、セキュアストレージ、リモートアクセスの利点を備えた紙ノートブックのデジタル版です。 また、チームメンバーやコラボレーターの間で簡単に共有できます。

使用される方法論、分析および手順、およびデータ固有の情報を文書化し、共有することが重要です。

(pd-overview-version-comp)=
## 計算作業

プロジェクトのアクティブなフェーズでは、コード内の一貫性を保つことが重要です ( {ref}`コード品質<rr-code-quality>`の章を読んでください)。 そのためのテストを文書化したり作成したりしています

あなたのコードを文書化することは、他の人があなたの作業を理解するのに役立ちます。 コードをより簡単に文書化できるツールは次のとおりです。
- RまたはPythonの"Docstring"
- Javaの「Javadoc」形式
- 統合されたソフトウェア開発(RStudio、Eclipse、VS Code)は、コメントの書き込みプロセスとドキュメントの生成を容易にします。

テストを作成することは時間とお金を節約するのに役立ちます。 コードが動作するかどうかを知る方法を提供することで、ミスはあなたや他の人によって簡単に対処することができます。

コードテストの詳細については、 {ref}`コードテストの章<rr-testing>` を参照してください。

(pd-overview-version-vcs)=
## バージョン管理

研究中に行われたすべての変更を記録することは再現性のある研究の主な部分です。 それはあなたと他の人が行われた決定を理解し、作業を再現可能にするのに役立ちます - あなたは取られた手順に関するすべての情報を持つことになります。

コラボレーションプロジェクトに取り組む場合、これは各変更を実行した人を追跡するのにも役立ちます。

追加の利点は、すべてがきちんと整理されることです あなたのプロジェクトの現在のバージョンと過去の変更を探す方法に簡単にアクセスできます。

バージョンを制御するためのいくつかのシステムは次のとおりです。
- Git
- Mercurial
- Subversion

この段階で役立つ可能性のある再現研究ガイドには、 {ref}`バージョン管理システム<rr-vcs>` に関する広範な章があります。