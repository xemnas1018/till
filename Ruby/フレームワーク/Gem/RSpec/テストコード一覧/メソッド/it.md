# it(イット)  
## 用途  
「describe」同様にグループ分けを行うメソッド。  
「describe」メソッドに記述した機能においてどのような状況のテストを行うかを明記する。  
「it」で分けたグループ及び「it」に記述した内容を「example(イグザンプル)」とも呼ぶ。  
## 記述例  
```ruby
RSpec.describe テスト対象MVC名称, type: :テスト対象MVC種類 do
  describe "テスト対象機能名称(一目でわかる名前にする)" do  
    it "テストする状況" do  
       テストする状況を再現するテストコード  
    end  
  end
end  
```
##関連ワード
●describe
