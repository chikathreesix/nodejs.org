---
layout: about.hbs
title: Node.js とは
trademark: Trademark
---

# <comment>Node.js® とは</comment>

Node はスケーラブルなネットワークアプリケーションを構築するために設計された非同期型のイベント駆動の JavaScript 環境です。以下の「Hello
World」の例では、たくさんの接続を同時に処理することができます。各接続ごとにコールバックは発火され、何もすることがない場合、Node はスリープします。

```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

これは OS のスレッドが採用されている一般的な同時実行モデルとは対象的です。
スレッドベースのネットワーキングは比較的非効率であり、使うのはとても困難です。
さらに Node にはロックがないので Node ユーザーはプロセスのデッドロックの悩みから開放されます。
ほとんどの Node の関数は I/O を直接実行しないため、プロセスをブロックしません。
ブロックしないのでスケーラブルなシステムを開発するのに Node はとても最適です。

この言葉だけでは不慣れな部分がいくつかあるかもしれません。
[Blocking vs
Non-Blocking](https://nodejs.org/en/docs/guides/blocking-vs-non-blocking/)
にもう少し詳しい記事があります。

---

Node は Ruby の [Event Machine](http://rubyeventmachine.com/) や Python の
[Twisted](http://twistedmatrix.com/) のシステムに影響を受けていて、同様の設計です。
Node
はランタイムコンストラクタの替わりにライブラリとして[イベントループ](https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/)を提供し、さらに小さなイベントモデルを持ちます。
ほかのシステムではイベントループの開始時にブロッキングコールが常にあります。
典型的な例ではスクリプトの先頭で動作をコールバックを用いて定義し、
最後に `EventMachine::run()` のようなブロッキングコールでサーバを起動します。
Node ではそのようなイベントループを開始する呼び出しはありません。
Node は単純にスクリプトを実行した直後にイベントループが開始されます。
実行するコールバックがこれ以上ない場合に Node はイベントループから抜けます。
この動作はブラウザ上の JavaScript と似ています — イベントループはユーザからは隠されます。

HTTP はストリーミングと低遅延を念頭に置いて設計された Node の第一級オブジェクトです。
これは Node で Web ライブラリやフレームワークの基礎を作るために適しています。

Node はスレッドがない設計をしているという理由だけで、複数コアの利点が得られないわけではありません。
通信しやすく設計された子プロセスは
[`child_process.fork()`](https://nodejs.org/api/child_process.html#child_process_child_process_fork_modulepath_args_options)
API を使って生成できます。
コア上でロードバランシングを有効にするためにプロセス間でソケットを共有することを可能にする
[`cluster`](https://nodejs.org/api/cluster.html) モジュールが同じインターフェース上に内蔵されています。
