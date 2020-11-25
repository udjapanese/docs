---
layout: relation
title: 'case'
shortdef: 'case marking'
udver: '2'
---

関係`case`は格を付与する要素を指し，個別の統語要素 (前置詞，後置詞，および接語である格マーカーを含む) として扱われるものに該当する. 格付与要素は名詞の依存部 (dependents) として扱われ，名詞へ付加したり名詞を導入したりする．(ゆえに，SD<!--SDって何?-->とは逆に，UDでは被修飾語と目的語を媒介する要素としてみなす見方を退ける) 関係`case`は，名詞的要素，前置詞および形態論が豊富な言語における格に対して統一的な分析を与えることを志向している: 斜格 (oblique case) の名詞句は側置詞から導入される名詞句と同一の依存構造を持つ.

~~~ sdparse
the Chair 's office
det(Chair-2, the-1)
nmod(office-4, Chair-2)
case(Chair-2, 's-3)
~~~

~~~ sdparse
the office of the Chair
det(office-2, the-1)
nmod(office-2, Chair-5)
case(Chair-5, of-3)
det(Chair-5, the-4)
~~~

French:

~~~ sdparse
le bureau du président \n the office of the_Chair
det(bureau, le)
nmod(bureau, président)
case(président, du)
~~~

Hebrew:

~~~ sdparse
hwa/PRON rah/VERB at/PART[Case=Acc] h/DET klb/NOUN \n he saw ACC the dog  
obj(rah-2, klb-5)
case(klb-5, at-3)
~~~


格マーカーが形態素である場合，格の依存部 (case dependet) の独立した要素として名詞を分離することができず，(述語の依存部であるならば) 名詞全体が [obl]() として分析され，もしくは (名詞の依存部であるならば) [nmod]() として分析される．明示的に格を標示するには，
<a href="../pos/index.html">POSタグ</a> と
<a href="../feat/index.html">素性</a>
といった情報が用いられ，それは以下のロシア語の例から示される．
(追加の統語形態論的素性を参照するには，当該の語にマウスを重ねること.)

~~~ conllu
# I wrote the letter with a quill.
1   Я         ja         PRON   _   Case=Nom|Number=Sing|Person=1|PronType=Prs        2   nsubj   _   I
2   написал   napisat'   VERB   _   Gender=Masc|Number=Sing|VerbForm=Part|Voice=Act   0   root    _   wrote
3   письмо    pis'mo     NOUN   _   Case=Acc|Gender=Neut|Number=Sing                  2   obj    _   the-letter
4   пером     pero       NOUN   _   Case=Ins|Gender=Neut|Number=Sing                  2   obl    _   with-a-quill
~~~

このように取り扱うことで，多様な構文間と多くの言語内に対して平行性を与えることができる．(ただし，これらの格において) ここで得られた良い結果として，前置詞句と従属節との間にある平行性を捉えられたことが挙げられる．(ただし，これらの例では関係 [mark]() が用いられる):
<!--A good result is that we now have greater
parallelism between prepositional phrases and subordinate clauses,
which are often introduced by a preposition in some languages (but note that 
the relation should be [mark]() in those cases):-->

~~~ sdparse
Sue left after the rehearsal
nsubj(left-2, Sue-1)
obl(left-2, rehearsal-5)
det(rehearsal-5, the-4)
case(rehearsal-5, after-3)
~~~

~~~ sdparse
Sue left after we did
nsubj(left-2, Sue-1)
advcl(left-2, did-5)
mark(did-5, after-3)
nsubj(did-5, we-4)
~~~

構文の平行的な分析<!--parallel construction-->は，以下のものに対しても与えられる．


- 受動交替 (possessive alternation)

~~~ sdparse
the Chair 's office
det(Chair-2, the-1)
nmod(office-4, Chair-2)
case(Chair-2, 's-3)
~~~

~~~ sdparse
the office of the Chair
det(office-2, the-1)
nmod(office-2, Chair-5)
case(Chair-5, of-3)
det(Chair-5, the-4)
~~~


- フィンランド語における，格，前置詞，もしくは後置詞における異形態 (variant forms)

~~~ sdparse
etsiä ilman johtolankaa \n to_search without clue.PARTITIVE
obl(etsiä, johtolankaa)
case(johtolankaa, ilman)
~~~

~~~ sdparse
etsiä taskulampun kanssa \n to_search torch.GENITIVE with
obl(etsiä, taskulampun)
case(taskulampun, kanssa)
~~~

~~~ sdparse
etsiä johtolangatta \n to_search clue.ABESSIVE
obl(etsiä, johtolangatta)
~~~


- 二重目的語構文の分析が前置詞構文の分析と類似するような与格交替 (dative alternation)

~~~ sdparse
give the children the toys
obj(give, toys)
iobj(give, children)
~~~

~~~ sdparse
give the toys to the children
obj(give, toys)
obl(give, children)
case(children, to)
~~~

~~~ conllu
# give the toys to the children
1     donner    donner   VERB   _   VerbForm=Inf               0   root   _   give
2     les       le       DET    _   Definite=Def|Number=Plur   3   det    _   the
3     jouets    jouet    NOUN   _   Gender=Masc|Number=Plur    1   obj   _   toys
4-5   aux       _        _      _   _                          _   _      _   _
4     à         à        ADP    _   _                          6   case   _   to
5     les       le       DET    _   Definite=Def|Number=Plur   6   det    _   the
6     enfants   enfant   NOUN   _   Gender=Masc|Number=Plur    1   obl   _   children
~~~

この新しい分析を採るもう一つの利点として，"be"の述語補部となる前置詞句への対処法を提供することにある. この分析は名詞述語補部の扱いと一貫している:

~~~ sdparse
Sue is in shape
nsubj(shape-4, Sue-1)
cop(shape-4, is-2)
case(shape-4, in-3)
~~~

前置詞が積み重なる場合 (前置詞が連続するとき)，可能な分析が2つある．前置詞の連続が特定の意味を伴う固定したものである場合，`fixed`が最良の分析法となる．関連する英語の例として *out of* がある:

~~~ sdparse
Out of all this , something good will come .
case(this-4, Out-1)
fixed(Out-1, of-2)
det(this-4, all-3)
obl(come, this-4)
~~~

しかし，前置詞の様々な組み合わせによって異なる意味やニュアンスが表現される場合，各前置詞は格依存部として独立に分析される．関連する英語の例には *up beside* (*down beside* や *up near* と交替可能) や，*as during* もしくは *except after* と交替可能な*except during* が挙げられる．


~~~ sdparse
The cafe up beside the lookout
det(cafe-2, The-1)
case(lookout-6, up-3)
case(lookout-6, beside-4)
det(lookout-6, the-5)
nmod(cafe-2, lookout-6)
~~~
