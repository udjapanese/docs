---
layout: relation
title: 'orphan'
shortdef: 'orphan'
udver: '2'
---
関係'orphan'は，主辞の[省略 (ellipsis)](http://universaldependencies.org/u/overview/specific-syntax.html#ellipsis) のうち，単純な昇格 (promotion) だと不自然で誤解を招くような依存関係について用いられる．典型例として，必須項 (core argument) が節主辞へ昇格するような述語 (predicate) の省略がある．

~~~sdparse
Marie won gold and Peter bronze
nsubj(won, Marie)
obj(won, gold)
conj(won, Peter)
cc(Peter, and)
orphan(Peter, bronze)
~~~

上記の例では，主語の_Peter_は2番目の選言肢の主辞位置へ昇格している．目的語_bronze_を主語へ付加することは節の緊密性 (integrity) を保持するために必要な操作であるが，_bronze_は_Peter_の目的語ではないため，[obj]()という通常の関係は誤解が生じる.よって，標準的な付加でないことを示すためにも関係`orphan`が用いられるだろう．対照的に，上記の等位接続詞_and_は省略の有無に関わらず同じ機能を果たすので，通常の関係`cc`が保持される．

更なる議論については，[省略 (ellipsis)](http://universaldependencies.org/u/overview/specific-syntax.html#ellipsis) を参照されたい．
