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

<!--現行の基本的なタグつけスキームでは，先頭の接続要素における依存部と，等位接続全体で共通する依存部を区別することができない．
Note that the current basic annotation scheme cannot distinguish between a dependent of the first conjunct
and a shared dependent of the whole coordination:-->

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

さらに，拡張表示は等位接続の親 (parent) と各要間の関係を捉えることができる．
Furthermore, the enhanced representation can also capture the relation of each conjunct
to the parent of the coordination. Nevertheless, the effective parents can be found
algorithmically and showing them explicitly is for convenience only, while
the information about shared dependents is otherwise not available.

~~~ sdparse
I saw that he met her at the station and kissed her .
conj(met, kissed)
nsubj(met, he)
nsubj(kissed, he)
ccomp(saw, met)
ccomp(saw, kissed)
~~~

If a dependent is shared among conjuncts, the basic representation always links it to the
first conjunct (coordination head), while the enhanced representation shows all dependencies.
In the following example, relations that are only part of the enhanced representation are shown in red.

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

### Nested Coordination

Note further that the basic annotation scheme has only a limited capability to capture nested coordination
such as _apples and pears or oranges and lemons._
Consider coordinations

* A, B, C
* (A, B), C
* A, (B, C)

The first two cases, i.e. (A, B, C) and ((A, B), C), lead to the same tree:

~~~ sdparse
A B C
conj(A, B)
conj(A, C)
~~~

Only the right-nesting case (A, (B, C)) can be distinguished because its tree is different:

~~~ sdparse
A B C
conj(B, C)
conj(A, B)
~~~
