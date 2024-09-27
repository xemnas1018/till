# ActiveHash(アクティブハッシュ)  
|利用可能フレームワーク | RubyonRails                                                   |  
|---------------------|---------------------------------------------------------------|
|用途                  |* 都道府県名や商品カテゴリー等の変更されないデータをモデルファイル内に|
|                      |  直接記述することでデータベースに保存せずデータを取り扱うことができるGem |
|                      |* 文字を入力せずプルダウンで選択するタイプのフォームがこれに当たる。　  |
|bundle install        | 要                                                           | 
|個別インストール        | 不要                                                         |
|設定変更               | 要                                                           |  

## 実装方法  
⑴`Gemfile`の末尾に以下のように追記する。  
```bush
  gem "activ_hash"
```  
⑵アプリケーションのディレクトリへ移動し、ターミナルで以下のコマンドを順に実行する。  
  ```bush
  bundle install  
  ```  
⑶`rails g  model`コマンドを実行し、通常のモデルとActiveHashのデータを書き込む専用モデルを作成する。  
>[!TIP]
>* RubyonRailsのモデルとは異なる為、ActiveHash以外の運用に使用することはできない。
>  厳密にいうとActiveHashを用いて実装するクラスを作成している。
>* この専用モデルは実装したいカテゴリーの種類分用意する必要がある。
>  (都道府県と商品カテゴリーを実装したいなら、それぞれ1つずつ専用モデルの作成が必要。?)
  
  
⑷作成した専用モデルを以下のように記述する。  
```ruby
class モデル名 < ActiveHash::Base
 self.data = [
   { id: 1, name: '---' },
   { id: 2, name: 'カテゴリー名' },
   # 実装したいカテゴリーの数だけ記述する。
 ]
 end
```

⑸ActiveHashを適用したい通常モデルのマイグレーションファイルを以下のように編集する。  
```ruby
   create_table :通常モデル名 do |t|
     # 通常モデルで使用するカラムデータを記述
     t.integer    :専用モデル名_id     , null: false
     # 専用モデルに記述したカテゴリーを取得する。
     t.timestamps
   end
```

⑹データベースのマイグレーションを実施する。
```bush
rails db:migrate
```
⑺ActiveHashを適用したい通常モデルに以下のようにアソシエーションを設定する。
```ruby
class 通常モデル < ApplicationRecord
  extend ActiveHash::Associations::ActiveRecordExtensions
  belongs_to :専用モデル名
end
```
⑻専用モデルに以下のようにアソシエーションを設定する。  
```ruby
  include ActiveHash::Associations
  has_many :通常モデル名
```

⑼データベースに空の投稿が保存されないようにバリデーションを以下のように設定する。
```ruby
 #空の投稿を保存できないようにする
  validates :title, :text, presence: true

  #ジャンルの選択が「---」の時は保存できないようにする
  validates :genre_id, numericality: { other_than: 1 } 
```

## 関連ワード  
●``Faker``
