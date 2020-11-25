---
layout: relation
title: 'aux'
shortdef: 'auxiliary'
# The filename "aux" is not allowed on Windows, so we redirect instead
# (see https://github.com/UniversalDependencies/docs/issues/20)
redirect_from: "u/dep/aux.html"
udver: '2'
---

節の `aux` (補助動詞 (auxiliary) ) とは動詞述語と連結する機能語を指し，時制 (tense)，アスペクト (aspect)，ヴォイス (voice) もしくはエビデンシャリティ (evidentiality) といったカテゴリを表現する．補助動詞は動詞であることが多いが，多数の言語では動詞でないTAMEマーカー<!--TAMEって何？-->を持っており，これらも同様に`aux`のインスタンスとして扱われる．

**New from v2:** 受動の [voice](u-feat/Voice) を構成するのに用いられてきた補助動詞は，現在では`aux`としてラベル付けされる．しかし，文法化した (周辺的な) 受動態を備えた言語においては`aux`のサブタイプである`aux:pass`を用いることが強く推奨される
~~~ sdparse
Reagan has died
aux(died-3, has-2)
~~~

~~~ sdparse
He should leave
aux(leave-3, should-2)
~~~

~~~ sdparse
Do you think that he will have left by the time we come ?
aux(think, Do)
aux(left, will)
aux(left, have)
~~~
