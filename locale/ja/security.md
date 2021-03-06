---
layout: security.hbs
title: セキュリティ
---

# セキュリティ

## 脆弱性の報告

すべての Node.js の脆弱性は、速やかにメールにて報告するようお願いします [security@nodejs.org](mailto:security@nodejs.org)。
このメールは、セキュリティの問題を管理しているコアチームに自動で送信されます。

あなたのメールは24時間以内に確認され、48時間以内に問題の扱いやこれからの
ステップについての詳細を受け取ることができます。

あなたの報告への返信を行ったのちに、セキュリティチームはあなたに問題を解決するための修正に関する
進捗報告、及びに詳細の発表に尽力します。状況によっては、問題の詳細や発生した環境などについて
あなたに尋ねることもあります。これらの更新は5日おきに送信することになっていますが、実際は
毎24-48時間以内に送られています。

サードパーティ製のモジュールに関するセキュリティのバグは、各モジュールの管理者に報告するように
お願いします。また、[Node セキュリティプロジェクト](https://nodesecurity.io) との調整も
お忘れないようにお願いします。

Node.js のセキュリティ向上への協力に感謝します。あなたの貢献に対する努力と、責任感を伴った情報
共有は、広く評価されます。

## 情報開示のポリシー

Node.js における、情報開示のポリシーをここに記します。

- 脆弱性が報告されると、主要なメンバーがアサインされます。このメンバーは、修正とリリースの
    プロセスを調整します。脆弱性が確認されたら、影響のある全てのバージョンのリストを作成します。
    コードは、潜在的な同様の問題があるか精査されます。修正は、メンテナンスされている全てのバージョン
    に向けて用意されます。これらの修正は、正式なアナウンスを行うまでは公開リポジトリには追加されません。

- CVE (Common Vulnerabilities and  Exposures (CVE®)) により、脆弱性に関する
    情報解禁日が提案され、それを決定します。

- 情報解禁日に、Node.js のメーリングリストに公式発表と同様のものが送信されます。修正済みの
    バージョンは、公開リポジトリに送信され、新しいビルドが nodejs.org に置かれます。メーリングリスト
    に共有されてから6時間以内に、セキュリティ勧告を Node.js のブログにて行います。

- 一般的に情報解禁日は、CVEに報告されてから72時間と設定されます。しかし、脆弱性を修正する複雑さによってはこの限りではありません。

- このプロセスは他のプロジェクトの管理者との調整を必要とする際など、ときに時間を要することがあります。可能な限り迅速にバグを修正するために尽力するだけでなく、一貫性のあるプロセスで情報開示を行うために上記のリリースプロセスを従うこともまた重要です。

## セキュリティリポートを受け取る

セキュリティリポートは、以下のサイトを介して報告されます。

- [https://groups.google.com/group/nodejs-sec](https://groups.google.com/group/nodejs-sec)
- [https://nodejs.org/en/blog](https://nodejs.org/en/blog)

## このポリシーに関して提案をする

このプロセスを改善するための提案をお持ちの際は、[プルリクエスト](https://github.com/nodejs/nodejs.org)
か、 メール [security@nodejs.org](mailto:security@nodejs.org) にてご報告ください。
