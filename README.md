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

### 手順

Gitクローン（お好きなフォルダで）
```
git clone xxxx(リポジトリのURL)
```

.env.exampleファイルをコピーして .envファイルを生成する
```
cd quiz-app
cp .env.example .env
```

APP_KEYを生成
```
php artisan key:generate
```

Dockerコンテナを起動（初回起動時は時間がかかります）
```
sail up -d
```

viteを起動（ターミナルで別タブを開いて実行するのがおすすめ）
```
sail npm run dev
```

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
