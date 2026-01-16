---
name: commit-message
description: プロジェクトの規約（Conventional Commits）に従い、適切な変更内容を含むコミットメッセージを作成するためのスキル。
---

# Commit Message Skill

Gitのコミットメッセージを作成する際のルールとテンプレートです。**Conventional Commits** に準拠します。

## フォーマット

```text
<type>(<scope>): <subject>

<body>

<footer>
```

## 1. Type (必須)

変更の種類を表すキーワードを選択してください。

- **feat**: 新機能の追加
- **fix**: バグ修正
- **docs**: ドキュメントのみの変更
- **style**: コードの動作に影響しない変更（空白、フォーマット、セミコロン欠落など）
- **refactor**: バグ修正も機能追加も行わないコードの変更（リファクタリング）
- **perf**: パフォーマンスを向上させるコードの変更
- **test**: テストの追加や修正
- **chore**: ビルドプロセスやドキュメント生成などの補助ツールやライブラリの変更

## 2. Scope (任意)

変更の影響範囲を示します。基本的には **機能名** や **モジュール名** を指定します。
- 例: `feat(auth):`, `fix(editor):`, `style(ui):`
- 全体に影響する場合は省略可能、または `*` を使用。

## 3. Subject (必須)

変更内容の簡潔な要約（50文字以内推奨）。
- **必ず英語で記述してください**。
- 命令形で記述する（例: `Add feature` であり `Added feature` や `Adds feature` ではない）。
- 文末にピリオドは不要。

## 4. Body (任意)

変更の詳細な説明。
- **可能な限り英語で記述してください**（チームの英語力に応じて柔軟に対応可ですが、基本は英語推奨）。
- **What**: 何を変えたか
- **Why**: なぜ変えたか（コンテキスト）
- 破壊的変更がある場合はここで明記する。

## 例

### 新機能の追加
```text
feat(article): add like button to article page

- Add like button component to the article detail page
- Implement server action `toggleLike`
- Show login modal for non-authenticated users
```

### バグ修正
```text
fix(auth): fix redirect url after login

Change the redirect behavior to return to the previous page instead of always redirecting to the home page.
```

### ドキュメント更新
```text
docs(readme): update setup instructions
```
