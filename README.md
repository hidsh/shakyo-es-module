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
```
index.html
    <script type="module" src="src/main.js"></script>
      ↓
src/main.js
    component() {
    element.innerHTML = [
        'Hello ES module! script type="module"',
        `5 cubed is equal to ${cube(5)}`
      ↓
src/math-module.js
    export function cube(x) {
        return x * x * x;
    }
```


