# Basic認証(ベーシック認証)  
## 解説  
* ユーザー名とパスワードをコントローラーに定義することで簡易的なアクセス制限機能を適用する認証方法のこと。
  認証されたユーザーのみが特定のリソースにアクセス可能になる。

* `application_controller.rb`にメソッドを定義して、そのブロック内にアクセスを許可するユーザー名とパスワードを設定する。
  
## 雛形 
```ruby
  # ユーザー名:test,パスワード:9999に設定
  before_action :basic_auth

  private

  def basic_auth
    authenticate_orA_request_with_http_basic do |username,password|
      username == "test" && password == "9999"
    end
  end
```
## 関連ワード  
* `authenticate_or_request_with_http_basicメソッド`  
