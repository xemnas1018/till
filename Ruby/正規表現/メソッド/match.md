# match(マッチ)  
## 解説  
* 判定対象となる文字列内に、引数に指定した文字列が含まれているかどうか判定するメソッド。
  文字列が含まれている場合は引数に指定した文字列が`MatchData`オブジェクトとして戻り値として得られる。
  含まれていない場合は、nilが戻り値として得られる。   
  
* `Matchdata`オブジェクトからマッチした文字列等を取り出したい場合は配列の一番初めのデータえお取り出すのと同様の
  形で文字列を取り出すことができる。

>[!CAUTION]
>合致しなかった場合の返り値がnil=無の為、返り値を参照して処理を行う場合、数値や文字列として扱うとエラーが発生する。
>条件分岐で返り値がnilの場合の処理を記述するなど、条件式の記述方法に注意すること。
  
## 雛形   
```ruby
str = "hello, world"
puts str.match(/hello/)[0]
#"hello"が出力される
```
## 関連ワード  
