# セットアップガイド

## 前提条件

- Node.js 16.0.0 以上
- npm または yarn
- Git

## インストール手順

### 1. リポジトリのクローン

```bash
git clone https://github.com/username/family-budget-app.git
cd family-budget-app
```

### 2. 依存関係のインストール

```bash
npm install
```

### 3. 環境変数の設定

```bash
cp .env.example .env.local
```

`.env.local` ファイルを編集して、以下の設定を追加してください：

#### Firebase設定

1. [Firebase Console](https://console.firebase.google.com/) でプロジェクトを作成
2. Authentication を有効化し、Google サインインを設定
3. Firestore Database を作成
4. プロジェクト設定から設定値を取得して `.env.local` に設定

### 4. 開発サーバーの起動

```bash
npm run dev
```

ブラウザで http://localhost:3000 にアクセスしてアプリが起動することを確認してください。

## Firebase設定詳細

### Authentication設定

1. Firebase Console で「Authentication」を選択
2. 「Sign-in method」タブで「Google」を有効化
3. プロジェクトのパブリック名前を設定

### Firestore設定

1. Firebase Console で「Firestore Database」を選択
2. 「データベースを作成」をクリック
3. 「テストモードで開始」を選択（後でセキュリティルールを設定）

### セキュリティルール

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /families/{familyId} {
      allow read, write: if request.auth != null && 
        request.auth.uid in resource.data.members;
      
      match /transactions/{transactionId} {
        allow read, write: if request.auth != null && 
          request.auth.uid in get(/databases/$(database)/documents/families/$(familyId)).data.members;
      }
    }
  }
}
```

## トラブルシューティング

よくある問題と解決方法については [TROUBLESHOOTING.md](TROUBLESHOOTING.md) を参照してください。
