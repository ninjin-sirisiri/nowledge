---
name: write-test
description: プロジェクトのテストコード（Unit, Integration）を作成・修正するためのガイドライン。
---

# Write Test Skill

VitestとSolid Testing Libraryを使用したテスト作成のスタンダードです。

## 基本方針

- **フレームワーク**: Vitest
- **ライブラリ**: `@solidjs/testing-library`, `@testing-library/user-event`
- **ファイル配置**: テスト対象ファイルと同じディレクトリに `__tests__` フォルダを作るか、`ComponentName.test.tsx` のように隣接させる（プロジェクトの慣習に合わせる）。

## テストカテゴリと実装詳細

### 1. ユニットテスト (Utility/Logic)
ロジック関数やユーティリティのテストです。純粋な関数の振る舞いを検証します。

```typescript
// example.test.ts
import { describe, it, expect } from 'vitest';
import { calculateTotal } from './math';

describe('calculateTotal', () => {
  it('should return correct sum', () => {
    expect(calculateTotal(10, 20)).toBe(30);
  });
});
```

### 2. コンポーネントテスト (UI)
UIコンポーネントのレンダリングとインタラクションを検証します。SolidJS特有のReactivityに注意してください。

```typescript
// Component.test.tsx
import { render, screen } from '@solidjs/testing-library';
import userEvent from '@testing-library/user-event';
import { Counter } from './Counter';

describe('Counter', () => {
  it('increments count when button is clicked', async () => {
    const user = userEvent.setup();
    render(() => <Counter />);
    
    const button = screen.getByRole('button', { name: /count is/i });
    expect(button).toHaveTextContent('count is 0');
    
    await user.click(button);
    expect(button).toHaveTextContent('count is 1');
  });
});
```

## チェックリスト

- [ ] **正常系**: 期待通りの入力で期待通りの出力/表示になるか。
- [ ] **異常系**: エラー時や不正な入力時の挙動は正しいか。
- [ ] **境界値**: 0, 空文字, 最大値などの境界条件での動作。
- [ ] **非同期処理**: APIコールを含む場合、モック（Mock）を使用しているか。

## モックの使用

外部API呼び出しなどは基本的にモック化してください。
`vi.mock()` を使用して依存関係を制御します。
