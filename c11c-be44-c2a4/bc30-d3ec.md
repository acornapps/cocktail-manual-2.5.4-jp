### 3.1.5 パイプライン

---

パイプライン機能でイメージビルドタスクからサーバーデプロイタスクまで一度に進めることができる。

また、デプロイ中のサーバーのイメージバージョンを変更して再デプロイすることができる。

##### a\) サービス → アプリケーションマップ選択 → パイプラインをクリック。 ![](/assets/JP/2.5/3.1.5_1.png)![](/assets/JP/2.5/3.1.5_2.png)

| **パイプラインメニュー ** | **説明 ** |
| :---: | :--- |
| バッチ実行 | パイプラインのタスクを一括して実行 |
| 実行 | 該当パイプラインのタスクを実行 |

| **イメージメニュー** | **ビルド** | **説明 ** |
| :---: | :--- | :--- |
| イメージタグ | X | レジストリにあるタグ入力時、該当バージョンでサーバーをデプロイ |
| 指定 | ⃝ | イメージバージョン中の指定されたバージョンでサーバーをデプロイ |
| 最新 | ⃝ | イメージバージョン中の最新バージョンでサーバーをデプロイ |
| ビルド＆デプロイ | ⃝ | 新たなビルドタスク後、該当イメージバージョンでサーバーをデプロイ |

##### b\) パイプライン実行

##### **1. パブリックイメージでサーバーを作成した場合**

イメージタグを入力後、「実行」または「バッチ実行」をクリック （deployしたバージョンと入力しバージョンが異なる場合のみ実行可能。ただし、latestを除く） ![](/assets/JP/2.5/3.1.5_3.png)

##### **2. ビルドしたイメージでサーバーを作成した場合**

* **指定したイメージでデプロイ**

パイプラインタスクリストの右側で「指定」およびイメージを選択した後、 「実行」 または「バッチ実行」をクリック（deployされたバージョンと入力したバージョンが異なる場合のみ実行可能）![](/assets/JP/2.5/3.1.5_4.png)

* **新たなビルドタスク後、該当イメージでデプロイ**

パイプラインタスクリストの右側で「ビルド＆デプロイ」を選択した後「実行可否」をチェック。その後、「実行」または「バッチ実行」をクリック（実行可否がチェックされている場合のみ実行可能） ![](/assets/JP/2.5/3.1.5_5.png)

* **最新のイメージでデプロイ**

パイプラインタスクリストの右側で「最新」を選択した後、「実行」または「バッチ実行」をクリック（deployされたバージョンと入力したバージョンが異なる場合のみ実行可能） ![](/assets/JP/2.5/3.1.5_6.png)

* **ビルド編集画面の移動およびログ表示**

ビルドイメージ名をクリックすると、ビルド編集画面に移動する。![](/assets/JP/2.5/3.1.5_7.png)

ビルドタグ名をクリックすると、ログを表示することができる。![](/assets/JP/2.5/3.1.5_8.png)![](/assets/JP/2.5/3.1.5_9.png)

