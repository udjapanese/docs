---
layout: relation
title: 'advcl'
shortdef: 'adverbial clause modifier'
udver: '2'
---

副詞節を成す修飾句 (adverbial clause modifier) は動詞や他の述語 (形容詞など) を修飾する節であり，必須の補部 (core complement) ではなく，修飾句としてふるまう．これには時間を示す節 (temporal clause)，帰結節 (consequence)，条件節 (conditional clause)，目的節 (purpose clause) といったものが含まれる．依存部 (dependet) には必ず節 (もしくは [advmod]() であるもの) をとり，依存部は節の主述語 (main predicate) である．

~~~ sdparse
The accident happened as night was falling
advcl(happened, falling)
~~~

~~~ sdparse
If you know who did it, you should tell the teacher
advcl(tell, know)
~~~

~~~ sdparse
He talked to him in order to secure the account
advcl(talked, secure)
~~~

~~~ sdparse
He was upset when I talked to him
advcl(upset, talked)
~~~
