---
layout: relation
title: 'obj'
shortdef: 'object'
udver: '2'
---

動詞の目的語 (object) は，主語に後続する，動詞の2番目の必須項 (core argument) である．目的語は典型的に，行為を受けたり，状態変化もしくは動作を経験するような事物を表す (プロト被動作主)．

~~~ sdparse
She gave me a raise
obj(gave, raise)
~~~

形態 [cases](u-feat/Case) を区別する言語において，目的語は対格 (accusative case) として標示される．ただし，動詞の原子価 (verb valency) は，以下のドイツ語の例が示すように与格 (dative case) といった，他の形式を取るように指定する場合がある:
~~~ sdparse
jemandem begegnen \n someone.Dat to-meet
obj(begegnen, jemandem)
~~~

一般的に，目的語が1つだけ生起する場合，それは形態格や意味役割の種類に関わらず`obj`としてラベル付けされる．2つ以上の目的語が存在する場合，1つは`obj`，もう1つは [iobj]() となる．そのような事例では，どれが最も影響を受けた目的語 _(patient)_ なのかを決定する必要がある．

<!--以下，元々コメントアウト
The one exception is when there is a clausal complement. 
Then the clausal complement is regarded as a “clausal object” and an object nominal will be an [iobj]().-->

目的語を複数とる構文に関するさらなる議論は，[iobj]() のページにある．可能なら，1番目の (もしくは直接) 目的語を同定させるような言語固有のドキュメンテーションがあることが望ましい．