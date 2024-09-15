# eq(イーキュー)  
## 解説  
●``expectの引数``と``eqの引数``が等しいことを確認するmatcher。  

●計算結果や処理結果が想定したものと同じになるか確認する際などに使用できる。

## 雛形 
```ruby
describe "テストを行う機能"
  it "テスト条件" do 
    expect(テスト対象の引数).to.eq(比較対象の引数)
  end
end
```
## 関連ワード  
●``matcher``
●``expect``
