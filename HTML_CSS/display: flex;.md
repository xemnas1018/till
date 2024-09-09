# displayflex  
◎用途：⑴子要素の並びを縦から横並びに変更するプロパティ。  
       ⑵要素配置に関するいくつかのプロパティを有効にする。  
       ⇒柔軟な要素の配置が可能になる。  
例：display: flex;
  
## 有効になるプロパティ  
### justify-content  
◎用途：子要素の水平方向の配置を変更する。  
例：⑴justify-content: center;(左右中央に配置)  
    ⑵justify-content: space-around(要素を均等に配置し各要素の両側に均等な余白を確保)  
    ⑶justify-content: space-between(要素を均等に配置し、最初と最後の要素を両端に配置する)  

### align-items  
◎用途：子要素の垂直方向の配置を変更する。  
例：⑴align-items: center;(上下中央に配置)  
    ⑵align-items: flex-start;(上揃えで配置)  
    ⑶align-items: flex-end;(下揃えで配置)  

### flex-direction  
◎用途：displayflexが適用された子要素を並び替える。  
※このプロパティを使用して立て並びに変更した場合、適用されている子要素の水平方向・垂直方向が逆転する。  
⇒水平方向の配置を変更したい場合は、垂直方向の配置を変更しなければ効果がなくなる。  
例：⑴flex-direction: row;(子要素を左から右に横並びにする)  
    ⑵flex-direction: row-reverse;(子要素を右から左に横並びにする)  
    ⑶flex-direction: column;(子要素を上から下に立て並びにする⇒横並びにする前の状態と同じになる)  
    ⑷flex-direction: column-reverse;(子要素を下から上に立て並びにする⇒横並びにする前と逆の並びになる)
