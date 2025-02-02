# Blazor(ブレイザー)  
## 解説  
* C#を使ってWebアプリのフロントエンドを開発できるフレームワーク。

* 開発にはC#とHTMLを組み合わせた`razor(レイザー)`を使用する。

* Blazorを使用するメリット・デメリットは以下のとおりである。
    
|メリット                                                    |デメリット                                                        |
|-----------------------------------------------------------|-----------------------------------------------------------------|
|C#一本でフルスタック開発が可能となり、学習コストが削減される    |ファイルサイズが大きくなる傾向があり初期ロードに時間がかかることがある    |
|.NETの豊富なライブラリやツールを使用可能                      |サポート状況によっては一部のブラウザで動作しない可能性あり               |
|WebAssemblyによりネイティブに近いパフォーマンスを発揮できる    |Blazor Serverはサーバーとの情事接続が必要でありネットワーク環境に依存する|
|Blazor ServerではJavaScriptを使わずにリアルタイムな更新が可能 |大規模なアプリではサーバー負荷が増加する可能性がある                     |

* Blazorでは`ディレクティブ`と呼ばれるRazorコンポーネントの動作を制御したりコンポーネントに特別な機能を追加する専用の構文を用いる。

* Blazorを使用するとViewやUIを自動生成してくれるため、開発労力を削減することができる。

## 関連ワード  
* `ディレクティブ`
