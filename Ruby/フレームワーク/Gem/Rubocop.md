# Rrubocop(ルボコップ)  
|利用可能フレームワーク | RubyonRails                                                   |  
|:---------------------|:---------------------------------------------------------------|
|用途                  |●Rubyの静的コード解析ツールで「インデントが揃っていない」                    |
|                      |「余分な改行・スペースがある」などの指摘をRubyStyleGuidに基づいて行ってくれる|
|                      | ●Rubocopの導入でレビューに掛かる時間を減らし、コード品質の担保ができるようになる。　　　　                     |
|bundle install        | 要                                                           | 
|個別インストール        | 要                                                         |
|設定変更               | 要                                                           |  

## 実装方法  
⑴`Gemfile`の`group :devekopment do ～ end`内に以下のように追記する。  
```bush
  gem "rubocop",require: false
```  
⑵アプリケーションのディレクトリへ移動し、ターミナルで以下のコマンドを順に実行する。  
  ```bush
  bundle install
  touch .rubocop.yml
  ```  
⑶アプリケーションのディレクトリに`.rubocop.yml`が作成されていることを確認する。    
  
⑷`.rubocop.yml`内に設定用コードを手動で記述する。  
>[!TIPS]
>コードが非常に長いため、導入時に検索し、コピペすることを推奨する。

⑸Rubocopを実行する際は以下のコマンドをターミナルから実行する。  
>[!NOTE]
>コードレビューを依頼する前にRubocopを実行すること。
  ```bush
  # Rubocopの実行コマンド
  bundle exec rubocop
  ```
  ```bush
  # Rubocopの実行+check内容自動修正コマンド
  bundle exec rubocop -a
  ```

## 関連ワード  
無し
