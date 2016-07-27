# ポイントトラブルシューティング

## ページ訪問が認識されない

いくつかの理由が考えられます:

1) Mauticにログインしたままページ訪問のテストをしていないか確認してください。Mauticはユーザーが生成したアクティビティは無視するので、匿名セッションか別のブラウザを利用するか、Mauticからログアウトしてください。

2) この時点では、ポイントアクションは一つのコンタクトにつき一度のトラッキングになります。これはつまり、すでにトリガーされているアクションは連続した訪問では再トリガーされないということです。

3) URLが訪問したURLに_正確に_マッチするようにするか、もしくはワイルドカードを使用するようにしてください。(<a href="https://ja.wikipedia.org/wiki/Uniform_Resource_Locator" target="_blank">URLにはスキーマ、ホスト/ドメイン、パス、クエリーパラメータ、そして/もしくはフラグメントが含まれることに留意してください)

例えば、`http://example.com`というURLを持っていたとして、ページヒットが`http://example.com/index.php?foo=bar`を登録したとすると、そのアクションはトリガーされません。しかし、`http://example.com*`をURLとして使うとマッチするのでトリガーされます。