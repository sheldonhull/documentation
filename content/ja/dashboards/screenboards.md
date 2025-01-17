---
title: スクリーンボード
kind: documentation
aliases:
  - /ja/graphing/dashboards/screenboards/
  - /ja/graphing/dashboards/screenboard/
  - /ja/dashboards/screenboard/
  - /ja/screenboards/
  - /ja/screenboard/
further_reading:
  - link: /dashboards/template_variables/
    tag: ドキュメント
    text: テンプレート変数を使用してダッシュボードの機能を強化
  - link: /dashboards/sharing/
    tag: ドキュメント
    text: Datadog以外とグラフを共有
  - link: /dashboards/widgets/
    tag: ドキュメント
    text: すべてのウィジェットをダッシュボードで体験できます
---
スクリーンボードは自由形式のレイアウトのダッシュボードで、画像やグラフ、ログなど、様々なオブジェクトを含めることができます。リアルタイムに更新されたり、過去の定点を示すステータスボードやストーリーテリングビューとして使われるのが一般的です。

## グローバルタイムセレクター

スクリーンボードグローバルタイムセレクターを使うには、1 つ以上の時間ベースのウィジェットが `Global Time` を使うように設定されている必要があります。**Set display preferences** でウィジェットのエディターで選択するか、またはウィジェットを追加します (グローバルタイムはデフォルトの時間設定です)。

グローバルタイムセレクターは、同一のスクリーンボード上で `Global Time` オプションを使用するすべてのウィジェットに対して同一のタイムフレームを設定します。過去の移動ウィンドウ (`Past 1 Hour`、`Past 1 Day` など) を選択することも、固定期間を選択することもできます。固定期間は、`Select from calendar…` オプションを使用するか、[カスタムタイムフレームを設定][1]して選択できます。移動ウィンドウを選択した場合、ウィジェットはタイムウィンドウに沿って移動します。

グローバルタイムにリンクされていないウィジェットは、グローバルウィンドウに適用されたローカルタイムフレームに対応するデータを表示します。たとえば、グローバルタイムセレクターが 2019 年 1 月 1 日から 2019 年 1 月 2 日に設定されている場合、ローカルタイムフレームが `Past 1 Minute` に設定されているウィジェットには、2019 年 1 月 2 日の午後 11 時 59 分からの最後の 1 分が表示されます。

## TV モード

スクリーンボードは大画面や TV に主要パフォーマンスメトリクスを表示する場合に役立ちます。TV モードを有効にするには、キーボードショートカット `F` を使うか、スクリーンボードの TV アイコンをクリックします。

## 設定

### パブリック URL を生成

パブリック URL を生成することでスクリーンボードを外部ユーザーと共有します。詳しくは、[スクリーンボードの共有][2]を参照してください。

### UTC 時間を表示

UTC 時間とデフォルトのタイムゾーンを切り替えます。

### 通知

スクリーンボードで通知が有効になると、[イベントストリーム][3]でイベントが作成されます。このイベントでは、テキストの変更、ウィジェットの変更、スクリーンボードの複製、スクリーンボードの削除に関する情報が、アクションを実行したユーザーの名前とともに表示されます。

また、通知を有効にした個々のユーザーにはメールアラートが送信されます。管理権限の有無にかかわらず、組織内のすべてのユーザーは、登録すればスクリーンボードの変更通知を受信することができます。

通知が有効になっているダッシュボードの変更イベントは、検索することでイベントストリームで確認できます:

```text
tags:audit,dash
```

検索を特定のダッシュボードに制限するには、検索にダッシュボードの名前を含めます。

### アクセス許可

スクリーンボードでは、作成者または[管理者][4]は読み取り専用モードを有効にできます。この場合、非管理者によるスクリーンボードの編集はすべて無効になります。

読み取り専用モードでも、非管理ユーザーがスクリーンボードの複製、タイルの再配置、タイルのスナップショット、タイルの全画面表示を行うことは可能です。ただし、非管理ユーザーによるタイルの再配置は永続化されません。

### ダッシュボードを複製

このオプションを使うと、スクリーンボード全体を新しいスクリーンボードにコピーできます。このとき、複製に名前を付けるよう求められます。

### ダッシュボード JSON をコピー、インポート、エクスポート

ダッシュボード JSON のコピー、インポート、エクスポートについて詳しくは、[メインダッシュボードドキュメント][5]を参照してください。

### ダッシュボードを削除

このオプションを使うと、スクリーンボードを完全に削除できます。このとき、削除の確認を求められます。

## グラフメニュー

スクリーンボードグラフをクリックするとオプションメニューが開きます。

| オプション                 | 説明                                                   |
|------------------------|---------------------------------------------------------------|
| View in full screen    | グラフを[全画面モード][6]で表示します。                     |
| View related processes | グラフ参照範囲の[ライブプロセス][7]ページへジャンプします。   |
| View related hosts     | グラフ参照範囲の[ホストマップ][8]ページへジャンプします。         |
| View related logs      | グラフ参照範囲の[ログ][9]パネルに入力します。             |
| 関連トレースを表示    | グラフ参照範囲の[トレース][10]パネルに入力します。          |
| 関連プロファイルを表示  | グラフ参照範囲の[プロファイリング][11]ページへジャンプします。       |

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: /ja/dashboards/guide/custom_time_frames/
[2]: /ja/dashboards/sharing/#dashboards
[3]: /ja/events/
[4]: /ja/account_management/users/default_roles/
[5]: /ja/dashboards/#copy-import-export
[6]: /ja/dashboards/widgets/#full-screen
[7]: https://app.datadoghq.com/process
[8]: https://app.datadoghq.com/infrastructure/map
[9]: /ja/logs/
[10]: /ja/tracing/
[11]: /ja/tracing/profiler/