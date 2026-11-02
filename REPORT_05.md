# 第5回 Webエンジニアリング演習 レポート

## 学籍番号（学籍番号）
4724201

## TODO配列のコード（コードまたは確認結果）
const todos = [
  { id: 1, title: "型を復習する", completed: true },
  { id: 2, title: "配列を学ぶ", completed: false },
  { id: 3, title: "レポートを書く", completed: false },
  { id: 4, title: "課題を提出する", completed: false },
];


## TODOを更新した条件（コードまたは確認結果）
for (const todo of todos) {
  if (todo.completed === false) {
    todo.completed = true;
    console.log(todo.id + ": " + todo.title + " [完了]");
  }
}

## 完了件数の更新前後の実行結果（コードまたは確認結果）
@4724201 ➜ /workspaces/web-eng-typescript (class-05-collections) $ pnpm run start
$ tsx src/index.ts
1: 型を復習する [完了]
2: 配列を学ぶ [未完了]
3: レポートを書く [未完了]
4: 課題を提出する [未完了]
2: 配列を学ぶ [完了]
3: レポートを書く [完了]
4: 課題を提出する [完了]
完了件数: 更新前 1件 -> 更新後 4件
1: 型を復習する [完了]
2: 配列を学ぶ [完了]
3: レポートを書く [完了]
4: 課題を提出する [完了]
