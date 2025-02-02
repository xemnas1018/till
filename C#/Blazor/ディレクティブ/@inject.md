# @inject(インジェクト)  

## 使用箇所  
* 予め定義しておいたサービスを使用したい部分
  
## 解説  
* コンポーネントが直接インスタンスを生成せず、予め登録されたサービスを自動的に取得するためのディレクティブ。
  
* サービスの注入とも呼び、コンポーネント間の結合度を低く保ちコードの再利用性やテスト容易性を向上させる。 

* 異なる環境やテストシナリオに応じて注入するサービスを切り替えることも可能で柔軟な対応が可能。  
  
## 雛形   
```C#
　// サービスが提供する機能を定義(インターフェイス)
  public interface IMyService
  {
    データ型　メソッド名();
  }

  // インターフェイスで定義されたメソッドを実装する(実装クラス)
  public class MyService : IMyService
  {
    public データ型 メソッド名()
    {
      // 実際の処理内容
    }
}
  @inject IService servise

```
## 関連ワード  
