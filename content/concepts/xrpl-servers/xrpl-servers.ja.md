---
html: xrpl-servers.html
parent: concepts.html
blurb: rippledは、XRP Ledgerを管理するコアとなるピアツーピアサーバーです。
template: pagetype-category.html.jinja
---
# XRP Ledger サーバー

XRP Ledgerを動かすサーバーソフトウェアは、主に2種類あります。

- コアサーバーである`rippled`は、トランザクションを処理し、その結果についてコンセンサスを得るピアツーピアネットワークを実行します。
- APIサーバーである[Clio](the-clio-server.html)は、台帳からデータをフェッチしたりクエリしたりするための強力なインターフェイスを提供します。

誰でも必要に応じて、これらのタイプのサーバーの1つまたは両方のインスタンスを実行することができます。

## 独自サーバーを運用する理由

簡単なユースケースや個別のサーバーであれば、無料の[公開サーバー][]を利用することも多いでしょう。しかし、XRP Ledgerの利用が本格化すればするほど、独自のインフラを持つことが重要になってきます。

独自のサーバーを運用したいと思う理由はたくさんありますが、そのほとんどは、「自分のサーバーを信頼できる」「ワークロードをコントロールできる」「いつ、どのようにアクセスできるかを他人の判断に左右されない」ということに集約されます。もちろん、悪意のあるハッカーからサーバーを守るために、優れたネットワークセキュリティを実践する必要があります。

利用しているサーバーを信頼する必要があります。悪意のあるサーバーに接続すると、そのサーバーに利用されたり、損害を受けたりする可能性があります。例えば、以下のようなことです。

* 悪意のあるサーバーは、支払いを行っていないにもかかわらず、支払いを受けたと報告する可能性があります。
* 選択的に支払いパスや通貨交換のオファーを表示または非表示にすることができ、最良の取引を提供せず、彼ら自身の利益を確保する可能性があります。
* もし、アドレスの秘密鍵を送信してしまった場合、サーバーの管理者はあなたに代わって任意のトランザクションを実行し、アドレスが保有するすべての資金を転送または破棄する可能性があります。

さらに、独自のサーバーを運営することで、[管理者アクセス権限](get-started-using-http-websocket-apis.html#管理者アクセス権限)が与えられ、重要な管理者専用コマンドや負荷の高いコマンドを実行することができます。共有サーバーを使用する場合、同じサーバーの他のユーザーとサーバーの計算能力を共有することを考慮しなければいけません。WebSocket APIのコマンドの多くはサーバーに大きな負担をかけるので、サーバーには必要なときに応答を縮小するオプションがあります。サーバーを他人と共有する場合、常に最良の結果を得られるとは限りません。

最後に、バリデーションサーバーを運用する場合、パブリックネットワークへのプロキシとしてストックサーバーを使用し、バリデーションサーバーをプライベートネットワークに置いて、ストックサーバーを通してのみ外部にアクセスできるようにすることができます。これにより、バリデーションサーバに侵入することがより困難になります。

## サーバーの機能とトピックス

<!-- provided by the auto-generated table of children -->

<!--{# common link defs #}-->
{% include '_snippets/rippled-api-links.md' %}
{% include '_snippets/tx-type-links.md' %}
{% include '_snippets/rippled_versions.md' %}
