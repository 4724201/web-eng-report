# 第8回 Webエンジニアリング演習 レポート
## 学籍番号
4724201
## コンポーネント構成
src/
├── App.tsx
├── data.ts
├── types.ts
└── components/
    ├── TodoItem.tsx
    └── TodoList.tsx
## `TodoItem`のProps型
import type { Todo } from "../types";

type TodoItemProps = {
    todo: Todo;
};

export function TodoItem({ todo }: TodoItemProps) {
    return (
      <li>
          <strong>{todo.title}</strong>
          <span>{todo.completed ? "(完了)" : "(未完了)"}</span>
          {todo.dueDate && (
            <span style={{ color: new Date(todo.dueDate) < new Date() ? "red" : "inherit" }}>
              期限: {todo.dueDate}
            </span>
          )}
      </li>
  );
}
## 期限あり・なしの画面確認結果
期限が設定されている「Reactを学ぶ」には期限が表示され、期限が過ぎているため赤色で表示された。一方、「Propsを確認する」と「Stateを更新する」には期限が設定されていないため、期限は表示されなかった。

画面確認URL：https://literate-disco-g4v45qqq65g6f74v-5173.app.github.dev/

React TODO
Reactを学ぶ(完了)期限: 2026-11-20
Propsを確認する(未完了)
Stateを更新する(未完了)