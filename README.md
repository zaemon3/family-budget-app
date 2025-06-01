# 家族共有家計簿アプリ

家族みんなでリアルタイムに共有できる家計簿アプリです。

## 🌟 主な機能

- 📱 **リアルタイム同期** - 家族の誰かが入力すると、即座に全員のデバイスに反映
- 👨‍👩‍👧‍👦 **家族共有** - 複数のユーザーで同じ家計簿を管理
- 📊 **詳細な分析** - カテゴリ別支出分析、月別・年別レポート
- 🔒 **安全な認証** - Googleアカウントによる安全なログイン
- 📱 **PWA対応** - スマートフォンアプリのように使用可能
- 🌐 **オフライン対応** - ネットワークがなくても使用可能

## 🚀 クイックスタート

### 前提条件

- Node.js 16.0.0 以上
- npm または yarn

### インストール

```bash
# リポジトリのクローン
git clone https://github.com/username/family-budget-app.git
cd family-budget-app

# 依存関係のインストール
npm install

# 環境変数の設定
cp .env.example .env.local
# .env.local ファイルを編集して Firebase の設定を追加

# 開発サーバーの起動
npm run dev
```

## 📚 詳細ドキュメント

- [セットアップガイド](docs/SETUP.md)
- [家族向け使い方ガイド](docs/FAMILY_GUIDE.md)
- [デプロイガイド](docs/DEPLOYMENT.md)
- [API仕様](docs/API.md)

## 🤝 コントリビューション

プルリクエストやイシューの報告を歓迎します！

## 📄 ライセンス

MIT License
