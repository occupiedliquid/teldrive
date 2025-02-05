# TelDriveへの貢献

このガイドは、TelDriveへの貢献を始めるための手助けをします。

## 開発環境のセットアップ

### 前提条件

- Go (1.22以降)
- Git
- Task
- PowerShell（Windows用）またはBash（Unix系システム用）

### Taskのインストール

##### macOS/Linux (curl)
```sh
curl https://instl.vercel.app/go-task/task | bash
```

#### PowerShell/cmd.exe
```powershell
powershell -c "irm https://instl.vercel.app/go-task/task?platform=windows|iex"
```

### 初期セットアップ

1. リポジトリをクローンします:
```bash
git clone https://github.com/tgdrive/teldrive.git
cd teldrive
```

2. 依存関係をインストールします:
```bash
task deps
```

## TelDriveのビルド

### 完全なビルド
フロントエンドとバックエンドの両方をビルドするには:
```bash
task
```

### フロントエンド開発
フロントエンドは別のリポジトリ ([teldrive-ui](https://github.com/tgdrive/teldrive-ui))で管理されています。 メインリポジトリはビルド中に最新のフロントエンドリリースを取得します。

フロントエンドをセットアップするには：
```bash
task ui
```

### バックエンド開発
バックエンドのみをビルドするには:
```bash
task server
```

### TelDriveの実行
ビルドが完了したら、アプリケーションを実行します:
```bash
task run
```

## 機能開発

1. 機能用の新しいブランチを作成します:
```bash
git checkout -b feature/your-feature-name
```

2. API仕様を生成します:
```bash
task gen
```

## プルリクエストのガイドライン

1. **ブランチ名**:
   - 新機能には `feature/` を使用
   - バグ修正には `fix/` を使用 
   - ドキュメント変更には `docs/` を使用
   - コードのリファクタリングには `refactor/` を使用

2. **コミットメッセージ**:
   - 明確で説明的なコミットメッセージを使用
   - 適用可能な場合は問題を参照

3. **プルリクエストの説明**:
   - 変更内容を説明
   - 関連する問題番号を含める
   - 破壊的変更があればリストアップ