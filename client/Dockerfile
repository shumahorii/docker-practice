# 公式Nodeイメージをベースにする
FROM node:23-slim

# 作業ディレクトリ作成
WORKDIR /app

# package.jsonとlockファイルをコピー
COPY package*.json ./

# 依存関係をインストール
RUN npm install

# アプリ全体をコピー
COPY . .

# Viteは開発時にホスト:0.0.0.0で起動が必要
CMD ["npm", "run", "dev", "--", "--host"]
