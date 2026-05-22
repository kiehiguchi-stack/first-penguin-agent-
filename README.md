# 🐧 First Penguin Agent

先駆者を育成する4つのAIエージェントシステム。

## エージェント一覧

| エージェント | 役割 |
|---|---|
| 🔴 平均解棄却エージェント | 凡庸なアイデアを容赦なく棄却し、別角度を要求 |
| 🟠 極端思考ブースター | 思考を左右に振り切り、発想の限界を押し広げる |
| 🟡 先駆者育成コーチ | 松岡修造スタイルで魂から鼓舞する |
| 🔵 構造更新ナビゲーター | 個人の工夫を業界・組織の構造変化へ引き上げる |

---

## デプロイ手順（Vercel）

### 1. 必要なもの
- [GitHubアカウント](https://github.com)
- [Vercelアカウント](https://vercel.com)（無料）
- [Anthropic APIキー](https://console.anthropic.com)

### 2. GitHubにプッシュ

```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/あなたのユーザー名/first-penguin-agent.git
git push -u origin main
```

### 3. Vercelにデプロイ

1. [vercel.com](https://vercel.com) にログイン
2. **「Add New Project」** をクリック
3. GitHubのリポジトリを選択してインポート
4. **Environment Variables** に以下を追加：
   ```
   Name:  ANTHROPIC_API_KEY
   Value: sk-ant-xxxxxxxxxxxx  ← あなたのAPIキー
   ```
5. **「Deploy」** をクリック

### 4. 完了 🎉

デプロイ完了後、発行されたURL（例: `https://first-penguin-agent.vercel.app`）を共有するだけ！

---

## ローカルで動かす場合

```bash
npm i -g vercel
vercel dev
```

`.env` ファイルを作成：
```
ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxx
```

---

## プロジェクト構成

```
first-penguin-agent/
├── api/
│   └── chat.js          # サーバーレス関数（APIキーを安全に保管）
├── public/
│   └── index.html       # フロントエンド
├── vercel.json          # Vercel設定
└── README.md
```

## 注意

APIキーは絶対にフロントエンドのコードに書かないでください。
このプロジェクトはAPIキーをサーバーレス関数（`api/chat.js`）側で管理し、フロントエンドには露出しない構造になっています。
