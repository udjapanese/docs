---
layout: relation
title: 'nsubj'
shortdef: 'nominal subject'
udver: '2'
---

名詞句主語 (`nsubj`) は，節の統語的主語やプロト行為者 (proto-agent) を表す名詞句を指す．名詞句主語はすなわち，主語性 (subjecthood) に関する典型的な文法テストに合格するような節の場所に位置し，この項は行為性 (agentive) が高く，行為者であったり節のプロト行為者であったりする．この名詞句の主辞となるのは，名詞，もしくは代名詞や関係代名詞，または省略 (ellipsis) が起きる文脈では形容詞といったものが該当する．

**New from v2:** 動詞が受身形を表し，原子価 (valency) が変更されたことで主語が典型的にプロト行為者を表さない場合であっても，その名詞句主語には関係`nsubj`が用いられる．文法化した受動変形を有する言語においては，上記の事例に対して，`nsubj`のサブタイプ`nsubj:pass`を用いることが強く推奨される．

関係`nsubj`の支配項 (governor) は常に動詞だとは限らない: 動詞がコピュラ動詞 (copular verb) である場合，節の根 (root) はコピュラ動詞の補部であり，形容詞，および前置詞で修飾されたものを含む名詞となる．これは，以下の例から示される．

`nsubj`の役割は述語の意味項に対してのみ適用される．文法的な主語位置に空の項 (empty argument) が存在する (この要素は虚辞 (expletive) と呼ばれることがある) とき，それは [expl]() としてラベル付けされる．英語における，存在を表す_there_構文のように，分離 (displaced) した主語が存在する節においては，主語は`nsubj`としてラベル付けされる．

~~~ sdparse
Clinton defeated Dole
nsubj(defeated, Clinton)
~~~

~~~ sdparse
Dole was defeated by Clinton
nsubj:pass(defeated, Dole)
~~~

~~~ sdparse
The car is red .
nsubj(red, car)
~~~

~~~ sdparse
Sue is a true patriot .
nsubj(patriot, Sue)
~~~

~~~ sdparse
We are in the barn .
nsubj(barn, We)
~~~

~~~ sdparse
Agatha is in trouble .
nsubj(trouble, Agatha)
~~~

~~~ sdparse
There is a ghost in the room .
expl(is, There)
nsubj(is, ghost)
~~~

~~~sdparse
These links present the many viewpoints that existed .
acl(viewpoints, existed)
nsubj(existed, that)
~~~

