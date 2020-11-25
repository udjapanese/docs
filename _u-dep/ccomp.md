---
layout: relation
title: 'ccomp'
shortdef: 'clausal complement'
udver: '2'
---

動詞もしくは形容詞の節補部 (clausal complement) とは必須項として生起する依存部節を指し，動詞や形容詞の目的語のように機能する．


~~~ sdparse
He says that you like to swim
ccomp(says, like)
mark(like, that)
~~~

~~~ sdparse
He says you like to swim
ccomp(says, like)
~~~

そのような節補部は定型節か非定型節のどちらでもありうる．しかし，節補部の主語がコントロールされる場合 (つまり，上位の節の主語か目的語と同一であり，かつ他の解釈を許さない場合)，適切な関係は [xcomp]() である．

~~~ sdparse
The boss said to start digging
ccomp(said, start)
mark(start, to)
~~~

~~~ sdparse
We started digging
xcomp(started, digging)
~~~

ここでの重要な相違点は，最初の文で上司 (the boss) が掘削をしない解釈が許される一方，2番目の文では _digging_ の主語が明らかに _we_ しか許容されない．これは，`ccomp`と`xcomp`を区別づけるものである．

さらに，`ccomp`は完全な節 (full clauses) が関与する等価構文 (equational constructions) においても用いられる．

~~~ sdparse
The important thing is to keep calm.
ccomp(is, keep)
nsubj(is, thing)
~~~

~~~ sdparse
The problem is that this has never been tried .
ccomp(is, tried)
nsubj(is, problem)
~~~

(これらの例では，節境界の緊密性 (integrity) を保持し，1つの述語が2つの述語に割り当てられることを防ぐため，コピュラが主辞として扱われる．これは，名詞句の一つが主辞として扱われるような等価構文の分析を考えたとき最適な解決策とはいえない．しかし，現行の枠組みでは選好される策である.)

_注意:_ SD/USDの従来のバージョンでは，*fact* や *report*といった名詞の補部節も`ccomp`として分析された．しかし，ここでは[acl]() として分析するため，名詞句には`ccomp`が生起しない．名詞句は通常必須項をとらないため，この扱い方が合理的である．
