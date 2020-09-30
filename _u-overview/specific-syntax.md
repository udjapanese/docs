---
layout: base
title:  'Other Constructions'
permalink: u/overview/specific-syntax.html
udver: '2'
---

# Other Constructions
本セクションは単文節 (simple clause)，複文節 (complex clause)，および名詞句の主要なカテゴリから漏れる (もしくは境界の) 特定の構文について詳細な議論を行う．

* [等位接続 (Coordination)](#coordination)
* [省略 (Ellipsis)](#ellipsis)
* [複合表現 (Multiword expressions)](#multiword-expressions)
* [比較構文 (Comparative constructions)](#comparatives)
* [並立構文 (Paratactic constructions)](#paratactic-constructions)
* [カンマ (Punctuation)](#punctuation)


## Coordination

[complex clauses](complex-syntax.html) のセクションで議論したように，等位構造は，後続要素を関係 [u-dep/conj]() を介して先頭の要素へと付加することによって非対称的に扱われる．要素を限定する等位接続詞とカンマは，それぞれ関係 [u-dep/cc]() と [u-dep/punct]() を用いて直後の要素に付加する．この分析は節，句，および語のレベルの全ての等位構造に対して適用されるものである．

~~~ sdparse
He came home , took a shower and immediately went to bed .
conj(came, took)
conj(came, went)
punct(took, ,-4)
cc(went, and)
~~~

~~~ sdparse
He read the newspaper and a good book .
conj(newspaper, book)
cc(book, and)
~~~

~~~ sdparse
He read one or two books .
conj(one, two)
cc(two, or)
~~~

<a name="ellipsis"></a>

## Ellipsis

省略 (ellipsis) に対するUDのアプローチは以下のように要約される:

1. 省略要素が顕在的な (overt) 依存部 (dependents) を持たないとき，何もしない．
2. 省略要素が顕在的な依存部を持つとき，それらのうち一つが主辞 (head) の役割を担うように昇格 (promore) させる.
3. 省略要素が述語で，かつ昇格した要素が述語の項か付加詞 (adjuncts) である場合，昇格した主辞へ機能語ではない依存部を付加させる際に関係`orphan`を用いる．

### Ellipsis in Nominals

主辞の名詞句が省略される場合，依存部を次の順に昇格させる: `amod` > `nummod` > `det` > `nmod` > `case`.

例:

~~~ sdparse
Er kauft sich ein grünes Auto und sie kauft sich ein rotes . \n He buys himself a green car and she buys herself a red .

nsubj(kauft-2, Er-1)
det(Auto-6, ein-4)
amod(Auto-6, grünes-5)
obj(kauft-2, Auto-6)
conj(kauft-2, kauft-9)
nsubj(kauft-9, sie-8)
obj(kauft-9, rotes-12)
det(rotes-12, ein-11)
~~~

~~~ sdparse
She saw every animal at the zoo but he saw only some .

nsubj(saw-2, She-1)
det(animal-4, every-3)
obj(saw-2, animal-4)
conj(saw-2, saw-10)
advmod(some-12, only-11)
obj(saw-10, some-12)
~~~

~~~ sdparse
She saw three monkeys and he saw two .

nsubj(saw-2, She-1)
nummod(monkeys-4, three-3)
obj(saw-2, monkeys-4)
conj(saw-2, saw-7)
obj(saw-7, two-8)
~~~

### Ellipsis in Clauses

主述語が省略される場合，不定詞マーカーとなる`aux`，`cop`もしくは`mark`が存在するときに限り単純な昇格を用いる．

例:

~~~ sdparse
Sue likes pasta and Peter does , too .

nsubj(likes-2, Sue-1)
obj(likes-2, pasta-3)
conj(likes-2, does-6)
nsubj(does-6, Peter-5)
advmod(does-6, too-8)
~~~

~~~ sdparse
Sue is hungry and Peter is , too .

nsubj(hungry-3, Sue-1)
cop(hungry-3, is-2)
conj(hungry-3, is-6)
nsubj(is-6, Peter-5)
advmod(is-6, too-8)
~~~

~~~ sdparse
They will do it if they want to .

nsubj(do-3, They-1)
aux(do-3, will-2)
obj(do-3, it-4)
advcl(do-3, want-7)
nsubj(want-7, they-6)
xcomp(want-7, to-8)
~~~

述語が省略されつつも`aux`か`cop`が生起しない，より複雑な場合では，単純な昇格 (`orphan` <!--without `orphan` deprels deprelsってなんだ？-->) は極めて不自然か混乱を招くような関係を形成することとなる．例えば，次の例で_you_が_coffee_の主語となるのは，2番目の節が省略された述語ではなくコピュラ構文 (copular construction) を含んでいることを示唆する.

<div class="conllu-parse" tabs="yes">
# visual-style 6 5 nsubj color:red
1 I      I      _ PRP _ 2 nsubj _ _
2 like   like   _ VBP _ 0 root  _ _
3 tea    tea    _ NN  _ 2 obj   _ _
4 and    and    _ CC  _ 6 cc    _ _
5 you    you    _ PRP _ 6 nsubj _ _
6 coffee coffee _ VBP _ 2 conj  _ SpaceAfter=No
7 .      .      _ .   _ 2 punct _ _
</div>

もちろん，_coffee_のかわりに_you_を昇格させても構わないが，_coffee_が_you_の直接目的語であることを示唆してしまうので，決して良いとはいえない:

<div class="conllu-parse" tabs="yes">
# visual-style 5 6 obj color:red
1 I      I      _ PRP _ 2 nsubj _ _
2 like   like   _ VBP _ 0 root  _ _
3 tea    tea    _ NN  _ 2 obj   _ _
4 and    and    _ CC  _ 5 cc    _ _
5 you    you    _ PRP _ 2 conj _ _
6 coffee coffee _ VBP _ 5 obj  _ SpaceAfter=No
7 .      .      _ .   _ 2 punct _ _
</div>

混乱を解消して依存構造が不完全であることを明示するには，`orphan`という特別な関係を用いて非昇格要素と昇格要素を結合させる．この関係で結ばれた依存部は次の順で昇格が行われると考えられる:
`nsubj` > `obj` > `iobj` > `obl` > `advmod` > `csubj` > `xcomp` > `ccomp` > `advcl` > `dislocated` > `vocative`.
同じタイプの複数の`orphan` (e.g., 2つが共に`advmod`)を選ぶ必要があるとき，先頭に生起するもの (文頭に近いもの) が昇格する．

~~~ sdparse
I like tea and you coffee .

nsubj(like-2, I-1)
obj(like-2, tea-3)
conj(like-2, you-5)
cc(you-5, and-4)
orphan(you-5, coffee-6)
~~~

~~~ sdparse
Mary wants to buy a book and Jenny a CD .

nsubj(wants-2, Mary-1)
xcomp(wants-2, buy-4)
obj(buy-4, book-6)
conj(wants-2, Jenny-8)
orphan(Jenny-8, CD-10)
~~~

~~~ sdparse
They had left the company , many for good .

nsubj(left, They)
obj(left, company)
conj(left, many)
orphan(many, good)
~~~

~~~ sdparse
Mary wants to buy a book . ROOT And Jenny a CD .

nsubj(wants-2, Mary-1)
xcomp(wants-2, buy-4)
obj(buy-4, book-6)
root(ROOT, Jenny)
orphan(Jenny, CD)
~~~

~~~ sdparse
She gave the dog a bone , and the man a flower .

nsubj(gave, She)
iobj(gave, dog)
det(dog, the-3)
obj(gave, bone)
det(bone, a-5)
conj(gave, flower)
punct(flower, ,)
cc(flower, and)
orphan(flower, man)
det(man, the-9)
det(flower, a-11)
punct(gave, .)
~~~

関係`orphan`は，通常の関係が誤解を招く場合 (例えば，主語へ目的語を付加してしまう) にのみ用いること．特に，関係`cc`は，`orphan`の依存部によって形成される擬似的な構成素 (pseudo-constituent) へ付加するような等位接続に限定して用いるべきである．

<!--ドイツ語では不定動詞が節の最後尾に生起することを要求し，定の助動詞とは異なることを
In German the grammar requires that non-finite verbs are at the end of the clause, which may mean that they are far away from
their finite auxiliary verbs, possibly with intervening conjuncts.--> 次の例では，_wurde geschieden_が一つの構成素内にあると考えない代わりに，助動詞の_wurde_が先頭の等位要素へと昇格し，かつ<!--content participle-->の_geschieden_が3番目の要素の主辞になると考える．2番目の要素には動詞が存在せず，その代わり関係`orphan`が用いられている．また，[issue 522](https://github.com/UniversalDependencies/docs/issues/522) も参照されたい．

~~~ sdparse
Der Genuß wurde von der Arbeit , das Mittel vom Zweck , die Anstrengung von der Belohnung geschieden . \n The pleasure was from the work , the means from-the goal , the effort from the reward distinguished .
nsubj:pass(wurde, Genuß)
obl(wurde, Arbeit)
conj(wurde, Mittel)
orphan(Mittel, Zweck)
punct(Mittel, ,-7)
conj(wurde, geschieden)
nsubj:pass(geschieden, Anstrengung)
obl(geschieden, Belohnung)
punct(geschieden, ,-12)
~~~

## Multiword Expressions

複合表現 (Multiword expressions; MWEs) は (程度差はあれど) 構成的な句よりも語彙単位として振る舞うような語の組み合わせである．UDの分類法はMWEsを分析するのに3つの特別な関係を備えている:

* [u-dep/fixed]() は_in spite of_のように固定の文法化したMWEsを分析するのに用いられる
* [u-dep/flat]() は_Barack Obama_のように，外心的 (exocentric) で固定されつつあるMWEsの分析に用いられる
* [u-dep/compound]() _noun phrase_のような内心的 (endocentric) な複合語 (compounds) を分析するのに用いられる

<!--[u-dep/fixed]() や [u-dep/flat]() で分析される構造は，定義的に主辞を欠き， 
Structures analyzed with [u-dep/fixed]() and [u-dep/flat]() are headless by definition and are consistently
annotated by attaching all non-first elements to the first and only allowing outgoing dependents from the first element.-->

<div id="s8a" class="sd-parse">
We had a nice time in spite of the rain .
case(rain,in)
fixed(in,spite)
fixed(in,of)
obl(had,rain)
</div>

<div id="s8b" class="sd-parse">
Martin Luther King had a dream .
nsubj(had,Martin)
flat(Martin,Luther)
flat(Martin,King)
</div>

対照的に，[compounds](複合語) は修飾構造を示すためのタグである，標準の主辞の概念を含む:

<div id="s9" class="sd-parse">
I bought a computer disk drive enclosure .
nsubj(bought, I)
det(enclosure, a)
compound(drive, computer)
compound(drive, disk)
compound(enclosure, drive)
obj(bought, enclosure)
</div>

## Comparatives

比較構文 (comparative construction) の統語論は言語理論に対して多くの困難を与える．英語では，これらの多くがBresnan (1973) や Huddleston and Pullum (2002, 13章) で議論されてきた．ここでは，<!--equality comparisons (_That car is as big as mine_) and inequality scalar comparisons (_Sue is taller than Jim_).について議論を行う．-->

_as X as Y_ もしくは _the same X as Y_ といった形式の構文では，XとYは様々な統語タイプをとり，以下のような表層形を生み出す:

* _Commitment is as important as a player’s talent._
* _Get the cash to him as soon as possible._
* _I put in as much flour as the recipe called for._

構文全体の主辞はXを含む句の主辞だと考えられるため，単に次のように言うこともできる:

*  _Commitment is important._
*  _Get the cash to him soon._
*  _I put in flour._

先頭の_as_はX句の要素を修飾するような独立の修飾語だと考えられる．以下の_as Y_は任意の要素となるからである:

* _Commitment is (just) as important._
* _?Get the cash to him (just) as soon._
* _I put in (just) as much flour._

しかし，先頭の_as_はXの主辞を修飾するのではなく，主辞の修飾要素を修飾している可能性がある．その役割は副詞的 ([u-dep/advmod]()) なもので，他の種類の程度修飾 (degree modification) とも整合する:

~~~ sdparse
Commitment is as important as a player ’s talent .
advmod(important, as-3)
~~~

~~~ sdparse
I put in as much flour as the recipe called for .
advmod(much, as-4)
amod(flour, much)
~~~

比較の補部は先頭部分の依存部であり，斜格を取るものと考える．補部の_as Y_が節になり得るのは明らかであり，上で示したように通常は任意の要素である．この理由から，補部を [u-dep/advcl]() として分析し，2番目の_as_は`mark`として分析される<!--he second _as_ analyzed as a markのmarkは`mark`のこと?-->:

~~~ sdparse
I do n't hear from my brother as often as I previously heard from him .
nsubj(hear, I-1)
aux(hear, do)
advmod(hear, n't)
case(brother, from-5)
det(brother, my)
obl(hear, brother)
advmod(often, as-8)
advmod(hear, often)
mark(heard, as-10)
nsubj(heard, I-11)
advmod(heard, previously)
advcl(often, heard)
case(him, from-14)
obl(heard, him)
punct(hear, .)
~~~

<!--We take the _as Y_ clause as a dependent of the content-word whose degree is being assessed (here _often_). We take its head to be the head of the clause, here _heard_.  An initially plausible alternative analysis would be to make the clausal dependent headed by _as_ a dependent of the comparative modifier _as_, _more_, or _less_, and indeed this is the analysis which Huddleston and Pullum (2002) argue for in English.
_as Y_節は，程度 (degree) が評価対象となる内容語 (ここでは_often_) の依存部として扱われ，上記の例では_heard_が_as Y_節の主辞として扱われる．他の妥当な分析としては，_as_を主辞とした節の依存部を_as_，_more_もしくは_less_といった比較の修飾語の依存部として扱うことであり，これはHuddleston and Pullum (2002) が英語において主張している分析である． しかし，いくつかの理由からこの分析は疑わしい． 一点目は，UDの基本原則として内容語を主辞として選好することに求められる．二点目は，通言語的な妥当性を満たす動機に基づいている: フィランド語や日本語といった言語では，このような機能語を持たない.-->

~~~ sdparse
“Y” より “X” が 面白い 。 \n Y than X NOM interesting .
nsubj(面白い, “X”)
case(“X”, が)
case(“Y”, より)
obl(面白い, “Y”)
punct(面白い, 。)
~~~
先頭の_as_は機能語であるため，依存部は_as often_の句全体を修飾するものとして理解され，句の主辞へ付加される．また，英語のいくつかの変種では比較語を伴わずに比較が可能であることに注意されたい．例えば，インド英語では_So don't worry if you think that you have a girl-friend, who is intelligent than you._といった用法が観察される．比較の形態論的な議論は以下で論じる．同様の分析は，_more_や_less_と比較形容詞および_than_を用いた，量に違いのある比較に対しても与えられる．この分析は上記の_as_の2つ用法と並行的であるが，_more_が名詞を直接修飾できたり，_more_が名詞と関係 [u-dep/amod]() を結ぶ点で相違点も存在する．この事例において，比較の補部は_more_への依存度が高く，おおよそ_more 数量 (numerous)_を省略したものとしてみなされる．一般的に，比較の補部は常に形容詞や副詞と依存し，[obl]() である場合を除き，通常は [advcl]() として扱われる (本セクションの最後でも議論する)．

~~~ sdparse
more problems than you thought of last week
amod(problems, more)
advcl(more, thought)
mark(thought, than)
~~~

~~~ sdparse
more important than you thought
advmod(important, more)
advcl(important, thought)
mark(thought, than)
~~~

~~~ sdparse
more rapidly than you thought
advmod(rapidly, more)
advcl(rapidly, thought)
~~~

~~~ sdparse
a more difficult problem than you thought
advmod(difficult, more)
amod(problem, difficult)
advcl(difficult, thought)
~~~

通言語的な妥当性に加えて，_more_を_than_節に付加させないことの利点はもう一つある: この分析をとることで，依存構造を_more intelligent_のような迂言的比較 (periphrastic comparative) や_taller_のような形態的比較 (拘束形態素であっても，_-er_は比較の主辞として主張が可能である) と並行的に扱うことができる．

~~~ sdparse
smarter than you thought
advcl(smarter, thought)
mark(thought, than)
~~~

~~~ sdparse
fiksumpi kuin luulit \n smarter than you_thought
advcl(fiksumpi, luulit)
mark(luulit, kuin)
~~~

~~~ sdparse
a smarter boy than you thought
amod(boy, smarter)
advcl(smarter, thought)
mark(thought, than)
~~~

主辞が省略される場合，機能語が昇格する．

~~~ sdparse
Wheat raises blood sugar even more than sugar does .
advcl(more, does)
~~~

比較の補部節は部分的な省略を受けることが一般的だが，極端な場合もある:

~~~ sdparse
I put in as much flour as the recipe called for .
nsubj(put, I)
compound(put, in)
advmod(much, as-4)
amod(flour, much)
obj(put, flour)
mark(called, as-7)
det(recipe, the)
nsubj(called, recipe)
advcl(much, called)
obl(called, for)
punct(put, .)
~~~

~~~ sdparse
He plays better drunk than sober
nsubj(plays, He)
advmod(plays, better)
acl(He, drunk)
mark(sober, than)
advcl(better, sober)
~~~

<!--一般的には[u-dep/advcl]() であり続けるremnantは何であれ，上記のように扱われる.
In general, we treat whatever remnant that remains as still an [u-dep/advcl](), as above.-->

しかし，限定的であるが，名詞句のみが生起する事例もある.

* _as important as a player 's talent_
* _more important than a player 's talent_

この例では分析が不明瞭である: 比較の補部は省略された節と分析するのか，単に名詞句の修飾句として分析するべきだろうか? 両者を支持する主張があり，英語においては Huddleston and Pullum (2002; 13章の2.2節) が大部にわたる議論を展開している．UDでは観察されない構造をなるべく仮定しない立場に立つため，これらの事例を単に斜格名詞句の補部として扱うことにする．

~~~ sdparse
as important as a player 's talent
advmod(important, as-1)
case(talent, as-3)
obl(important, talent)
~~~

~~~ sdparse
more important than a player 's talent
advmod(important, more)
case(talent, than)
obl(important, talent)
~~~

### _More than_ as a multi-word expression

特定のコンテクストにおいて，比較の補部では行為と形容詞を，その量と組み合わせる場合がある:

* _more than 90 percent (= over 90 percent)_
* _more than likely_
* _Home prices have more than doubled in the past decade._

これらの例では，_more than_ は分離不可能である (_*more percent than 90._) ため，固定のMWEとして扱われる．

~~~ sdparse
That is more than likely .
nsubj(likely, That)
cop(likely, is)
advmod(likely, more)
fixed(more, than)
punct(likely, .-6)
~~~

_more than_ が加算名詞句を修飾する場合，修飾される数へ直接付加する:

~~~ sdparse
more than two years ago
nummod(years, two)
fixed(more, than)
advmod(two, more)
~~~

数が存在しない場合 (不定冠詞が"1"として機能する)，主辞へ直接付加する:

~~~ sdparse
more than a year ago
det(year, a)
fixed(more, than)
advmod(year, more)
~~~

## Paratactic Constructions

関係 [parataxis]() は，節が標準の等位関係よりも緩い関係で結合されるような構文を分析するために用いられる．

### Side-by-side sentences ("run-on sentences")

関係 [parataxis]() は，複数の独立文であり得るが単一の文として扱われる文のペアに対して用いられる．この扱いは，文末のピリオドによって文の境界が決定されることに起因する (複数の節はコロンやカンマで区切られる場合もあれば，そうでない場合もある)．また，話し言葉コーパスでは，一般的に文とラベル付けされる要素は発話のターン (turn) であり，ツリーバンクで文を分離させたとしても，明らかに2つの節を結合させる談話関係が存在すると考えられるためである．2つより多くの文を結合する場合もあり，その場合は後続する文を先頭の文の依存部として扱う．この方法を採ることで，等位関係に用いられる分析との類似性を高めることが可能となる.

~~~ sdparse
Bearded dragons are sight hunters , they need to see the food to move .
parataxis(hunters, need)
~~~

この関係は文よりも小さいユニットでも発生し得る．

~~~ sdparse
Divided world the CIA
amod(world, Divided)
parataxis(world, CIA)
det(CIA, the)
~~~

### Reported Speech

間接話法の例:

~~~ sdparse
The guy , John said , left early in the morning
parataxis(left, said)
~~~

基本的に同じ意味を表すパラフレーズが存在するものの，その統語構造は異なる．間接話法が従属節に埋め込まれたとき (顕在的な補文マーカーのthatを伴う/伴わない場合のいずれでも)，従属節は発言動詞 (speech verb) の [ccomp]() となる．<!--間接話法が発言動詞に後続し，コロンで分離されたとき，When the
reported speech follows the speech verb and is separated by a colon, the reported speech forms a main clause
that attaches to the preceding main clause with a [parataxis]() relation, hence with the speech verb as its head.-->
しかし，発言動詞が中間部か最後部の挿入句として生起する場合はその関係が逆転し，発言動詞は間接話法の [parataxis]() として扱われる．
この分析は異論がないわけではないが，Huddleston and Pullum (2002), _The Cambridge Grammar of the English Language_ (see chapter 11, section 9) といった文献に裏付けられている．

~~~ sdparse
John said that the guy left early in the morning .
ccomp(said, left)
~~~

~~~ sdparse
John said the guy left early in the morning .
ccomp(said, left)
~~~

~~~ sdparse
John said : “ The guy left early in the morning . ”
parataxis(said, left)
~~~

~~~ sdparse
“ The guy left early in the morning ” , John said .
parataxis(left, said)
~~~

~~~ sdparse
The guy left early in the morning , John said .
parataxis(left, said)
~~~

~~~ sdparse
The guy , he said , left early in the morning .
parataxis(left, said)
~~~

この分析を支持する主張として，埋め込みとして分析される例において，節全体は埋め込みがさらに可能である (_I was taken aback when John said the guy left early in the morning._) 一方で，発言動詞が中間か最後部に置かれた場合は埋め込みが不可能である (_*I was taken aback when the guy left early this morning, John said._ )，というものがある．

### News Article Bylines

新聞記事の署名部分を結合するためにも並立関係が用いられる．これは，他によい選択肢が存在しないからである．

~~~ sdparse
Washington ( CNN ) :
parataxis(Washington, CNN)
~~~

### Interjected Clauses

単一の間投詞 (interjection) や間投詞句は [discourse]() として分析されるが，節全体が挿入される場合には，並立関係を持ちいる．

~~~ sdparse
Calafia has great fries ( they are to die for ! )
parataxis(has, are)
~~~

~~~ sdparse
Just to let you all know Matt has confirmed the booking for 3rd Dec is OK .
parataxis(confirmed, let)
~~~

2つ目の例では，2番目の部分を依存関係の主辞として扱う．1番目の部分は節全体からなる間投詞だと感じられ，発話の主節ではないように思われるからである．

### Tag Questions

並立関係 (parataxis relation) は_isn't it?_ もしくは _haven't you?_といった付加疑問文にも用いられる．

~~~ sdparse
It 's not me , is it ?
parataxis(me, is)
~~~
* 直接話法および間接話法: 現行では関係 [u-dep/parataxis]() として記述される.

### Feedback words

_yes_や_no_といった返答語 (feedback word) から始まり，主節へ続くような文では主節の述語を文の根 (root) として扱い，返答語は関係 [discourse]() を伴って述語へ付加される:

~~~ sdparse
yes , we should apply for membership .
discourse(apply, yes)
~~~

しかし，応答が応答語ではなく完全な節で表現された場合は，この節の述語を根として扱い，後続する節の述語は関係 [parataxis]() を伴って根へ付加される:

~~~ sdparse
I agree , we should apply for membership .
parataxis(agree, apply)
~~~

## Punctuation

関係 [u-dep/punct]() を伴うトークンは常に内容語へ付加され (省略 (ellipisis) は例外)，依存部を持つことがない．`punct` が標準的な依存関係でないことから，主辞を決定する通常の基準は適用できない．その代わり，以下の原則に従う:

1. 等位要素を分離するカンマは後続要素へ付加する．
2. 先行/後続の依存部ユニットを標示するカンマは，その要素へ付加する．
3. 関連するユニット内では，投射可能性 (projectivity) を保持するような最高位の節点に付加される.
4. 一組で使われる符号 (引用符や括弧) は投射可能性が失わなれない限り同一の語に付加される．この語は通常，句の主辞である．

<div id="punct1" class="sd-parse">
We have apples , pears , oranges , and bananas .
obj(have, apples)
conj(apples, pears)
conj(apples, oranges)
conj(apples, bananas)
cc(bananas, and)
punct(pears, ,-4)
punct(oranges, ,-6)
punct(bananas, ,-8)
</div>

<div id="punct2" class="sd-parse">
Der Mann , den Sie gestern kennengelernt haben , kam wieder .
punct(kennengelernt, ,-3)
punct(kennengelernt, ,-9)
punct(kam, .)
</div>

<div id="punct3" class="sd-parse">
A.K.A., AKA, または a\/k\/a: 匿名 (pseudonyms) や変名 (aliases) などを表す “ Also known as ” を指す ( “ formerly known as ” を表すf.k.a. と比較せよ. )
punct(AKA, ,-2)
punct(a/k/a, ,-4)
punct(refer, :)
punct(known-13, “-11)
punct(known-13, ”-15)
punct(used, ,-16)
punct(aliases, ,-21)
punct(etc., ,-23)
punct(Compare, (-25)
punct(Compare, )-35)
punct(known-31, “-29)
punct(known-31, ”-33)
punct(Compare, .-34)
</div>

例は [parataxis]() も参照のこと.
