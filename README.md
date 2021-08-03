# 気付いたこと
---

## devise/設定ファイルいじるとデフォのpermitの内容まで変わってるっぽい
- config/initializers/devise のconfig.authentication_keys = [:email] を
config.authentication_keys = [:name]に変えると
デフォルト（ストロングパラメータへの明記なし）でpermitされているキーが
emailからnameに変わるっぽい

=> 新しく追加したキーをログインに使う場合(設定ファイルをいじる場合)は、
ストロングパラメータのkeys:[:(キー名)]のところに
ログインに使う新しいキーの名前ではなくemailを記述する
(configファイルの書き換えによってemailがデフォルトで許可されなくなったため)(多分)


(deviseのgithubでconfigのauthentication_keysの仕様見ればわかるかも)