



-> # Chap.23 - Diplomatic immunity <-



-> Hidetatsu Yaginuma <-

---




-> # What's Diplomatic immunity? <- 



<br>

```
外交使節とその随員に対して接受国から与えられる特権。
国家の尊厳を維持しかつ職務を有効に遂行するため国家が相互に与えあう。
身体，名誉，館邸，文書，財産に対する不可侵権と，
刑事・民事裁判権，課税権，警察権の免除などの治外法権とからなり，
外交使節の特権および免除とも称される。
```

---




-> # つまり <-



<br>
* 外交官が

<br>
* 外交官の職務において外国にいる際に

<br>
* 様々な特権を持つこと

<br>
例:

<br>

* 逮捕・勾留されない
* プライバシーが守られる

---




-> # 本章におけるDiplomatic immunityとは <-



<br>
データベースアドミニストレータが **特権** を得ること。

---




-> # どんな特権か？ <-



<br>
* ドキュメンテーション

<br>
* テスト

<br>
* バージョン管理

<br>
を **行わなくて良い** という特権。

---




-> # 何故特別扱いされていたのか？ <-



<br>
* ソフトウェアエンジニアとデータベース管理者が区別されており、

<br>
* どのプロジェクトでも「お客さん扱い」されるため

<br>
* SQLをアプリケーションコードとみなさないため

<br>
* データベース管理者が豊富にいないため

<br>
-> => エンジニアに対する **外交官** 的存在 <-

---




-> # ここまでのまとめ <-



<br>
* データベース管理者は **特権** を持っている

<br>
* そのため、 

<br>
 - **ドキュメンテーション** 

<br>
 -  **自動テスト・そのメンテナンス** 

<br>
 - **バージョン管理** 

<br>
* の義務を負わない

<br>
* しかし

<br>
* !!これはアンチパターンである!!

---




-> # 何故アンチパターンなのか？ <-



<br>
* エンジニアリングは **QC(Quality Control 品質管理)** だけでなく、

<br>
* **QA (Quality Assurance 品質保証)** を必要とする

<br>
* データベースの品質保証は 

<br>
 - **文書化**

<br>
 - **バージョン管理**

<br>
 - **テスティング** 

<br>
* に従うことで達成される

<br>
* そのため、特権は許されない

---




-> # データベースのQAを達成するために <-

---




-> ## ドキュメンテーション <-



<br>
* ER図を書く(リレーション定義のため)

<br>
* テーブル定義書を書く(カラム、キー等の説明のため)

<br>
* インフラ仕様書を書く(接続情報等の明文化のため)

<br>

以下本書より引用
```
百戦錬磨のプログラマーでさえ、
ソフトウェアの他の部分は文書化しない場合でも、
データベースを文書化する必要があることを知っています
```

---




-> ## バージョン管理 <-



<br>
* データ定義(マイグレーションファイル)

<br>
* トリガ/プロシージャ

<br>
* シードデータ(あれば)

<br>
* スクリプト(あれば)

<br>
* 作成したドキュメント

---




-> ## テスティング <-



<br>
* テーブル、列、ビューの存在確認

<br>
* 制約違反時にエラーが起こることの確認

<br>
* クエリが正しい結果を返すことの確認

---




-> # アンチパターンを用いても良いケース <-



<br>
* すぐに削除できるような、使い捨てのコードである場合

---




-> # MMM Way <-



<br>
## ドキュメンテーション

<br>
* ER図・テーブル定義など、どこまで書くか？

<br>
* メンテナンスが確実にされるような仕組みはどう作るか？

<br>
## バージョン管理


<br>
* フレームワークレベルでバージョン管理の仕組みが無い限り、
モデルを修正するのみで、バージョン管理はしていないのが現状

<br>
* バージョニングに意味はあるか？
後で「バージョン管理しててよかった」ことってあるのか？

<br>
* マイグレーションのベストプラクティスはなんなのか？

<br>
## テスト


<br>
* テーブルが存在していることのテストは必要なのか？

<br>
* ストアドのテストはまあ必要だと思う(ものにもよるが)

<br>
* ユニークキーがついてること、みたいなテストは必要なのか？

<br>

-> # 議論はじめ <-
