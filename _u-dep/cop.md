---
layout: relation
title: 'cop'
shortdef: 'copula'
udver: '2'
---

`cop` (コピュラ) は，主語と動詞以外の述語を連結するのに用いられる関係を指す．コピュラは動詞であることが多いが，動詞以外 <!--(-pronominal 代名詞)--> のコピュラを多く使用する言語もある．コピュラ動詞は，`VERB`ではなく[AUX]()とタグ付けされる．そして，代名詞コピュラは[PRON]()もしくは[DET]()が付与される．

関係`cop`は述語の意味にTAMEカテゴリを加えるような純粋なコピュラに対してのみ用いるべきであり，大抵の言語は最大1つのコピュラしか持たないことになる．そして，`cop`は動詞以外の述語が節の主辞であるような場合にのみ適用するべきである．

具体的に言えば，西欧言語の多くでは英語の_to be_に相当するものだけが関係`cop`として生起できる．スペイン語や，それに関連する言語においては，_ser_と_estar_の両方がコピュラとなる．チェコ語や，それに関連する言語においては，_být_ と _bývat_ の両方がコピュラとなる (これらは同じ語彙素 (lexeme) の異形態である．2つの語が見出し語 (lemma) として認定されるのは，チェコ語等においてアスペクト関連の形態論 (aspect-related morphology) が派生形態論として扱われるからである.)
対照的に，_to become_に相当する表現は伝統文法とは異なりコピュラとしては扱われない. 存在の_to be_は，等価を表す節で用いられる動詞と同一である場合に限り，コピュラとして扱われる _(John is a teacher)_. ある言語内で異なる2つの動詞を用いる場合，存在を表す動詞はコピュラとしては扱われない．このトピックに関する義議論は [here](https://universaldependencies.org/v2/copula.html#guidelines-for-udv2) にアーカイブされている.

~~~ sdparse
Bill is honest
nsubj(honest, Bill)
cop(honest, is)
~~~

~~~ sdparse
Ivan is the best dancer
nsubj(dancer-5, Ivan-1)
cop(dancer-5, is-2)
det(dancer-5, the-3)
amod(dancer-5, best-4)
~~~

コピュラの*be*ではなく，上記に示した動詞以外の述語が節の主辞として扱われる.

そのような分析は，以下のロシア語の例で示すように，多くの言語では明示的なコピュラを頻繁に，もしくは常に欠くという事実によって動機づけられる:

~~~ sdparse
Ivan lučšij tancor \n Ivan best dancer
nsubj(tancor, Ivan)
amod(tancor, lučšij)
~~~

インフォーマルな英語でもコピュラの省略が起こる.

~~~ sdparse
Email usually free if you have Wifi.
nsubj(free, Email)
~~~

同一のコピュラが用いられる (もしくはコピュラを欠く) とした場合，述語が前置詞であってもこの分析は適用される．そのようなケースでは，前置詞句の名詞部分が節の主辞となる．

~~~ sdparse
Sue is in shape
nsubj(shape, Sue)
cop(shape, is)
case(shape, in)
~~~

<!--元々コメントアウトの部分
A parallel can also be drawn to so-called raising-to-object or small clause constructions in English.
Under the basic analysis proposed for SD, the predicate complement is
not linked to its subject argument, but in the enhanced representation
(see below), the linkage is then parallel to the treatment in a zero
copula language:

~~~ sdparse
I judge Ivan the best dancer
nsubj(judge-2, I-1)
obj(judge-2, Ivan-3)
xcomp(judge-2, dancer-6)
det(dancer-6, the-4)
amod(dancer-6, best-5)
nsubj(dancer-6, Ivan-3)
~~~
-->

コピュラが他の助動詞を伴う (時制やアスペクトといった要素を表す) 場合，それらに対しては平板構造 (flat structure) が与えられ，語彙的述語の依存部として扱われる:

~~~ sdparse
Sue has been helpful
nsubj(helpful, Sue)
cop(helpful, been)
aux(helpful, has)
~~~

この方略を採る動機として，この構造が動詞に伴う補助動詞に対する説明と平行的であることがある. 特に英語といった言語においては，分詞を動詞か形容詞のどちらとして扱うかが困難である．以下の文は，そのような事例に相当する:

~~~ sdparse
The presence of troops will be destabilizing .
nsubj(destabilizing, presence)
cop(destabilizing, be)
aux(destabilizing, will)
~~~

このような事例であっても品詞を同定する必要が生じるが，品詞の選択によって依存構造が変わることは望ましくない．ただし，コピュラ構文の正確な分布は言語によって変異を見せることに注意されたい．

動詞以外のコピュラが節の形式を取るとき，関係`cop`は用いられない.この形式は以下の例のような等価構文 (equational construction) において頻繁に生起する:

~~~ sdparse
The important thing is to keep calm .
ccomp(is, keep)
nsubj(is, thing)
~~~

~~~ sdparse
The problem is that this has never been tried .
ccomp(is, tried)
nsubj(is, problem)
~~~

コピュラ動詞ではなく節の述語を主辞としたとき，その文は2つの主語を持つことになるため，この方略は効果的でない．上記の例だと先頭の名詞句を述語として分析*できるかもしれない*が，この解決策が望ましいとは言えず，*be*の左右両方に節が存在する例を説明することができない: *(For us) to not attempt to solve the problem is (for us) to acknowledge defeat*.
(注意: この解決策は完璧なものではないので，これを改良することが今後の方針として考えられる．)