# if文(イフぶん)  
## 解説  
* 条件分岐を行う構文。()内の条件に合致した場合に{}内の処理を行う。

* {}内の各行末尾以外に`;`をつけてはいけない。

* 処理内容が一行のみの場合は{}は省略することもできる。  
  
* if文のスコープは、ブロック外部で宣言された変数等をブロック内部で使用可だが、
  ブロック内部で宣言された変数等をブロック外部で使用することはできない。
  
## 雛形   
```C#
if (条件式1)
{
  条件式1に合致した場合に実行される処理;
}
else if (条件式2)
{
  条件式1に合致せず、条件式2に合致した場合に実行される処理;
}
else
{
  いずれの条件式にも合致しない場合に実行される処理;
}

```
## 関連ワード  
