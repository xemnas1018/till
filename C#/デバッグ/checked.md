# checked(チェックド)  

## 解説  
* 算術演算におけるオーバーフローを検出し、例外を発生させるための仕組み。
>[!NOTE]
>オーバーフロートは、数値型変数に格納可能な値の範囲を数値が超過してしまうこと。

  
* オーバーフローを検知すると`OverflowException`例外がスローされる。
    
## 雛形   
```C#
  int a = int.MaxValue;
  int b = 1;

//オーバーフローを検知し、例外がスローされる
checked
{
  int c = a + b;
  Console.WriteLine(a);
}
```
## 関連ワード  
