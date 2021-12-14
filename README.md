# shakyo-es-module

ES module のテストプログラム

[HTMLでES moduleをつかうメモ](https://chaika.hatenablog.com/entry/2018/12/17/083000) を写経。

# 確認

```
$ cd shakyo-es-Module
$ python -m http.server 8080
```

![ss](./doc-image/ss1.png)

# メモ

## ファイルの関連
```
index.html
    <head>
      <script type="module" src="src/main.js"></script>
      ↓
src/main.js
    import {square, cube} from './math-module.js';
      ↓
src/math-module.js
    export function cube(x) { ... }
```

## 処理の流れ
```
index.html
    <script src="...">で src/main.js を取得
      ↓
src/main.js
   import {square, cube} from '...' で src/math-module.js 内の関数をインポート
   component()関数を定義
   component()関数を実行
    フォーマット文字列の ${cube(5)} で src/math-module.js 内の cube() 関数をコール
src/math-module.js
    cube()を実行
      ↓
src/main.js
    cube()の戻り値をフォーマット文字列に埋め込む
    <pre>タグを定義して、その innerHTMLにフォーマット文字列を入れる
    その<pre>タグを appendChild()でDOMに追加
```


