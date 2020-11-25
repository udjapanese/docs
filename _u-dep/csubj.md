---
layout: relation
title: 'csubj'
shortdef: 'clausal subject'
udver: '2'
---

節主語 (clausal subject) とは，節の統語的な主語を指す．すなわち，主語それ自身が節となるようなものである．この関係の支配項 (governor) はいつでも動詞だとは限らない：動詞がコピュラ動詞であるとき，節の根 (root) はコピュラ動詞の補部となる．このときの依存部は主動詞や，主節における他の述語である．以下の例にある*what she said* (すなわち *said*) は，それぞれ*makes*と*interesting*の節主語となる．

**v2から:** 関係`csubj`は動詞の受身形や特定の動詞グループにも用いられるようになった．そのとき，文法化した受動変形が起きる言語においては，サブタイプの`csubj:pass`を用いることが強く推奨される．

~~~ sdparse
What she said makes sense
csubj(makes, said)
~~~

~~~ sdparse
What she said is interesting
csubj(interesting, said)
~~~

~~~ sdparse
What she said was well received
csubj:pass(received, said)
~~~
