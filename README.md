## 開発環境構築
### 前提
- 以下をインストールしておくこと。
  - [Docker for Mac](https://docs.docker.com/desktop/install/mac-install/)
  - [VSCode](https://code.visualstudio.com/download)

### 1. .env ファイルを作成
1. `.env.example` ファイルをコピーし、`.env` ファイルを作成する。
2. `GIT_USER_NAME`, `GIT_USER_EMAIL` それぞれに、自身の名前とメールアドレスを入力する。
    - 例：
      ```
      GIT_USER_NAME="Tatsuya Kai"
      GIT_USER_EMAIL="tatsuya.kai@example.com"
      ```
- (※)本来の目的は、コンテナ内でもGit操作をできるようにするためだが、まだ実現できていない。

### 2. Docker Compose を使って開発環境を作成
1. Terminalから、`spring-boot-practice` があるディレクトリに移動する。
2. 以下、Terminal操作
    ```bash
    # Dockerコンテナの作成
    $ docker compose up -d --build
    ### コンテナ立ち上げ処理が走り始めるので、終了まで待つ
    ```

### 3. VSCodeの準備
1. VSCodeの拡張機能から、`Dev Containers` を検索し、インストールする。

### 4. `Dev Containers` を使って、コンテナ上のソースを開く
1. サイドバーに、`リモート エクスプローラー` のアイコンがあるので、それをクリックする。
2. 出てきたコンテナ一覧から、`spring-boot-practice spring_java` というものを見つけ `→` の右隣の「フォルダ追加」っぽいマークをクリックする。
3. 新しいウィンドウで、コンテナ上のSpringコードが開く

### 5. コンテナ内のVSCodeの準備
1. コンテナ内を表示するVSCodeの拡張機能から、以下のプラグインを検索してインストールする
   - vscjava.vscode-java-pack
   - vmware.vscode-boot-dev-pack
   - vscjava.vscode-gradle
   - shardulm94.trailing-spaces
   - christian-kohler.path-intellisense
   - MS-CEINTL.vscode-language-pack-ja
   - aaron-bond.better-comment

### 6. Springを起動してみる
1. サイドバーに、`Spring Boot Dashboard` のアイコン（電源ボタンのようなもの）があるので、それをクリックする。
2. `▶️` が2つ重なったような `Run` のアイコンをクリックすると、起動する。