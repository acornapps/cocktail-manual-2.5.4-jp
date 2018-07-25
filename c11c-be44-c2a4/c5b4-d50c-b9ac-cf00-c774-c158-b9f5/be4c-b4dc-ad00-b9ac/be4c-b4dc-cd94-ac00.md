### 3.2.1 ビルド追加

---

ドッカーイメージのビルドタスクを追加する。 アプリケーションのダウンロード、アプリケーションビルド、イメージビルドの合計3つを選択することができる。

**a\) サービス → ビルド管理 → ビルド作成の編集を選択し、該当ページに移動**
![](/assets/EN/2.5/3.2.1_1.png)![](/assets/EN/2.5/3.2.1_2.png)

**b\) アプリケーションダウンロード、アプリケーションビルド、イメージビルドの内容を作成した上、作成ボタンを押してサーバーを作成**![](/assets/EN/2.5/3.2.1_3.png)

| **ビルド作成段階** | **説明** |
| :--- | :--- |
| アプリケーションダウンロード | ビルドに必要なソースをダウンロード |
| アプリケーションビルド | ソースのコンパイルが必要な場合に使用 <br/>**コマンド** - ビルドしながら実行するタスク <br/>**ホストパス** - タスクが行われるコンテナパスとマウントされるホストパス <br/>**Working dir** - 実際にコンテナ内で作業するパスで、 コンテナパスに合わせる <br/>**イメージ** - ビルド時に使用するイメージ |
| イメージビルド | 作業したソースでドッカーファイルを作ってイメージを作成し、該当イメージをレ
ジストリストレージに保存するステップ |

* **ビルドの基本情報**
![](/assets/EN/2.5/3.2.1_4.png)

| **基本情報** | **説明** |
| :--- | :--- |
| ビルド名 | 作成するビルドの名前 |
| 最近のアクション | ビルドの最近の動作状態 |
| ステータス | ビルドの現在の状態 |

* **アプリケーションのダウンロード**
![](/assets/EN/2.5/3.2.1_5.png)

| **アプリケーションのダウンロード** | **説明** |
| :--- | :--- |
| リポジトリ | ソースファイルをダウンロードするバージョン管理ツールの種類。 現在のバージョンでは、 Gitのみサポート |
| プロトコル | リポジトリが提供するHTTP / HTTPSプロトコルをサポート |
| Gitリポジトリタイプ | Private/Common をサポート |
| リポジトリ URL | ダウンロードするためのストレージ URL |
| リポジトリ User ID | ストレージの権限を有するID |
| リポジトリのパスワード | ストレージの権限を有するIDのパスワード |
| ターゲットブランチ(Branch) | ダウンロードするソースのブランチ情報 |

* **Application Build**
![](/assets/EN/2.5/3.2.1_6.png)

| **Application Build** | **Description** |
| :--- | :--- |
| Command | Command to be executed during build |
| Host Path | Path of downloaded source |
| Container Path | The container path where the operation is to take place |
| Working Dir | Actual path to work within the container. Matched with container path |
| Image | Container image for build |

* **Image Build**
![](/assets/EN/2.5/3.2.1_7.png)

| **Image Build** | Description |
| :--- | :--- |
| Dockerfile | Docker file for image creation |
| Registry Name | Registry where the created image is to be stored |
| Image | Name and tag of image to be stored in the registry |



