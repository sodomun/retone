# ReTone

AI によるテキスト調整機能を備えたリアルタイムメッセージングアプリです。
Next.js + Firebase + Gemini API で構築されています。

## WebアプリのURL
https://retone-black.vercel.app

## 主な機能

- **メール認証** — メールアドレス / パスワードでのサインアップ・ログイン
- **1対1チャット** — 友達を追加してリアルタイムにメッセージ交換
- **グループチャット** — 複数人のグループトークを作成・チャット
- **AI テキスト調整** — 受信メッセージを Gemini 2.5 Flash で自動的に加工（任意のプロンプト文でAIの性格を決めることが可能）
- **プロフィール設定** — 表示名の変更

## 技術スタック

| カテゴリ          | 使用技術                |
| ----------------- | ----------------------- |
| フレームワーク    | Next.js 16 (App Router) |
| UI                | React 19                |
| 言語              | TypeScript 5            |
| バックエンド / DB | Firebase Firestore      |
| 認証              | Firebase Authentication |
| AI                | Google Gemini 2.5 Flash |

## セットアップ

### 1. リポジトリのクローン

```bash
git clone https://github.com/sodomun/retone.git
cd retone
```

### 2. 依存関係のインストール

```bash
npm install
```

### 3. 環境変数の設定

`.env.example` をコピーして `.env.local` を作成し、各値を入力してください。

```bash
cp .env.example .env.local
```

```env
# Gemini API
GEMINI_API_KEY=your_gemini_api_key

# Firebase
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_firebase_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_firebase_storage_bucket
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_firebase_messaging_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_firebase_app_id
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_firebase_measurement_id
```

- **Gemini API キー**: [Google AI Studio](https://aistudio.google.com/) で取得
- **Firebase 設定値**: Firebase コンソールのプロジェクト設定から取得

### 4. 開発サーバーの起動

```bash
npm run dev
```

ブラウザで [http://localhost:3000](http://localhost:3000) を開いてください。

## ディレクトリ構成

```
src/
├── app/
│   ├── api/adjust-message/   # AI テキスト調整 API Route
│   ├── friends/add/          # 友達追加ページ
│   ├── login/                # ログインページ
│   ├── signup/               # 新規登録ページ
│   ├── settings/             # 設定ページ
│   └── talk/                 # トーク一覧・チャット画面
├── components/
│   ├── chat/                 # チャット関連コンポーネント
│   ├── common/               # 共通コンポーネント
│   ├── talk/                 # トーク一覧コンポーネント
│   └── user/                 # ユーザー関連コンポーネント
├── hooks/                    # React が提供する useState / useEffect を持つファイル群. リスナー登録・解除の処理が多い
└── lib/                      # 各ページに対応するロジック・関数を持つ
```

## スクリプト

```bash
npm run dev    # 開発サーバー起動
npm run build  # プロダクションビルド
```
