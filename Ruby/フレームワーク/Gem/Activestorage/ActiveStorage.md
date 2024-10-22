# ActiveStorage(アクティブストレージ)  
|利用可能フレームワーク | RubyonRails                                                   |  
|---------------------|---------------------------------------------------------------|
|用途                  |* アプリに画像投稿機能を実装することができるGem。  |
|                      |* 画像URLを投稿フォームに記述し送信するタイプや、実際の画像データを送信するタイプの実装が可能。 |
|                      |* デフォルトだと1枚/回の画像データの送信をする。　                |
|                      |* Railsで使用する場合は付随するGemを3つ追加でインストールする必要がある
|bundle install        | 要                                                           | 
|個別インストール        | 要                                                         |
|設定変更               | 要                                                           |  

## 実装方法  
⑴アプリケーションのディレクトリへ移動し、ターミナルで以下のコマンドを実行し`imagemagic`をインストールする。
```bush
 brew install imagemagick
```
⑵アプリのGemファイル最下行に以下のように追記する。  
```ruby
gem "mini_magick"
gem "image_processing", "~> 1.2"
```
⑶アプリケーションのディレクトリであることを確認し、ターミナルで以下のコマンドを実行する。
```bush
bundle install
```  
⑷`config/application.rb`の以下の部分に設定を追記する。  
```ruby
#省略

module アプリ名称
# Initialize configuration defaults for originally generated Rails version.
`config.active_storage.variant_processor = :mini_magick`
#この部分を追記

#省略
```
⑸ローカルサーバーの再起動を行う。  
```bush
rails s
```
⑹アプリのディレクトリであることを確認し、以下のコマンドをターミナルで実行する。  
```bush
rails active_storage:install
```
⑺上記コマンドを実行するとマイグレーションファイルが生成される為dbマイグレートを実行する。  
```bush
rails db:migrate
```
⑻データベースを確認できるソフトを使用して、`active_storage_*`という名前のテーブルが合計3つ作成されていれば実装準備完了。  

## 使用方法  
⑴画像投稿機能を実装したいモデルに`has_one_attachedメソッド`を記述してレコードとファイルを紐づける。 
>[!NOTE]
>* この記述を行うことで、`モデル名.ファイル名`で送付されたファイルにアクセス可能になる。
>* このファイル名は紐づいたモデルのフォームから送られるパラメーターのキーにもなる。
>* ActiveStorageを使用する場合、紐づいたモデルではなくActivestorageのテーブルに画像データが保存されるため、モデルに新しくカラムを追加する必要はない。
  
```ruby
class モデル < ApplicationRecord
  has_one_attached :ファイル名(小文字) #添付ファイルが分かる名前にする
end
```
⑵紐づいたモデルに対応するコントローラーに、画像データが保存されるようにストロングパラメーターを設定する。  
>[!CAUTION]
>* 画像字体を直接データベースへ保存するタイプの実装をした場合、バリデーションで`null: false`になっているとテストコードで`Faker`を使用してインスタンスの自動生成をすることができない。
>* その場合は以下を参考にして、アプリ内に保存されたダミー画像を使用してテストを実施する。
>  ```ruby
>  FactoryBot.define do
>    factory :紐づいたモデル名 do
>     after(:build) do |紐づいたモデル名(小文字)|
>        紐づいたモデル名(小文字).ファイル名(小文字).attach(io: File.open('ダミー画像の保存先パス'), filename: '拡張子を含むダミー画像ファイル名')
>     end
>   end
>  end  
>  ```

## 関連ワード  
