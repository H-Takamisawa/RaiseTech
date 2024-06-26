### 第7回課題

## 概要
1. 作成環境の脆弱性について考える
2. 感想

## 1. 作成環境の脆弱性について考える
1. アカウントIDがGitHubで公開しているエビデンス画像に載っていること
    - アカウントIDは一意の識別子の一つであり、これが漏洩するだけでも攻撃者のターゲットになる可能性もあるという記事があるくらい大事な情報の一つであるため、容易に公開するのは避けたほうがいい。
    - 対策としては、アカウントIDが載ってしまう場合、画像編集でマスクするなどの自衛をすることが挙げられる。

2. EC2のセキュリティグループのインバウンドルールでポート80を0.0.0.0/0で許可していること
    - ALBからEC2にアクセスする環境なので、EC2に直接HTTP接続できる状態はリスクであるため、EC2に直接接続する事を禁止する設定にする必要がある。
    - 対策としては、EC2のセキュリティグループのインバウンドルールでALBのセキュリティグループからのみHTTPを許可するように設定する。

3. ALBにHTTPアクセスするルールになっていること
    - HTTPは暗号化されていない通信なので、通信を覗き見される危険がある。
    - 対策としては、ACMによりSSL証明書を発行してALBにアタッチする。
      加えて、ALBのリスナーの設定をHTTPSの443番ポートを指定するように変更する。

## 2. 感想
- セキュリティ対策としてどこにどんな問題があって、どうすれば対策になるのかを考えることはとても大変だと感じました。
- 公開する情報に関しても問題ない情報かをきちんと検討しないと、思わないところでリスクとなっている危険があるということを理解して、慎重にならないといけないなと思いました。