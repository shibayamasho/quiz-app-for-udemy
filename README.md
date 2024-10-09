# quiz-app

Udemyで公開しているクイズアプリ制作のソースコードです

## 環境

- PHP v8.3
- Laravel v11
- Laravel Sail
- Laravel Breeze
- Docker

## インストール方法

前提として、以下が必要です
- Gitがインストールされている
- Dockerがインストールされている
- PHP8.2以上がインストールされている
- Composerがインストールされている
- nodeがインストールされている

### 手順

Gitクローン（お好きなフォルダで）
```
git clone xxxx(リポジトリのURL)
cd quiz-app
```

composerをインストールする
```
composer install
```

.env.exampleファイルをコピーして .envファイルを生成する
```
cp .env.example .env
```

APP_KEY（.envの環境変数）を生成
```
php artisan key:generate
```

Dockerコンテナを起動（初回起動時は時間がかかります）
```
sail up -d
```

npmインストール
```
npm ci
```

viteを起動（ターミナルで別タブを開いて実行するのがおすすめ）
```
sail npm run dev
```

※もし sail npm run dev でエラーになる場合の対処方法は、コース内の環境構築のセクションのレクチャー「学習開始時・終了時に実行する操作について」で解説しています

マイグレーションを実行
```
sail artisan migrate
```

シーディングを実行（管理者データを作成）
```
sail artisan db:seed
```

管理画面：localhost/login を開く

管理者ログイン情報
- メールアドレス：test@example.com
- パスワード：password123

プレイヤー画面：ブラウザで localhost を開く
