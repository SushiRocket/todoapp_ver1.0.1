# backend/Dockerfile

From python:3.10-slim

# 作業ディレクトリ
WORKDIR /app

# システム更新と必要ライブラリのインストール
# apt-get update && apt-get install -y build-essential で、まずAPTのパッケージリストを更新し (apt-get update)、次に build-essential パッケージをインストールしています。build-essential にはGCCやG++などのC/C++コンパイラや、makeなどのビルドに必要な基本ツールが含まれています。その後の apt-get clean と rm -rf /var/lib/apt/lists/* は、aptでダウンロードしたキャッシュやリストファイルを削除する処理です。これによって不要ファイルが削除され、コンテナイメージのサイズを小さくできます。
RUN apt-get update && apt-get install -y \
    build-essential \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 依存関係をインストール
COPY requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Djangoプロジェクトをコンテナのコピー
COPY . .

# ポートを公開
EXPOSE 8000

# サーバー起動コマンド
CMD ["python", "manage.py", "runserver", "0.0.0.8000"]