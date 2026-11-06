# 第6回 Webエンジニアリング
## 学籍番号
4724201
## `Todo`型の定義
export type Todo = {
  id: number;
  title: string;
  completed: boolean;
  dueDate?: string;
};
## 未完了件数を返す関数の引数と戻り値の型
export async function countIncompleteTodos(): Promise<number> {
  const currentTodos = await fetchTodos();
  const incompleteTodos = currentTodos.filter(
    (todo) => !todo.completed
  );
  return incompleteTodos.length;
}
## 未完了件数の実行結果
@4724201 ➜ /workspaces/web-eng-typescript (main) $ pnpm run start
$ tsx src/index.ts
[
  { id: 1, title: '型を定義する', completed: true },
  { id: 2, title: '関数を作る', completed: false }
]
関数を作る
[
  { id: 1, title: '型を定義する', completed: true },
  { id: 2, title: '関数を作る', completed: true }
]
未完了TODOの件数: 1