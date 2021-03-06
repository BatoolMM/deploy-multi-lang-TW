(rr-testing-smoketest)=
# スモークテスト

煙テスト(ビルド検証テストとも呼ばれます)は、基本的な機能だけでなく、いくつかの基本的な実装と環境上の前提を確保するために設計された特別な種類の初期チェックです。 煙テストは、通常、より完全なテストスイートを実行する前に、健全性チェックとして各テストサイクルの開始時に実行されます。

このタイプのテストの背後にあるアイデアは、実装中に大きな赤いフラグをキャッチするのを助け、さらなるテストが不可能であるか価値がないことを示す問題に注意を向けることです。 通常 テスターは、コンポーネントが明らかに壊れているか、ひどく壊れているかを尋ねているので、ビルドはテストする価値がない、または一部のコンポーネントは、壊れたビルドを示唆する明白な方法で壊れている、または新しいビルドの主な目的であるいくつかの重要な修正がうまくいかなかった。 煙のテストは非常に広範なものではありませんが、非常に迅速であるべきです。 プロジェクトへの変更により煙テストに失敗する場合 コアアサーションが破られたという早期のシグナルだ問題が解決するまで テストに時間を割くべきではない たとえば、プロジェクトの実行に必要なデータを読み込む関数が壊れている場合には、修正前にテストを行うことはできません。 失敗した煙テストの典型的な結果は、ビルド(ビルド停止のテスト)を拒否することであり、単なる新しいバグレポートではありません。
