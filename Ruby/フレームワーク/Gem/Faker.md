# Faker  
|利用可能フレームワーク | RubyonRails                                                   |  
|---------------------|---------------------------------------------------------------|
|用途                  |●メールアドレス、人名、パスワードなど様々な意図に応じた値を         |
|                      |ランダム生成してくれるGem。                                       |
|                      | ●``FactoryBot``と組み合わせると、``before``を使用して全ての　　　|
|                      |テスト項目に条件を満たすランダムな値を設定することができる。　　　　|
|bundle install        | 要                                                           | 
|個別インストール        | 不要                                                         |
|設定変更               | 不要                                                         |  

## 実装方法  
⑴``Gemfile``の``group :devekopment, :test do ～ end``内に以下のように追記する。  
```bush
  gem "faker"
```  
⑵アプリケーションのディレクトリへ移動し、ターミナルで以下のコマンドを順に実行する。  
  ```bush
  bundle install  
  ```  
## 使用方法  
⑴``Faker``を使用してランダムな値を生成したい部分に以下のように記述する。  
※モジュールは頭文字大文字のアッパーキャメルケースで記述する。
```ruby
Fakwe::モジュール.対応するメソッド
```
## モジュールとメソッド  

|モジュール  |対応メソッド　　　　                   |
|:---------:|:-----------------------------------:|
|Name       |first_name ``名字``                   |                        
|           |last_name ``氏名``                    |                              
|           |full_name ``フルネーム``               |                             
|           |initials(number: 文字数) ``イニシャル`` |                                                               
|Address    |city ``都市名``                        |                                 
|           |srteet_address ``住所``                |                
|           |zip_code ``郵便番号``                  |
|Internet   |email ``メールアドレス``                |                                                           
|           |url ``URL``                            |                                                               
|           |username ``ユーザー名``                 |
|Company    |name ``会社名``                         |
|           |industry ``業界名``                     |
|           |catch_phrase ``キャッチフレーズ``        |
|Lorem      |word ``単語``                           |
|           |sentence ``文章``                       |
|           |paragraph ``段落``                      |
|PhoneNumber|phone_number ``電話番号``               |
|           |cell_phone ``携帯電話番号``              |
|Date       |birthday ``誕生日``                     |
|           |foward ``現在から指定日数後の日付``       |
|           |backward ``現在から指定日数前の日付``     |

## 関連ワード  
●``FactoryBot``
