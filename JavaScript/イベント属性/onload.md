# onload(オンロード)  
## 解説  
* HTML文書や画像、リクエスト等、対象のオブジェクトが読み込み完了した時点でイベント発火するイベントハンドラー。    
  
* 読み込み完了 = 動作が正常に完了した時に起動させることができる。

*複数のonloadを記述した場合、後から記述されたものが優先される。  
   
## 雛形   
```js
オブジェクト.onload = function(){
  イベント発火時に実行させたい関数
};
```
## 関連ワード  
