---
name: create-feature
description: Feature-based Architectureに基づき、新しい機能をプロジェクトに追加します。
---

# Create Feature Skill

新しい機能モジュールを作成する際のガイドラインです。プロジェクトの一貫性を保つため、以下の手順に従ってください。

## 手順

1. **機能名の決定**
   - 機能名（Feature Name）を決定します。形式はケバブケース（例: `user-profile`, `article-editor`）とします。

2. **ディレクトリ構造の作成**
   - `src/features/<feature-name>/` ディレクトリを作成します。
   - その中に以下の標準的なサブディレクトリを作成します：
     - `components/`: この機能固有のUIコンポーネント
     - `api/`: サーバーアクションやAPIロジック
     - `types/`: 型定義
     - `hooks/`: カスタムフック（必要に応じて）
     - `index.ts`: 公開APIのエクスポート用

3. **ファイルの配置**
   - **ルーティング**: ページが必要な場合は、`src/routes` 配下にファイルを作成し、`src/features/<feature-name>/components` からメインコンポーネントをインポートして使用してください。ロジックを `routes` に直接書かないようにします。
   - **コンポーネント**: UIロジックは可能な限り `src/features/<feature-name>/components` 内に閉じ込めます。

4. **確認事項**
   - 既存の共通コンポーネント（`src/components/ui` など）が利用できる場合は再利用してください。
   - 新しいライブラリが必要な場合は、ユーザーに確認してから追加してください。

## 実行例

ユーザーから「記事のブックマーク機能を作って」と言われた場合:

1. 機能名: `bookmark`
2. 作成:
   - `src/features/bookmark/components/BookmarkButton.tsx`
   - `src/features/bookmark/api/toggleBookmark.ts`
   - `src/features/bookmark/types/index.ts`
   - `src/features/bookmark/index.ts`
