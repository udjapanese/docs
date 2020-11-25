---
layout: relation
title: 'cc'
shortdef: 'coordinating conjunction'
udver: '2'
---

<!--For more on coordination, see the [conj]() relation.-->
`cc`は，接続要素 (conjunct) と先行する [coordinating conjunction](../pos/CCONJ) との関係を表す. 

<!--(Note: different dependency grammars have different treatments of coordination.
We take the first conjunct as the head of the coordination.)-->

~~~ sdparse
Bill is big and honest
conj(big, honest)
cc(honest, and)
~~~

等位接続詞 (coordinating conjunction) は文頭にも現れる場合がある．これは，先行する接続要素がない場合であっても`cc`と呼ばれる．<!--(except implicitly or in a preceding sentence).-->

~~~ sdparse
And then we left .
cc(left, And)
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
