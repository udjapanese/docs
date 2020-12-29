---
layout: relation
title: 'punct'
shortdef: 'punctuation'
udver: '2'
---

記号が依存関係において保持される場合，節内の[記号 (punctuation)](/u/pos/PUNCT.html)に関係`punct`が用いられる．ただし，[SYM](/u/pos/SYM.html)によってタグ付けされるシンボルは記号 (punctuation) とは区別されるので，関係`punct`によって付加させることができない．

~~~ sdparse
Go home !
punct(Go, !)
~~~

関係[u-dep/punct]()にあるトークンは常に内容語 (省略 (ellipsis) されたものを除く) に付加され，それは依存部 (dependents) を持たない．`punct`は通常の依存関係にないため，主辞を決定する通常の規則が適用できない．かわりに，次の原則に従うことにする:

1. 等位関係を形成するユニットを分離する記号は後続要素に付加される.
2. 依存部ユニットに先行/後続する記号は，そのユニットに付加される．
3. 関連するユニット内で，記号は投射性 (projectivity) が保持できる最も上位にあるノードへ付加される．
4. 記号 (e.g. 引用符，括弧，ダッシュ，カンマその他) のペアは，投射性が保たれるならば同一の語へ付加される．その語とは，通常記号ペアに囲まれた句の主辞である．

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

<div id="punct2" class="sd-parse">
Der Mann , den Sie gestern kennengelernt haben , kam wieder .
punct(kennengelernt, ,-3)
punct(kennengelernt, ,-9)
punct(kam, .)
</div>

<div id="punct3" class="sd-parse">
A.K.A. , AKA , もしくは a\/k\/a は“ Also known as ”を指す; 偽名や変名などを表すのに用いられる (“ formerly known as ”のf.k.a. と比較)
punct(AKA, ,-2)
punct(a/k/a, ,-4)
punct(refer, :)
punct(known-13, “-11)
punct(known-13, ”-15)
punct(used, ,-16)
punct(aliases, ,-21)
punct(etc., ,-23)
punct(Compare, (-25)
punct(Compare, )-35)
punct(known-31, “-29)
punct(known-31, ”-33)
punct(Compare, .-34)
</div>

他の例は[並置 (parataxis)]() を参照されたい．
