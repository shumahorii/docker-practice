# フルスタック Docker アプリ

このプロジェクトは以下の技術で構成されたフルスタックのWebアプリです：

- フロントエンド：React（Vite + TypeScript）
- バックエンド：Node.js（Express）
- データベース：PostgreSQL
- 実行環境：Docker Compose

---

## 🚀 起動手順

### 1. 初回のみ依存関係をインストール（ローカルで確認したい場合）

```bash
cd client
npm install

cd ../server
npm install
```

---

### 2. Dockerでアプリを起動

```bash
docker-compose up --build
```

起動後にアクセスできるURL：

- フロントエンド（React）：http://localhost:5173  
- バックエンド（API）：http://localhost:3001/api/users  
- データベース（PostgreSQL）：localhost:5432  
  - ユーザー：postgres  
  - パスワード：postgres

---

### 3. 初期データの登録

最初の起動時に、`db/init.sql` が実行され、以下のようにテーブルとデータが自動作成されます：

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT
);

INSERT INTO users (name) VALUES ('Shuma'), ('Taro'), ('Hanako');
```

---

## 🧼 クリーンアップ（削除）

すべてのコンテナ・ネットワーク・ボリュームを削除する場合：

```bash
docker-compose down --volumes --remove-orphans
```

---

## 💡 補足

- 初回以降の通常起動は `docker-compose up` だけでもOK
- PostgreSQLのデータを初期化したい場合は `--volumes` オプションを付けて再構築してください


