# ベースイメージとしてPythonの公式イメージを使用
FROM python:3.9-slim

# 作業ディレクトリを設定
WORKDIR /app

# ホスト側の現在のディレクトリの内容をコンテナの/appにコピー
COPY . /app

# 必要な依存関係があればインストール (今回は無し)
RUN pip install --no-cache-dir flask

# シンプルな Flask アプリケーションを作成
RUN echo 'from flask import Flask\napp = Flask(__name__)\n@app.route("/")\ndef hello():\n    return "Hello, World!"\nif __name__ == "__main__":\n    app.run(host="0.0.0.0", port=80)' > app.py

# ポート80を公開
EXPOSE 80

# コンテナ起動時にFlaskアプリを起動
CMD ["python", "app.py"]

