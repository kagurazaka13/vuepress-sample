# 例外処理に疑問を持て！

前提
---
設計書を見てると機能の目的や要望など、機能に直結するものはしっかりと書かれているものの、じゃあ例外が発生した場合はどうするの？については<font color="HotPink" size=4>書いていない</font>とか <font color="HotPink" size=4>エラーを出してね！</font>とか一言書いてるだけだったりする場合がある。  
設計書にはそう書いてあるからその通りにしちゃお〜！と何も考えずに進めてしまうとどうなるのかをご覧いただこう。。。

## 実装
---
```
・受け取った値を割り算して下さい。
　エラーだったらメッセージ出して下さい。
```
何も考えないで上記の内容を実装するとこんな感じになる。
```java
class Multiplication {
   void doubleMethod(int inNum1, int inNum2){
	   try {
		   int result = num1 / num2;
		   return result;
	   } catch (Exception e) {
		   System.out.println("エラーです！");
		   System.out.println(e);
		   return 0;
	   }
   }
}
```

## 修正
---

## まとめ
---
おわかりいただけただろうか  
何もしていないからと言ってエラーを握りつぶしてしまったり、何も考えないメッセージを表示したりしてしまうと、いざその場所で問題が発生した時に調査に凄く時間がかかってしまうのである。ましてや握りつぶしてしまったらエラー箇所を特定する事すら困難になるのである。
- 例外処理の詳細、挙動が記載されていなかったら設計者に確認する
- 例外処理自体の記載がない場合、設計書を読む際は「ここで何か起きないか？起きた場合は？」をイメージすること、その上で不明な場合は設計者に確認する

自分の実装したものがもしトラブルを起こした時、例外処理の事を意識しているかどうかで解決へ道のりは大きく変化するので、製造の際は注意して取り組みましょう。


![hibiki](https://firebasestorage.googleapis.com/v0/b/type-c1c71.appspot.com/o/UPVvXYIWvpsUa9cu%2FPlTku4Oe8S8BuFTS.jpg?alt=media&token=5ea837f5-bdf4-456e-9fed-e59e435dabcd)
