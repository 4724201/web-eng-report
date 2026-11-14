# 第7回 Webエンジニアリング演習 レポート
## 学籍番号
4724201
## 2画面の見出しと本文
csr/app.ts で、比較画面と詳細画面の見出し・本文を以下のように設定した。

① 比較画面（#compare）

<h1>画面生成方式の比較</h1>
<p>MPA・SPA・CSR・SSRの違いを比較する。</p>

② 詳細画面（#detail）

<h1>画面生成方式の詳細</h1>
<p>それぞれの方式の特徴を説明する。</p>

URLのハッシュが #compare の場合は比較画面が表示され、#detail の場合は詳細画面が表示される。


## クリック後のURLとNetworkの確認
csr/index.html に以下のリンクを作成した。

<nav>
  <a href="#compare">比較</a>
  <a href="#detail">詳細</a>
</nav>
<main id="app"></main>
<script type="module" src="./app.js"></script>

「比較」をクリックすると、URLが以下のように変化する。

https://curly-cod-7vjvr999wxw6crv69-3000.app.github.dev/csr/?utm_source=chatgpt.com#compare

「詳細」をクリックすると、URLが以下のように変化する。

https://curly-cod-7vjvr999wxw6crv69-3000.app.github.dev/csr/?utm_source=chatgpt.com#detail

Networkタブで通信を確認した結果、最初のページ読み込み時にはDocumentリクエストが1件発生した。その後、「詳細」と「比較」をクリックするとURLのハッシュと画面の内容は切り替わったが、新しいDocumentリクエストは発生しなかった。このことから、ページ全体を再読み込みせずに画面を切り替えられることを確認した。


## 画面を切り替える処理の要点

csr/app.ts に以下のコードを記述した。

const app = document.querySelector("#app");

if (app === null) {
  throw new Error("#appが見つからない");
}

const appElement = app;

function renderPage() {
  const page = location.hash;

  if (page === "#detail") {
    appElement.innerHTML = `
      <h1>画面生成方式の詳細</h1>
      <p>それぞれの方式の特徴を説明する。</p>
    `;
  } else {
    appElement.innerHTML = `
      <h1>画面生成方式の比較</h1>
      <p>MPA・SPA・CSR・SSRの違いを比較する。</p>
    `;
  }
}

renderPage();

window.addEventListener("hashchange", renderPage);