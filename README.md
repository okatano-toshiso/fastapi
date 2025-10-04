# 🚀 FastAPI アプリケーション

このプロジェクトは **FastAPI** を使用した Web アプリケーションです。  
以下の手順で環境構築・アプリ起動・データベース初期化を行うことができます。

---

## 📦 環境構築手順

### 1️⃣ プロジェクトディレクトリへ移動
```bash
cd fastapi
```

### 2️⃣ 仮想環境を有効化
Windows:
```bash
.venv\Scripts\activate
```
macOS / Linux:
```bash
source .venv/bin/activate
```

### 3️⃣ 依存パッケージをインストール
```bash
pip install -r requirements.txt
```

---

## ⚙️ アプリケーションの起動

開発サーバーを起動します。
```bash
uvicorn app.main:app --reload
```

アプリが起動したら、以下のURLにアクセスしてください：
- http://127.0.0.1:8000
- 自動生成ドキュメント: http://127.0.0.1:8000/docs

---

## 🗄️ データベースのセットアップ

### 1️⃣ Dockerでデータベースを起動
```bash
docker-compose up -d
```

### 2️⃣ テーブルをリセット
```bash
alembic downgrade base
```

### 3️⃣ 初期テーブルを作成
```bash
alembic upgrade head
```

---

## 🧩 プロジェクト構成

```
fastapi/
├── app/
│   ├── main.py          # エントリーポイント
│   ├── routers/         # ルーティング関連
│   ├── models/          # DBモデル
│   ├── schemas/         # Pydanticスキーマ
│   └── core/            # 設定・共通処理
├── alembic/             # マイグレーション設定
├── requirements.txt     # 依存パッケージ
├── docker-compose.yml   # DBコンテナ設定
└── README.md
```

---

## 🧪 開発Tips

- **ホットリロード**: `--reload` オプションでコード変更を即時反映  
- **APIドキュメント**: `/docs` (Swagger UI) または `/redoc`  
- **マイグレーション**: `alembic revision --autogenerate -m "message"` で新規マイグレーション作成  

---

## 📝 ライセンス

このプロジェクトは MIT ライセンスの下で公開されています。

---

## 🙌 参考リンク

- [FastAPI 公式ドキュメント](https://fastapi.tiangolo.com/)
- [GitHub Markdown 書き方ガイド](https://docs.github.com/ja/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [良いREADMEの書き方 (Qiita)](https://qiita.com/dfalcon0001/items/843b93d90f21b9e99d50)
