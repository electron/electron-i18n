---
title: Electron で V8 や Chromium の機能を使用する
author: jlord
date: '2016-01-07'
---

Electron アプリケーションの構築は、1 つのブラウザ向けに 1 つのコードベースとデザインを作成するだけでいいので、非常に手軽です。 しかも Electron は最新リリースの [Node.js](http://nodejs.org) と [Chromium](https://www.chromium.org) を保持しており、同梱の優れた機能を利用できます。 これにより以前はウェブアプリに含める必要があった依存関係が解消される場合があります。

---

多くの機能があるため、ここでは例をいくつか取り上げます。すべての機能について知りたい場合は、[Google Chromium ブログ](http://blog.chromium.org) 及び [Node.js 変更ログ](https://nodejs.org/en/download/releases) に目を通してください。 Node.js、Chromium、V8 の Electron での使用バージョンは [electronjs.org/#electron-versions](https://electronjs.org/#electron-versions) で確認できます。

## V8 による ES6 サポート

Electron は Chromium のレンダリングライブラリに Node.js を組み合わせています。 二者は同じ JavaScript エンジン [V8](https://developers.google.com/v8) を共有します。 多くの ECMAScript 2015 (ES6) の機能はすでに V8 に組み込まれており、コンパイラーがなくても Electron アプリケーションで使用できます。

以下にいくつかの例を示しますが、class (strict モード)、ブロックスコープ、Promise、TypedArray などを書くこともできます。 V8 の ES6 機能の詳細については [このリスト](https://nodejs.org/en/docs/es6/) を参照してください。

**アロー関数**

```js
const findTime = () => {
  console.log(new Date())
}
```
**文字列内挿**

```js
var octocat = "Mona Lisa";
console.log(`The octocat's name is ${octocat}`);
```

**new.target**

```js
function Octocat() {
  if (!new.target) throw "Not new";
  console.log("New Octocat");
}

// 例外が投げられる
Octocat();
// ログが出る
new Octocat();
```

**Array.includes**

```js
 // true を返します
[1, 2].includes(2);
```

**残余引数**

```js
// 可変長引数を配列として表現します
(o, c, ...args) => {
  console.log(args.length)
}
```

## Chromium の機能

Google と Chromium に貢献してくれた皆の協力のおかげで、Electron アプリを構築するときに、以下のすごいものも使用できます (これだけではありません)。

- [MouseEvent.getModifierState()](https://googlechrome.github.io/samples/mouseevent-get-modifier-state/index.html)
- [CSS.escape()](https://googlechrome.github.io/samples/css-escape/index.html)
- [Fetch API ストリーム](https://googlechrome.github.io/samples/fetch-api/fetch-response-stream.html)

[Google Chromium ブログ](http://blog.chromium.org) をフォローすれば、新しいバージョンが出るたびにその機能について知ることができます。また、Electronが使用する Chromium のバージョンは [こちら](https://electronjs.org/#electron-versions) で確認できます。

## 何か好きなものはありましたか?

V8 や Chromium のお気に入りの組み込み機能を [@ElectronJS](https://twitter.com/electronjs) 宛にツイートしましょう。

