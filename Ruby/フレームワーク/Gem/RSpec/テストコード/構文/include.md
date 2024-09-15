# include(インクルード)  
## 解説  
●``expectの引数``に``includeの引数``が含まれていることを確認するmatcher。  

●処理の結果に特定のメッセージや値を含むか確認する際などに使用できる。

## 雛形 
```ruby
describe "テストを行う機能"
  it "テスト条件" do 
    expect(テスト対象の引数).to.include(検索対象の引数)
  end
end
```
## 関連ワード  
●``matcher``
●``expect``
