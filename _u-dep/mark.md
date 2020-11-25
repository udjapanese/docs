---
layout: relation
title: 'mark'
shortdef: 'marker'
udver: '2'
---

マーカー (marker) とは，ある節が別の節の従属節を形成していることを示すような語を指す．[complement clause](ccomp) においては，[en] _that_
や _whether._ といった語に相当する．[adverbial clause](advcl) においては，マーカーは [en] _while_ or _although_ といった [subordinating conjunction](../pos/SCONJ) が典型である．このマーカーは従属節の主辞に対する依存部となる．[relative clause](../overview/complex-syntax.html) でマーカーとなるのは，通常屈折をせず，単に関係節を導入するような [he] _še_. (関係節¥において，`mark`である [en] _who_ or _that_ といった関係節マーカーと，動詞の項や修飾語として働く [en] _who_ or _that_ のような関係代名詞とを区別する必要がある．) といった語である．
~~~ sdparse
Forces engaged in fighting after insurgents attacked
mark(attacked, after)
~~~

~~~ sdparse
He says that you like to swim
mark(like, that)
~~~

不定節 (infinitival clauses) における不定節マーカー (英語の_to_やドイツ語の_zu_など) も，`mark`として付加される．

~~~ sdparse
Er kam wieder , um das Werk zu Ende zu bringen \n He came again , so-that the work to end to bring
mark(bringen, um)
mark(bringen, zu-10)
mark(bring, so-that)
mark(bring, to-22)
~~~
