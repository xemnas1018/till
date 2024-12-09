# dataset(データセット)  
## 解説  
* HTML要素に埋め込まれたカスタムデータを取得するためのプロパティ。    
  
* HTML要素に埋め込まれているカスタムデータ`data-情報名`の場合、`document.dataset.情報名`と記述することで取得可能。

* `addEventListener`メソッド等と組み合わせ、documentを`this`に設定することでイベント発火した要素のカスタムデータを取得することができる。
  
## 雛形   
```js
document.dataset.情報名

# イベント発火した要素のカスタムデータを取得する
document.addEventListener(イベント名, function() {
  this.dataset.情報名;
});
```
## 関連ワード  
