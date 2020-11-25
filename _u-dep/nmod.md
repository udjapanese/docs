---
layout: relation
title: 'nmod'
shortdef: 'nominal modifier'
udver: '2'
---

`nmod`は他の名詞の依存部である名詞句を表す関係であり，機能的には．この名詞句は属性 (attribute) や，属格の補部 (genitive complement) に相当する．

**New from v2:** 関係 `nmod` は従来，動詞，形容詞や副詞の依存部となる名詞句に対して用いられた．このような関係は，現在では [obl]() という新たな関係によって示される．．

[case]() と同じく，`nmod`は所有交替に対して一貫した分析を提供する (後置修飾をとらないケースと区別するため，`nmod:poss`という選択肢もある):

~~~ sdparse
the office of the Chair
det(office-2, the-1)
nmod(office-2, Chair-5)
case(Chair-5, of-3)
det(Chair-5, the-4)
~~~

~~~ sdparse
the Chair 's office
det(Chair-2, the-1)
nmod:poss(office-4, Chair-2)
case(Chair-2, 's-3)
~~~
