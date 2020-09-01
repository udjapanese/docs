---
layout: base
title:  'Simple Clauses'
permalink: u/overview/simple-syntax.html
udver: '2'
---

# Simple Clauses

UDのタグ付けでは，節 (clause) をあらゆる言語にみられる基本的な構造だと仮定している．単純な節 (simple clause) は少なくとも述語 (predicate) および依存部 (dependents) である必須項 (core argument) から構成されるが，斜格の修飾部 (oblique modifier) が伴う場合もある．必須項は典型的には名詞句 (nominals) であるが，斜格の修飾部は (斜格の) 名詞句もしくは副詞的な修飾部である．( [complex clauses](complex-syntax.html) では，必須項と斜格の修飾部は従属節 (subordinate clauses) として実現することもある.) そして，述語は時制 (tense)，ムード (mood)，アスペクト (aspect)，ヴォイス (voice)，エビデンシャリティー (evidentiality) もしくは従位接続 (subordination) といった，様々な機能語 (function words) と結びつくことがある．

* [Intransitive and transitive clauses](#intransitive-and-transitive-clauses)
* [Nonverbal clauses](#nonverbal-clauses)
* [Non-core dependents](#non-core-dependents)
* [Function word dependents](#function-word-dependents)


## Intransitive and Transitive Clauses

ほとんどの節では，述語は動詞の形式をとり，それは自動詞か他動詞である．

~~~ sdparse
she left
nsubj(left, she)
~~~
~~~ sdparse
she left a note
nsubj(left, she)
obj(left, note)
~~~

自動詞は関係 [u-dep/nsubj]() を伴う単一の項 (言語類型論の文献では，通常Sと呼ばれる) をとる．他動詞は，それに加えて関係 [u-dep/obj]() を伴う項をとる．どちらの関係を他動詞節で用いるかを決定する際， 動作主 (proto agent) (言語類型論ではAと呼ばれる) と類似し，当該言語での主語性 (subjecthood) を満たすような項には関係 [u-dep/nsubj]() が用いられる (主語性は格標示 (case-marking)，一致 (agreement)，または述語と比較した線形順序の位置 (linear position) を基に判断される)．一方，関係 [u-dep/obj]() は，被動作主 (proto-patient) (言語類型論ではOかPと呼ばれる) に類似し，当該言語内の基準を満たすような項に用いられる．ただし，格標示 (形態的 (morphological)か分析的 (analytic) のどちらか) が特定の言語で重要な証拠を提供するものの，必須項の意味役割 (roles) を決定するために格のアライメント (case alignment) を用いるべきではないことに注意されたい．つまり，能格言語 (ergative language) においては，他動詞における被動作主 (patient; O/P) は，自動詞の[u-dep/nsubj]() が用いられる項と同じ格標示 (S) を受けるにもかかわらず，関係  [u-dep/obj]() をとるのである．
 

いくつかの言語では，2つ以上の依存部が必須項として実現することで他動詞節の拡張を許す．加わった必須項が (間接目的語) として関係 [u-dep/iobj]() をとる一方で，被動作主に類似し，かつ主語でない項に対しては関係 [u-dep/obj]() が保持される.  追加の依存部が必須項がどうかを判断する基準とは，格標示，一致や語順に照らしたとき典型的なエンコーディングが為されるかどうかである．例えば英語の二重目的語構文 (double object  construction) は，３つ全ての名詞句が前置詞を伴わずに生起するため，拡張した他動詞節として認定される．


~~~ sdparse
she left him a note
nsubj(left, she)
obj(left, note)
iobj(left, him)
~~~

対照的に，受益者 (recipitent) の意味役割が前置詞句によって実現するような斜格構文 (交替構文 (alternative construction) ) は，我々の基準からすると拡張した他動詞節ではないため，3番目の参与者は斜格としてタグ付けされる．

~~~ sdparse
she left a note to him
nsubj(left, she)
obj(left, note)
obl(left, him)
~~~

意味役割 (それ自体) は依存部が必須項であるかを決定づけない．UDは (必須の) 項と (任意) の付加詞を区別しないため，斜格の依存部は項でも付加詞でもありうる.

最後に，あらゆる言語が拡張された他動詞節を許すわけではない (また，いくつかの言語では適用形 (applicative) の形成といった，原子価 (valency) を変える操作でのみ行われる) ことに注意されたい．よって，関係  [u-dep/iobj]() は全ての言語で用いられるわけではない．

### Valency-Changing Operations

受動化 (passivization) が項の主語位置への昇格 (promotion) に関わるとき，昇格したことを示すため，この項には主語のサブタイプである `nsubj:pass` のタグが付与される．斜格のサブタイプの `obl:agent`  は，(文中に生起する場合は) 降格した (demoted) 主語に付与される．


~~~ sdparse
she left a note on the table
nsubj(left, she)
obj(left, note)
obl(left, table)
~~~
~~~ sdparse
a note was left on the table
nsubj:pass(left, note)
obl(left, table)
~~~
~~~ sdparse
a note was left by her on the table
nsubj:pass(left, note)
obl:agent(left, her)
obl(left, table)
~~~

同様の下位タイプは原子価 (valency) を変える操作でも用いられる場合がある．動詞の使役形 (causatives) では，目的語が降格した主語であることを示すのに `obj:caus` や `iobj:caus` といったサブタイプが用いられる．

~~~ sdparse
Hasan koştu \n Hasan ran
nsubj(koştu, Hasan)
~~~
~~~ sdparse
(ben) Hasanı koşturdum \n I Hasan made-run
obj:caus(koşturdum, Hasanı)
~~~
~~~ sdparse
Hasan kitabı okudu \n Hasan book read
obj(okudu, kitabı)
~~~
~~~ sdparse
(ben) Hasana kitabı okuttum \n I I Hasan book made-read
obj(okuttum, kitabı)
iobj:caus(okuttum, Hasana)
~~~


## Nonverbal Clauses

動詞でない述語 (名詞句もしくは形容詞) は関係 [u-dep/nsubj]() をもつ単一の項をとる．必須項の関係は，述語と主語を結合する連結動詞が生起するか否かに関わらず同じである．

~~~ sdparse
she is my mother
nsubj(mother, she)
~~~
~~~ sdparse
она моя мать \n she my mother
nsubj(мать, она)
nsubj(mother, she)
~~~
~~~ sdparse
she is nice
nsubj(nice, she)
~~~
~~~ sdparse
она милая \n she nice
nsubj(милая, она)
nsubj(nice, she)
~~~

UDのv2において動詞でない述語を一貫して取り扱うため，まず，通言語的に観察される，非動詞述語の6つのカテゴリを定義する (連結動詞 (連結動詞) がある場合/ない場合がある):

1. 等価 (Equation; もしくは同定 (identification) ): “she is my mother”
2. 属性 (Attribution): “she is nice”
   2.1. 量化 (Quantification): “they are two”
3. 場所 (Location): “she is in the bathroom”
4. 所有 (Possession): “the book is hers”
5. 受益 (Benefaction): “the book is for her”
6. 存在 (Existence): “there is food (in the kitchen)”

これらの構文の分析にあたっては，以下のガイドラインを設ける:

* 連結動詞が生起しない場合 (もしくは，当該の語の人称 (person) や時制 (tense) が省略された場合)，叙述名詞 (predicative nominal) は上記の6カテゴリのいずれに該当しようとも節の主語として扱われる．(英語のような) 固定されたSVO語順をとる言語では，最後の名詞句が述語であり，最初の名詞句が主語である．語順が自由な言語においては，最初の名詞句が述語となるのも可能であり，述語と主語の区別は言語特有の基準に基づく．
* 等価構文 (カテゴリ1) で用いられる連結動詞が生起している場合，その語はコピュラとみなされ，依存部 [u-dep/cop]() として標示されるため，節の主辞 (head) にはならない．**例外:** 等価構文における述語の要素が節である場合，連結動詞は節の主辞として扱われ，後続の節は (小さい方の節が2つの主語を持たないように)  [u-dep/ccomp]() として表される．いくつかの言語では，その節を，連結動詞を関係 [u-dep/cop]() として保持しつつ，主語 ([u-dep/csubj]()) として分析することが可能であるかもしれない．
* 存在構文 (カテゴリー6) に用いられる，等価構文におけるコピュラとは異なる語が生起する場合，連結動詞は主語 (場所格 [u-dep/obl]() も頻繁に) をとる存在文節の主辞としてみなされる．
* コピュラ構文と目される他の事例 (カテゴリ2-5) は，当該言語に固有の考え方に則して，等価構文や存在構文に吸収されると考えるのが最も合理的である.
* どの言語も高々1つのコピュラを持つのが通常であるが，例外もある．それは，屈折のパラダイムが欠けていたり，1から5のカテゴリで動詞が交替したり (6にはない)，同じカテゴリであっても意味の違いを区別するような場合においてである<!--TAME categories?→SAME categories?-->．

これらのガイドラインが様々な言語に適用されることを例証するため，英語，アイルランド語，スウェーデン語，チェコ語，ロシア語およびトルコ語から類例を示す．

### English

英語では，(1b) の等価構文節や，連結動詞が節の主辞として扱われる (6) の存在構文節を除いて，"to be" が (1-6) の全てで用いられるため，一貫したコピュラの分析が与えられる．

(1a)

~~~ sdparse
she is my mother
nsubj(mother, she)
cop(mother, is)
~~~

(1b)

~~~ sdparse
the fact is that she is my mother
nsubj(is-3, fact)
ccomp(is-3, mother)
nsubj(mother, she)
cop(mother, is-6)
~~~

(2)

~~~ sdparse
she is nice
nsubj(nice, she)
cop(nice, is)
~~~

(3)

~~~ sdparse
she is in the kitchen
nsubj(kitchen, she)
cop(kitchen, is)
case(kitchen, in)
~~~

(4)

~~~ sdparse
it is hers
nsubj(hers, it)
cop(hers, is)
~~~

(5)

~~~ sdparse
it is for her
nsubj(her, it)
cop(her, is)
case(her, for)
~~~

(6a) 

~~~ sdparse
there is food
expl(is, there)
nsubj(is, food)
~~~

(6b) 

~~~ sdparse
there is food in the kitchen
expl(is, there)
nsubj(is, food)
obl(is, kitchen)
case(kitchen, in)
~~~

### Irish

アイルランド語は，連結動詞はカテゴリ1，4と5で用いられ，別の動詞が2，3と6で用いられる．このとき，動詞だけではなく語順も異なる．

(1) 

~~~sdparse
is ise mo mháthair \n COP her my mother
nsubj(mháthair, ise)
cop(mháthair, is)
~~~

(2) 

~~~sdparse
tá sí deas \n is she nice
nsubj(tá, sí)
xcomp(tá, deas)
~~~

(3)

~~~sdparse
tá sí sa seomra folctha \n is she in room bath
nsubj(tá, sí)
xcomp(tá, seomra)
~~~

(4)

~~~sdparse
is lei an leabhar \n COP with her the book
nsubj(leabhar, lei)
cop(leabhar, is)
~~~ 

(5)

~~~sdparse
is di an leabhar \n COP with her the book
nsubj(leabhar, di)
cop(leabhar, is)
~~~ 

(6)

~~~sdparse
tá bia ann
nsubj(tá, bia)
~~~~


### Czech

チェコ語の動詞_být_は (1-6) の全てのカテゴリで用いられ，_být_以外の述語が使用できない，純粋な存在を表す場合 (場所が示されない) を除き，あらゆる場合において連結動詞として分析される．チェコ語の語順は自由であるため，あらゆる構文が主語-連結動詞-述語の順で現れる保証はない．逆の語順 (述語-連結動詞-主語) は一般的ではないが，「等価」のカテゴリ1であっても可能である．また，チェコ語はpro-drop言語であるため，代名詞の主語は任意である．

(1a)

~~~ sdparse
(ona) je moje matka \n she is my mother
nsubj(matka, (ona))
nsubj(mother, she)
cop(matka, je)
cop(mother, is)
~~~

(1b)

~~~ sdparse
faktem je , že ona je moje matka \n fact is , that she is my mother
cop(faktem, je-2)
cop(fact, is-11)
csubj(faktem, matka)
csubj(fact, mother)
nsubj(matka, ona)
nsubj(mother, she)
cop(matka, je-6)
cop(mother, is-15)
~~~

(2)

~~~ sdparse
(ona) je milá \n she is nice
nsubj(milá, (ona))
nsubj(nice, she)
cop(milá, je)
cop(nice, is)
~~~

(3)

~~~ sdparse
(ona) je v kuchyni \n she is in kitchen
nsubj(kuchyni, (ona))
nsubj(kitchen, she)
cop(kuchyni, je)
cop(kitchen, is)
case(kuchyni, v)
case(kitchen, in)
~~~

(4)

~~~ sdparse
to je její \n it is hers
nsubj(její, to)
nsubj(hers, it)
cop(její, je)
cop(hers, is)
~~~

(5)

~~~ sdparse
to je pro ni \n it is for her
nsubj(ni, to)
nsubj(her, it)
cop(ni, je)
cop(her, is)
case(ni, pro)
case(her, for)
~~~

(6a) 

~~~ sdparse
jídlo je \n food is
nsubj(je, jídlo)
nsubj(is, food)
~~~

(6b) 

~~~ sdparse
v kuchyni je jídlo \n in kitchen is food
nsubj(kuchyni, jídlo)
nsubj(kitchen, food)
cop(kuchyni, je)
cop(kitchen, is)
case(kuchyni, v)
case(kitchen, in)
~~~


### Russian

ロシア語では，連結動詞の現在形が存在しない．未来時制と過去時制では動詞_быть_ "be"が用いられる．
同様の分析はカテゴリ (1-5) にも適用される．

(1a)

~~~ sdparse
она моя мать \n she my mother
nsubj(мать, она)
nsubj(mother, she)
~~~

(1b)

カンマに後続する部分が節であるとき，指示代名詞の_то_が挿入されなければならない．結果として，その統語構造には異なった分析が与えられる:
形式的に，節は指示詞によって表される名詞句を修飾する．

~~~ sdparse
дело в том , что она моя мать \n fact in that , that she my mother
nsubj(том, дело)
nsubj(that-12, fact)
acl(том, мать)
acl(that-12, mother)
nsubj(мать, она)
nsubj(mother, she)
~~~

(2)

~~~ sdparse
она милая \n she nice
nsubj(милая, она)
nsubj(nice, she)
~~~

(3)

~~~ sdparse
она на кухне \n she in kitchen
nsubj(кухне, она)
nsubj(kitchen, she)
case(кухне, на)
case(kitchen, in)
~~~

(4)

~~~ sdparse
это ее \n it hers
nsubj(ее, это)
nsubj(hers, it)
~~~

(5)

~~~ sdparse
это для нее \n it for her
nsubj(нее, это)
nsubj(her, it)
case(нее, для)
case(her, for)
~~~

(6a) 

 _есть_の形式は，もとは動詞_быть_ (連結動詞としても機能する) の3人称単数の直接法 (indicative) である．しかし現代ロシア語においては，この形式は，どの数や人称であっても，存在を言明する場合のみに用いられる．ただし，過去や未来での存在の言明は_быть_の通常の形式を用いる．

~~~ sdparse
есть еда \n is food
nsubj(есть, еда)
nsubj(is, food)
~~~

(6b) 

~~~ sdparse
есть еда на кухне \n is food in kitchen
nsubj(есть, еда)
nsubj(is, food)
obl(есть, кухне)
obl(is, kitchen)
case(кухне, на)
case(kitchen, in)
~~~


### Turkish

トルコ語では，_i-_ と _ol-_ の2つの連結動詞がある．"真正の" のコピュラはパラダイム上に存在しない (defective) _i-_であり，特定の時制形式 (アオリスト，過去) と接語しかもたない．コピュラで他の時制を表す場合，_ol-_ が用いられる．ただし，_i-_ という形式が生起する場合，それに対応する_ol-_という形式は「~になる」(become) を意味する．

現在時制において，3人称単数のアオリストがnon-formalであるとき，3人称単数の接尾辞が現れない．ロシア語と異なり，コピュラ動詞がパラダイムにおける現在時制の位置に存在ようなトルコ語では，3人称を除き全ての人称で現れる (1aと1bを比較せよ)．これは，パラダイム上の主格部分に類似している (ゼロ接尾辞 (-Ø suffix) も存在し，ロシア語のコピュラよりも類似する)．

トルコ語 (および，ほとんどのテュルク諸語で) では存在構文は統語的に異なり， 形容詞 _var_ "existent" を用いる (6aと6bを見よ)．


(1a)

~~~ sdparse
O benim annem . \n she my mother
nsubj(annem, O)
nsubj(mother, she)
~~~

(1a)

~~~ sdparse
Ben senin baban -ım . \n I your father am
nsubj(baban, Ben)
cop(baban, -ım)
nsubj(father, I)
~~~

(1c)

~~~ sdparse
O benim annem -di . \n she my mother was
nsubj(annem, O)
cop(annem, -di)
nsubj(mother, she)
~~~


(2)

~~~ sdparse
O hoş . \n She nice
nsubj(hoş, O)
nsubj(nice, She)
~~~

(3)

~~~ sdparse
O mutfakta . \n She kitchen-in .
nsubj(mutfakta, O)
nsubj(kitchen-in, She)
~~~

(4)

~~~ sdparse
Bu onun . \n It hers .
nsubj(onun, Bu)
nsubj(hers, It)
~~~

(5)

~~~ sdparse
Bu onun için . \n It hers for .
nsubj(onun, Bu)
case(onun, için)
nsubj(hers, It)
case(hers, for)
~~~

(6a

~~~ sdparse
Yemek var . \n Food existing .
nsubj(var, Yemek)
nsubj(existing, Food)
~~~

(6b)

~~~ sdparse
Mutfakta yemek var . \n Kitchen-in food existing .
nsubj(var, yemek)
obl(var, Mutfakta)
nsubj(existing, food)
obl(existing, Kitchen-in)
~~~

## Non-Core Dependents

必須項に加えて，述語も追加の依存部を持つことがある．その文法的な形式は，格標示，一致および節の線形位置に関して必須項と異なる．そのような依存部は，意味的に項とみなせるか否かに関係なく，全て斜格である．関係 [obl]() が斜格名詞句に用いられ，関係 [advmod]() は副詞の修飾句に用いられる．


~~~ sdparse
she left a note on the table
nsubj(left, she)
obj(left, note)
obl(left, table)
~~~
~~~ sdparse
she left a note in the morning
nsubj(left, she)
obj(left, note)
obl(left, morning)
~~~
~~~ sdparse
she left from home
nsubj(left, she)
obl(left, home)
~~~
~~~ sdparse
she left suddenly
nsubj(left, she)
advmod(left, suddenly)
~~~

一般的な関係 [u-dep/obl]() に加えて，述語の必須項ではない依存部のために用いられる3つ関係がある: [u-dep/expl](), [u-dep/dislocated](), および [u-dep/vocative]().

### Expletives

関係 [u-dep/expl]() は虚辞 (expletive) もしくは冗長表現となる名詞句を表す．これらは述語の項の位置に現れる名詞句であるが，述語のいずれの意味役割を満たさない．節の主述語 (main predicate; 動詞，形容詞の叙述用法，叙述名詞) は支配項 (governor) である．英語の虚辞としては，*it*や*there*のいくつかの用法が該当する: 存在の*there* および，倒置構文 (extraposition construction) の*it* (*it*と*there*には虚辞ではない用法があることに注意)．

~~~ sdparse
There is a ghost in the room
expl(is, There)
~~~

~~~ sdparse
It is clear that we should decline .
expl(clear, It)
~~~

pro-dropが自由に行われる (代名詞の代わりにゼロ照応を用いる) 言語を含め，いくつかの言語では英語にみられるような虚辞を持たない．虚辞を持つ英語のような言語では，通常必須項が現れる位置に虚時が生起する: 主語の位置および直接目的語 (もしくは間接目的語) の位置．以下の分析では，後置した主語や節の項を必須項として扱い，虚辞に [u-dep/expl]() を付与していることに注意されたい．

~~~ sdparse
There is a ghost in the room
expl(is, There)
nsubj(is, ghost)
obl(is, room)
~~~

~~~ sdparse
I believe there to be a ghost in the room
nsubj(believe, I)
expl(believe, there)
xcomp(believe, be)
nsubj(be, ghost)
obl(be, room)
~~~

~~~ sdparse
It is clear that we should decline .
expl(clear, It)
csubj(clear, decline)
~~~

~~~ sdparse
That we should decline is clear .
csubj(clear, decline)
~~~

~~~ sdparse
I mentioned it to Mary that Sue is leaving
nsubj(mentioned, I)
expl(mentioned, it)
obl(mentioned, Mary)
ccomp(mentioned, leaving)
~~~

関係 [u-dep/expl]() の2番目の用法は，真正の二重の接語付加 (clitic doubling) である．接語と語彙的な名詞句が相補分布を示す言語 –"Kayneの一般化"に従うような，フランスといった言語– では，接語と名詞句のどちらが生起しても，[u-dep/obj]() もしくは [u-dep/iobj]() といった適切な役割を得る．そのような言語において，口語フランス語にように二重の接語付加が起きる場合，語彙的な名詞句を [dislocated]() としてみなすのが正しい分析である (例を参照せよ)．その分析では，名詞句が他の名詞句や規則的な代名詞を二重にした場合と同様である．名詞句の項の位置を埋める
As such, the analysis will be the same as when a noun phrase doubles another noun phrase or a regular pronoun that fills a nominal argument position. 
しかし，ギリシャ語やブルガリア語といった他の言語では，語彙的な名詞句と代名詞的接語の二重を標準的に許すが，前者では述語の項として通常の役割の位置に現れる．このような例において，語彙的名詞句と接語が一つの節に一つしか現れない場合に限り，両者は [u-dep/obj]() や [u-dep/iobj]() 等の文法役割が与えられる – 他の言語における語彙的名詞句と代名詞の扱いと並行的であり，接語である代名詞は文の異なる位置に生起する．しかし，両者がともに生起する場合，語彙的名詞句は [u-dep/obj]() や [u-dep/iobj]() 等の文法役割が与えられ，接語は代名詞のコピーとして扱われる．一方で後者はそれ自身が意味役割を受けるわけではないため，[u-dep/expl]() が与えられる．語順が異なるものの，これは上述した英語における_it_と_there_の扱いと並行的であり，別の句が述語の意味役割を満たす．ギリシャ語とブルガリア語の例は以下の通り:

~~~ sdparse
Της τον έδωσε της Καίτης τον αναπτήρα \n PRON.Fem.Gen PRON.Masc.Acc gave ART.Fem.Gen Keti.Gen ART.Masc.Acc lighter.Acc
expl(έδωσε, Της-1)
iobj(έδωσε, Καίτης)
det(Καίτης, της-4)
expl(έδωσε, τον-2)
obj(έδωσε, αναπτήρα)
det(αναπτήρα, τον-6)
~~~

~~~ sdparse
Marija mu izprati pismo na rabotnika \n Maria 3.S.M.IO sent letter to the.worker
expl(izprati, mu)
obj(izprati, pismo)
iobj(izprati, rabotnika)
case(rabotnika, na)
~~~

虚辞の関係 (expletive relation) は再帰代名詞にも用いられ (素性
 [u-feat/Reflex]() を参照)，再帰動詞 (reflexive verbs) に付加される．再動詞は再帰代名詞なしには現れず，その代名詞は通常の目的語としての役割を果たさない (さもなければ，非再帰代名詞 (irreflexive) や他の名詞句と置換が可能となる)．
チェコ語の例:

~~~ sdparse
Martin se bojí zvířat . \n Martin REFLEX fears animals .
expl(bojí, se)
expl(fears, REFLEX)
~~~

虚辞の一般的な議論については，Postal, P. M., and G. K. Pullum (1988) “Expletive Noun Phrases in Subcategorized Positions,” _Linguistic Inquiry_ 19(4): 635–670 にもある. 二重接語の付加 (clitic doubling) の地位と，代名詞のコピーの一種である接語に対する項となるような語彙的名詞句についての議論は，特にBoris Harizanov (2014) [Clitic doubling at the syntax-morphology interface: A-movement and morphological merger in Bulgarian](http://stanford.edu/~bharizan/pdfs/Harizanov_2014_NLLT.pdf). _Natural Language and Linguistic Theory_ に見られる．

### Dislocated

関係 [u-dep/dislocated]() は前置もしくは後置した，文の通常の文法関係を満たさないような要素に用いられる．これらの要素は文の周辺部 (periphery) にしばしば現れ，カンマのイントネーション (comma intonation) によって分離する.

以下の日本語やギリシャ語の例が示すように，文のトピックを導入するために前置要素が用いられる．転移要素 (dislocated element) は節の主辞に付加される:

~~~ sdparse
象 は 鼻 が 長い \n zoo wa hana ga naga-i \n elephant TOPIC nose SUBJ long-PRES
dislocated(長い-5, 象-1)
~~~

~~~ sdparse
to jani ton kserume poli kala \n the John-Acc him know-1pl very well 
dislocated(kserume, jani)
~~~

しかし，文主語でもある，トピックが付与された名詞には用いられない; この場合，[nsubj]() となる．

転移要素は後置要素にも用いられ，二重に現れる依存部と同一の支配項 (governor) に付加される．右側に転移した要素は話し言葉に現れることが多く，それはフランス語とギリシャ語の以下の例から示される．

~~~ sdparse
Il faut pas la manger , la plasticine \n It must not it eat , the playdough
obj(manger, la-4)
dislocated(manger, plasticine)
obj(eat, it-13)
dislocated(eat, playdough)
~~~

~~~ sdparse
ton kserume oli mas edho poli kala, to jani 
dislocated(kserume, jani)
~~~

### Vocatives

関係 [u-dep/vocative]() は，テキスト (会話，対話，電子メール，ニュースグループの投稿など) で言及される対話の参加者を表示するのに用いられる．この関係は聞き手の名前とホストの文を結合する．一つ目の例が示すとおり，呼格 (vocative) は空主語 (null subject) と共起することが一般である．名詞句が呼格であることが意図的である場合，関係 [u-dep/vocative]() が優先的に用いられる．

~~~ sdparse
Guys , take it easy!
vocative(take, Guys)
~~~

~~~ sdparse
Marie , comment vas - tu ?
vocative(vas, Marie)
~~~


## Function Word Dependents

必須項と必須でない項に加え，節の述語も機能語 (function words) によって修飾される場合がある:

1. `aux` は時制，アスペクト，ムード，ヴォイス，もしくはエビデンシャリティーに関する情報を付け加えることで動詞を修飾する．
2. `cop` は動詞でない述語を主語と結合させ，また，時制，アスペクト，ムード，ヴォイス，もしくはエビデンシャリティーに関する情報を付け加えることがある．
3. `mark` は，述語が (特定のタイプの) 従属節における主辞であることを示す．

~~~ sdparse
she has left
nsubj(left, she)
aux(left, has)
~~~
~~~ sdparse
she is happy
nsubj(happy, she)
cop(happy, is)
~~~
~~~ sdparse
she has been happy
nsubj(happy, she)
cop(happy, been)
aux(happy, has)
~~~
~~~ sdparse
( she knows ) that it is raining
ccomp(knows, raining)
mark(raining, that)
~~~
~~~ sdparse
( she left ) because it was raining
advcl(left, raining)
mark(raining, because)
~~~

