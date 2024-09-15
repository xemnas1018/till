# include(インクルード)  
## 解説  
●``expectの引数``に``includeの引数``が含まれていることを確認するmatcher。

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
