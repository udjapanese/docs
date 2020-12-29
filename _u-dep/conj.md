---
layout: relation
title: 'conj'
shortdef: 'conjunct'
udver: '2'
---

接続要素 (conjunct) とは，_and_や_or_といった等位接続詞 (coordinating conjunction) で連結した2つの要素間の関係を指すものである．これらの要素は非対称的に扱われる: この関係の主辞は先頭の要素であり，他の全ての要素は関係`conj`に依存する．

~~~ sdparse
Bill is big and honest
conj(big, honest)
~~~

<div id="punct1" class="sd-parse">
We have apples , pears , oranges , and bananas .
obj(have, apples)
conj(apples, pears)
conj(apples, oranges)
conj(apples, bananas)
cc(bananas, and)
punct(pears, ,-4)
punct(oranges, ,-6)
punct(bananas, ,-8)
</div>

等位節の取り扱いは，構成要素が他のタイプであっても同様である:

~~~ sdparse
He came home , took a shower and immediately went to bed .
conj(came, took)
conj(came, went)
punct(took, ,-4)
cc(went, and)
~~~

場合として等位接続は_asyndetic_<!--asyndetic-->であることがあり，接続詞が省略される．カンマや他の句読点記号は典型的に等位要素を限定する．言語によってはAsyndeticな等位接続が頻繁に用いられる，2つの要素間に常に接続詞が生起する言語もある．

~~~ sdparse
Veni , vidi , vici .
conj(Veni, vidi)
conj(Veni, vici)
punct(vidi, ,-2)
punct(vici, ,-4)
~~~

### Shared Dependents and Effective Parents in Coordination

現行の基本タグ付けスキームでは．先頭の接続要素の依存部と等位接続全体で共有される依存部とを区別できないことに注意したい．

~~~ sdparse
He met her at the station and kissed her .
conj(met, kissed)
nsubj(met, He)
~~~

vs.

~~~ sdparse
He met her at the station and she kissed him .
conj(met, kissed)
nsubj(met, He)
nsubj(kissed, she)
~~~

対照的に，拡張表示 (enhanced representation) によって依存関係を追加することで，1つ目の例における_he_が_kissed_の主語であることもエンコードできる:

~~~ sdparse
He met her at the station and kissed her .
conj(met, kissed)
nsubj(met, He)
nsubj(kissed, He)
~~~

さらに，拡張表示は等位接続の親 (parent) と各要間の関係を捉えることができる．ただし，実際の親は手続き的に発見されることもあり，それを明示することは便宜上のものにすぎない．一方で，共有された依存部に関する情報は拡張表示を用いなければ示すことができない．

~~~ sdparse
I saw that he met her at the station and kissed her .
conj(met, kissed)
nsubj(met, he)
nsubj(kissed, he)
ccomp(saw, met)
ccomp(saw, kissed)
~~~

依存部が等位要素間で共有される場合，基本表示は常に最初の要素 (等位接続の主辞) へと結合させる一方，拡張表示は全ての依存関係を示す．以下の例では，拡張表示でしか形成されない関係が赤色で示される．

~~~ conllu
# visual-style 6 1 amod color:red
# visual-style 4 3 amod color:red
# visual-style 6 3 amod color:red
1 American   _ _ _ _ 4 amod 6:amod        _
2 and        _ _ _ _ 3 cc   _             _
3 British    _ _ _ _ 1 conj 4:amod|6:amod _
4 professors _ _ _ _ 0 root _             _
5 and        _ _ _ _ 6 cc   _             _
6 students   _ _ _ _ 4 conj 0:root        _
~~~

### 等位接続のネスト

基本的なタグ付けスキームでは，_apples and pears or oranges and lemons._といったネストした等位構造に対しては非常に限られた分析しか与えることができない．例えば，次の等位構造を考えてみたい

* A, B, C
* (A, B), C
* A, (B, C)

1番目と2番目の場合 (i.e. (A, B, C)， ((A, B), C)) は同じツリーとして表示される．

~~~ sdparse
A B C
conj(A, B)
conj(A, C)
~~~

右側にネストする場合 (A, (B, C)) はツリーが異なるため，これに限って他と区別が可能となる．

~~~ sdparse
A B C
conj(B, C)
conj(A, B)
~~~
