# describe(ディスクライブ)  
## 用途  
どの機能に対してのテストを行うかテストコードのグループ分けを行う。  
「do~end」内に「describe」を記述することで入れ子にすることが可能。 
## 記述例  
```ruby
  RSpec.describe テスト対象MVC名称, type: :テスト対象MVC種類 do
    describe "テスト対象機能名称(一目でわかる名前にする)" do
      テストコード  
    end  
  end
 ```
## 関連ワード  
●「it」　　
