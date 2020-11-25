---
layout: relation
title: 'acl'
shortdef: 'clausal modifier of noun (adjectival clause)'
udver: '2'
---

`acl`は，名詞を修飾する定型/非定型節 (finite/non-finite clauses) を表す. 関係`acl`は関係 [advcl]() と対照を成し，後者は述語 (predicate) を修飾する副詞節に用いられる．関係`acl`の主辞 (head) は被修飾名詞であり，依存部 (dependent) は名詞を修飾する節の主辞である．

~~~ sdparse
the issues as he sees them
acl(issues, sees)
~~~

~~~ sdparse
There are many online sites offering booking facilities .
acl(sites, offering)
~~~

~~~ sdparse
I have a parakeet named cookie .
acl(parakeet, named)
~~~

~~~ sdparse
I just want a simple way to get my discount .
acl(way, get)
~~~

~~~ sdparse
Cette affaire à suivre \n This case to follow 
acl(affaire, suivre)
~~~

この関係は付随的な描写 (optional depictives) としても用いられ，形容詞が名詞を修飾し，二次述語 (secondary predication) として働く．結果構文 (resultatives) や描写構文 (depictives) のさらなる議論については [xcomp]() を参照されたい．

~~~ sdparse
She entered the room sad
acl(She, sad)
~~~

~~~ sdparse
He painted the model naked
acl(model, naked)
~~~

関係節 (relative clause) は`acl`のインスタンスであり，定性 (finiteness) および埋め込み節における被修飾名詞の省略によって特徴づけられる．いくつかの言語では，伝統的な関係節のクラスにおける下位クラスとして`acl:relcl`を設けることがある．

~~~ sdparse
I saw the man you love
acl:relcl(man, love)
~~~

言語によっては，*fact* もしくは *report* といった名詞のサブセットに対する定型節の補部 (complements) を許す．これらは概して関係節のようにふるまうが，依存部節内には省略要素が存在しない．これはHuddleston and Pullum 2002における"内容節 (content clauses)"に該当するものであり，`acl`として分析される.

~~~ sdparse
the fact that nobody cares
acl(fact, cares)
~~~
