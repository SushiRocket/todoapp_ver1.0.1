# 例: Python3.11 + Node20 両方を一緒に使えるベースイメージを作る
FROM python:3.11-slim AS base

# Node.js を追加インストール
# ここでは NodeSource の公式リポジトリを使う方法の例
RUN apt-get update && apt-get install -y curl gnupg2 && \
    curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt-get install -y nodejs

# pip をアップグレード
RUN pip install --upgrade pip

# コンテナ内作業ディレクトリ
WORKDIR /workspace

# あとは何も実行しない。postCreateCommand で Django と React プロジェクトを作る
CMD ["bash"]
