# wp-mypage

wp-mypageはコマンドラインでWordPressをインストールするために作りました。Mac等を使ってローカルにWordPressをインストールされたい方は是非ご活用ください。

## インストール手順

### 1. ファイルのダウンロード

今回インストールを行いたいディレクトリを作成し、このリポジトリからファイルをダウンロードしてください。

```
git clone git@github.com:toyokappa/wp-mypage.git
```

### 2. 設定ファイルを作成

インストールに必要な設定ファイルを作成してください。各項目については任意で設定するようにしてください。

```sh
# .env

# DB情報
export DBNAME=wordpress      # 任意のデータベース名
export DBUSER=username       # 任意のユーザー名
export DBPASS=password       # 任意のパスワード
export DBHOST=hostname       # 任意のホスト名（Macの場合、127.0.0.1）
export DBPREFIX=wp_          # 任意のプレフィックス名（変更不要）

# サイト情報
export URL=url                        # サイトのURL
export TITLE=title                    # サイトのタイトル
export ADMIN_USER=admin_user          # ログインユーザー名
export ADMIN_PASSWORD=admin_password  # ログインパスワード
export ADMIN_EMAIL=admin_email        # 任意のメールアドレス
```

### 3. データベースとユーザーの作成

上記の設定アイルの内容に基づいたデータベースとユーザー作成を行ってください。データベースの作成手順は下記のサイトを参考にしてください。

[データベースとユーザーの作成方法](https://wpdocs.osdn.jp/WordPress_%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB#.E6.89.8B.E9.A0.86_2.EF.BC.9A_.E3.83.87.E3.83.BC.E3.82.BF.E3.83.99.E3.83.BC.E3.82.B9.E3.81.A8.E3.83.A6.E3.83.BC.E3.82.B6.E3.83.BC.E3.81.AE.E4.BD.9C.E6.88.90)

### 4. WP-CLIのインストール（未導入の場合）

インストールのコマンドの実行にWP-CLIが必要となるため、下記のコマンドを実行しWP-CLIをインストールしてください。

```
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
sudo chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/bin/wp
```

インストールが実行できたら下記のコマンドで、インストールが動作確認をしてください。

```
wp --info
```

### 5. インストールの実行

下記のコマンドからインストールを実行してください。

```
source .env
bash install.sh
```

### 6. サーバーの起動

インストールが完了したら、下記のコマンドでサーバーの起動及びブラウザでの起動確認をしてください。

```
wp server
```

[http://localhost:8080/](http://localhost:8080/)を開き、下記のページが表示されればインストール完了です。

![image](https://user-images.githubusercontent.com/29325694/31925360-3751781c-b8c3-11e7-850f-a980bbae177d.png)
