# case文(ケースぶん)  
## 解説  
* 複数の条件を評価し、それに応じた処理を分岐させるための構文。    
  
* `if文`でも複数条件の分岐は可能だが、`case文`を使用するとより簡潔に複雑な条件分岐を記述できる。  
  
## 雛形   
```ruby
case 評価される値
when 条件1
  条件1が真の場合に実行される処理
when 条件2
  条件2が真の場合に実行される処理
else
  どの条件にも合致しない場合に実行される処理(省略可)
end
```
## 関連ワード  
* `if文`
