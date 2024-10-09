# attr_reader(アトリビュート・リーダー)  
## 解説  
* インスタンス変数の値を読み取る為のメソッドを自動生成するメソッド。    
  
* クラス内のインスタンス変数を定義した後に、定義されたインスタンス変数を呼び出すメソッドを
  定義する必要がなくなる為、記述量の削減につながる。
>[!TIP]
>メソッドの後ろに記述するのは定義したインスタンス名であり、複数定義されている場合は`,`で区切り全て記述すること。
  
## 雛形   
```ruby
# attr_reder使用時
class Book
  attr_reader :title,:price
  def initialize(title,price)
    @title = title
    @price = price
  end
end

book = Book.new("漫画","400円")
puts book.title
puts book.price

# attr_reder未使用時
class Book
  attr_reader :title,:price
  def initialize(title,price)
    @title = title
    @price = price
  end
  def title
    @title
  end
  def price
    @price
  end
end

book = Book.new("漫画","400円")
puts book.title
puts book.price

```
## 関連ワード  
