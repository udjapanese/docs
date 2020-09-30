---
layout: base
title:  'Syntax'
permalink: u/overview/syntax.html
udver: '2'
---

# Syntax: General Principles

UDスキームにおいて統語タグは，語間のタイプ付けされた依存関係 (dependency relations) から構成される．_通常_ の依存関係の表示は木 (tree) を形成する．1つの語が文の主辞 (head) となり，これは概念的な根 (ROOT) に依存する．そして，他の全ての語は文中の語に依存する．例は以下の通りである (ここでは根 (root) の依存関係を明示してあるが，省略されることもある．)．


~~~ sdparse
ROOT she wanted to buy and eat an apple
nsubj(wanted, she)
root(ROOT, wanted)
mark(buy, to)
xcomp(wanted, buy)
cc(eat, and)
conj(buy, eat)
det(apple, an)
obj(buy, apple)
~~~

全てのUDツリーバンクにおいて義務的である基本の依存関係の表示に加えて，_拡張版 (enhanced)_ の依存関係の表示を与えることができる．これは意味解釈に対して，より完全な規則を与えるために関係を加えよう (いくつかの関係は改変される) というものである．拡張版の表示は一般的に樹構造ではなくグラフ構造から成り，以下に示される (拡張版の依存関係は青で示される).

~~~ conllu
# visual-style 5 2 nsubj color:blue
# visual-style 7 2 nsubj color:blue
# visual-style 3 7 xcomp color:blue
# visual-style 7 4 mark color:blue
# visual-style 7 9 obj color:blue
1	ROOT	_	_	_	_	0	root	_	_
2	she	_	_	_	_	3	nsubj	5:nsubj|7:nsubj	_
3	wanted	_	_	_	_	1	root	_	_
4	to	_	_	_	_	5	mark	7:mark	_
5	buy	_	_	_	_	3	xcomp	_	_
6	and	_	_	_	_	7	cc	_	_
7	eat	_	_	_	_	5	conj	3:xcomp	_
8	an	_	_	_	_	9	det	_	_
9	apple	_	_	_	_	5	obj	7:obj	_

~~~

本ドキュメントの残りでは，基本的な表示と詳密な表示の両方に共通する側面に着目し，依存関係のタグ付けに係る基本原則を議論する．依存関係の表示の詳しい情報については，タグ付けの以下のガイドラインを参照している:

* Basic dependencies
    * [Simple clauses](simple-syntax.html)
    * [Complex clauses](complex-syntax.html)
    * [Nominal phrases](nominal-syntax.html)
    * [Other constructions](specific-syntax.html)
* [Enhanced dependencies](enhanced-syntax.html)

タイプ化した依存関係の目標は通言語的に適用可能な "普遍的な依存関係" を設定することにある．そのような依存関係では，重要な区別は設定しつつも，通言語的に同じ方法で同一の文法関係をタグ付けすることによって並行性を最大限に高めようとする．初めに，以下の2点に注意されたい:

* 並行性の目標には限界がある: UDでは複数の言語で生起しない "空" の要素を仮定せず，またタグ付けを行わない．また，当該言語に特有な関係を表示するため，普遍的な依存関係の改変を許す.
* 依存関係の概念には限界がある: 全ての文法関係が統語的な主辞と従属要素の間にある非対称的な関係に還元されるわけではない．よって，"依存" 関係のいくつかは単に他の関係のエンコードに便利なものとして理解する必要があり，それらは統語的な主辞とは無関係である．これは特に，複合表現 (multiword expressions)，等位関係 (coordination) や機能語 (function words) で関係する．

以降では，普遍的な依存関係が可能な限り通言的な並行性を満たすような一般原則について述べる．

## The Primacy of Content Words

依存関係は機能語によって導かれる間接的な関係ではなく，内容語の間にあることが主である．

<div id="s1a" class="sd-parse">
The cat could have chased all the dogs down the street .
nsubj(chased, cat)
obj(chased, dogs)
obl(chased, street)
</div>

機能語は最も密接に関係する内容語の直接的な依存部として付加する

<div id="s1b" class="sd-parse">
The cat could have chased all the dogs down the street .
det(cat, The)
aux(chased, could)
aux(chased, have)
det(dogs, all)
det(dogs, the-7)
case(street, down)
det(street, the-10)
</div>

カンマは節や句の主辞に付加される．


<div id="s1c" class="sd-parse">
The cat could have chased all the dogs down the street .
punct(chased, .)
</div>

カンマを置くことで依存木を完全にする．内部の節点 (nodes) は内容語であり，機能語とカンマは枝葉として現れる．

<div id="s1" class="sd-parse">
The cat could have chased all the dogs down the street .
nsubj(chased, cat)
obj(chased, dogs)
obl(chased, street)
det(cat, The)
aux(chased, could)
aux(chased, have)
det(dogs, all)
det(dogs, the-7)
case(street, down)
det(street, the-10)
punct(chased, .)
</div>

主辞が内容語を選好することで言語間の並行性は最大限に高まることとなる．それは，内容語の変異が機能語に比べて少ないためである．特に，いくつかの言語や構文では同一の文法関係が形態論によって表現され，他の言語では機能語によって表現されることが普通だが，そのような情報を全く標示しない言語もあるかもしれない (時制や定性を標示しない，といったように).

<div id="s2a" class="sd-parse">
On a dormi ...
nsubj(dormi, On)
aux(dormi, a)
</div>

<div id="s2b" class="sd-parse">
We slept ...
nsubj(slept, We)
</div>

<div id="s2c" class="sd-parse">
Ivan is the best dancer
nsubj(dancer, Ivan)
cop(dancer, is)
det(dancer, the)
amod(dancer, best)
</div>

<div id="s2d" class="sd-parse">
Ivan lučšij tancor
nsubj(tancor, Ivan)
amod(tancor, lučšij)
</div>

## The Status of Function Words

内容語の卓越は機能語が通常それ自身では依存部を持たないことを含意する．特に，同一の内容語に関連する複数の機能語は兄弟 (sibling) として生起し，解釈に関わらず埋め込み構造をとらない．典型例は助動詞であり，互いに依存関係を結ばない．

<div id="s3a" class="sd-parse">
She could have been injured .
aux(injured, could)
aux(injured, have)
aux:pass(injured, been)
</div>

この観点からは，コピュラ動詞 (copula verbs) も助動詞となる．コピュラ構文では，助動詞が動詞以外の述語に付加することがよくある．

<div id="s3b" class="sd-parse">
She could have been sick .
aux(sick, could)
aux(sick, have)
cop(sick, been)
</div>

同様に，複数の限定詞は常に主辞の名詞に付加される．

<div id="s3c" class="sd-parse">
All these three books .
det(books, All)
det(books, these)
nummod(books, three)
</div>

機能語を内容語の依存部として形式的に扱うことは，多数の統語的構文で逆の関係を選好するような他の依存文法と比べると異質であることを意識しておく必要がある．UDでは内容語と機能語との関係を狭義の依存関係とみなすのではなく，内容語の文法カテゴリを修飾する操作としてみなすことによって他の内容語とは異なる依存関係に参与させることが可能となる．内容語間の依存関係とは異なることを強調したいとき，それらの関係は_機能関係_もしくは_機能語関係_と呼ばれる．この見方は，機能語を (構造的にではなく) 機能的に形態論的操作へと類似させ，またTesnièreが仮定した統語的な依存関係の中心としての核 (nucleus) の概念とも整合する．

しかし，機能後が依存部とならないような，4つの重要な例外が存在する:

  1. 複合的な機能語 (Multiword function words)
  2. 並置された機能語 (Coordinated function words)
  3. 機能語の修飾句 (Function word modifiers)
  4. 主辞の省略による昇格 (Promotion by head elision)

### Multiword Function Words

固定的な機能語の複合表現 (multiword expression; MWE) を形成する語は [u-dep/fixed]() という特別な関係によって結合される．慣習的に先頭の語は主辞として扱われるため，複合表現が機能的要素であるとき，先頭の語は表層的に依存部を伴う機能語のように見える．

<div id="s6" class="sd-parse">
We had a nice time in spite of the rain .
case(rain,in)
fixed(in,spite)
fixed(in,of)
obl(had,rain)
</div>

ある表現が固定のMWEとして扱われるかの判断は，各々の言語によって決定されるべきであり，恣意的な慣習に従う場合もある．それは，文法化 (grammaticalization) の過程からある一点を抜き出すことに関わるからである．大抵の言語は，リンカー (linker)，標示 (marks) や格助詞 (case particle) といった，機能語のようにふるまう一般的なMWEがあるとはいえ，これらを複合的な機能語としてみなすことが望ましいわけではない．英語の例には _in spite of_ (_despite_に類似)，_as well as_ (_and_に類似) や _prior to_ (_before_に類似) といったものが含まれる．.

### Coordinated Function Words

主辞の並置は，接続詞や前置詞といった機能語を含むほとんどの品詞に適用できる統語プロセスである．そのような場合並置の標準的な分析が用いられ，機能語は依存部を持つことになる．

<div id="s4a" class="sd-parse">
She drove to and from work .
case(work,to)
conj(to, from)
cc(from, and)
</div>

<div id="s4b" class="sd-parse">
I will do that if and when it happens .
mark(happens,if)
conj(if, when)
cc(when, and)
</div>

### Function Word Modifiers

特定のタイプの機能語は，修飾句の限定的なクラス，主に軽副詞 (light adverbials; 否定辞を含む) をとることが可能である．典型的な例としては _not every (linguist)_ や _exactly two (papers)_ のような修飾された限定詞や従属接続詞の修飾句がある．

<div id="s7a" class="sd-parse">
not every linguist
det(linguist, every)
advmod(every, not)
</div>

<div id="s7b" class="sd-parse">
exactly two papers
det(papers, two)
advmod(two, exactly)
</div>

<div id="s7c" class="sd-parse">
just when you thought it was over
mark(thought, when)
advmod(when, just)
</div>

否定辞は任意の機能語を修飾できるが，他のタイプの修飾句では，主辞の性質を表現し，他の言語において形態的に表現されるような機能語には修飾することが認められない．_純粋な機能語 (pure function words)_ と呼ばれる，このクラスには助動詞，格付与マーカー (後置詞) および冠詞が含まれるが，各々の言語において明示的に定義される必要がある．純粋な機能語が否定辞以外の修飾句と生起したとき，修飾句を句全体に適用させて機能語の主辞に付加する．これは以下の例によって示される． 

<div id="s7d" class="sd-parse">
right before midnight
case(midnight, before)
advmod(midnight, right)
</div>

ここでは_right_が_before midnight_の句全体を修飾し，主辞である_midnight_へ付加するという分析が与えられる．(句の修飾が主辞の修飾と区別されないのは依存木の一般的性質である．) この分析は_before midnight_を副詞の_then_で置き換えが可能なことからも支持される．

<div id="s7e" class="sd-parse">
right then
advmod(then, right)
</div>

純粋な機能語が依存部を持たないと保証することは，対応する性質が形態的に示される言語との比較を促す．<!-- as well as conversion to the enhanced representation where this difference is neutralized.-->

要約すると，機能語の修飾句の扱いは3つの原則によって表される:

  1. 純粋な機能語は否定辞によってのみ修飾される．
  2. 他の機能語は軽副詞の修飾語をとる．
  3. 迷いが生じる場合は，機能語が内容語に付加されるような平板な構造 (flat structure) として扱うこと. 

また，言語特有のドキュメンテーションでは当該言語で何の語が純粋な機能語として扱われるかを特定すべきであることに注意されたい．

### Promotion by Head Elision

機能語の通常の主辞が省略される (elided) とき，機能語は，通常であれば内容語が主辞となるような関係に"昇格"する．このタイプの分析は，構造の断続が少なるため，一般的に関係 [u-dep/orphan]() を用いたものよりも選好される．よって，orphanを用いた分析は昇格できる機能語が存在しないときに限って行われるべきである．以下の例では助動詞，前置詞および従属接続詞の昇格を示している (ただし，最初の例のみが機能語が依存部を持たないことへの例外を示している)．
<div id="s5a" class="sd-parse">
Bill could not answer , but Ann could .
nsubj(answer, Bill)
aux(answer, could-2)
conj(answer, could-8)
nsubj(could-8, Ann)
</div>

<div id="s5b" class="sd-parse">
The address she wrote to .
acl:relcl(address, wrote)
nsubj(wrote, she)
obl(wrote, to)
</div>

<div id="s5c" class="sd-parse">
I know how .
nsubj(know, I)
ccomp(know, how)
</div>

## The Taxonomy of Typed Dependencies

以降，タイプ付けされた依存関係の分類法に関する重要概念について，いくつか検討していく．まず，内容語間の中心的な依存関係に注目する．

### Core Arguments vs. Oblique Modifiers

UDの分類法で専念するのは，必須項 (主語，目的語，節の補部) と他の依存部の区別についてである．この分類法では付加詞 (一般に修飾句) と斜格項 (主辞によって選択されるが必須でない項) をしない．このセクションの残りでは，これらの選択に関する言語的証拠を挙げていくが，飛ばしても構わない．

#### The definition of core arguments

必須項/斜格項の区別は，つまるところ情報の与え方の区別に求められる．全て，あるいは大半の言語には，大抵の動詞 (自動詞および他動詞) で1つか2つの項を表現する手段があり，項の無標 (unmarked) な形式は必須項である．必須項と同じように扱われる追加の項が生起可能な場合，それらも必須項としてみなされるかもしれない．(例えば，いくつかの言語では追加の必須項を持たないが，他の言語では複数の目的語項を許す．) 必須項は参与者の意味役割とは分離している．通常は，項を表す同一の手段を用いつつも動詞の意味によって様々な意味役割が表現されるが，相関性は存在する: 無標の原子価 (valence) において，述語の行為者 (agent) や被行為者 (patient)， もしくは主題 (theme) といった意味役割は通常必須項として実現する．

統語的には必須項から斜格を区別するような唯一の基準は存在しないものの，特定の言語において有用な基準は存在する．これらは以下のものを含む:

* 動詞は必須項のみと一致 (agree) する
* 斜格項は後置詞によって標示される一方，必須項は名詞句単体で生起する
* 伝統的に主格，対格，絶対格と呼ばれる特定の項は典型的に必須項を標示する
* いくつかの言語において必須項は節の特別な位置 (動詞に隣接) を占める
* 従属節の項のコントローラーや関係節化のターゲットを形成するような統語現象において，その対象は必須項に限定される

要するに，必須項と斜格は言語特有の観点から区別されるのである．例えば，多くの言語には与格もしくは経験者といった斜格の項を取る動詞があるが，これらの項は他動詞の項と並行的に扱われる統語的ふるまいに基づき，必須項としてみなされる．

#### Avoiding an argument/adjunct distinction

多くの文法的枠組みでは，斜格のいくつかは主辞から選択されるか，その項となる (例えば，_from the Queen_ の起点項 (source argument) は _receive_ の主辞である)．一方で，他の斜格は一般的な付加詞であり，選択を行う主辞を伴わずに述語と共起する (例えば， _after the holidays_ の時間項 (temporal argument) )．

しかし，項/付加詞の区別は微妙なもので，議論が絶えない．例えば，統語論者が様々な斜格を項だと主張する時もあれば，道具や発生源の意味役割を示す斜格が付加詞であると主張する時もあった．ここでは，その区別が微細なもので，実践的に最良の解決策とは区別を取り払うことだと考える．このアプローチはPennツリーバンクの元々の考えに軌を一にしている．

必須項と斜格の区別は言語類型論で認められ，両者は項と付加詞の区別よりも通言語的に適用が容易である．例として以下を参照されたい:

* Avery D. Andrews. 2007. The Major Functions of the Noun Phrase. In Timothy Shopen (ed.) Language Typology and Syntactic Description: Clause Structure (2nd ed), Cambridge University Press, Cambridge, United Kingdom, pp. 132-223. (1st edition, 1985.)
* Sandra A. Thompson. 1997. Discourse Motivations for the Core-Oblique Distinction as a Language Universal. In Akio Kamio (ed.) Directions in Functional Linguistics. Benjamins, Amsterdam, the Netherlands, pp. 59-82.

### A Mixed Functional-Structural System

依存関係の主要な役割の一つは機能 (function) を表示することにあるが，UDは構造概念もエンコードする．構造的な側面では，言語は原則的に3つの事柄に関与する:

* 名詞句 (存在物を表現する通常の手段であり，他の事物にも用いられる場合がある)
* 述語が主辞となる節 (多くは動詞であるが，形容詞，副詞，もしくは _He is **a wreck**_ のような叙述名詞である場合もある)
* それ自体が修飾を許すような，他の修飾語 (しかし，名詞句や述語ほど豊かな構造へと拡張できない)

3つの区別は通常，依存関係の名称にエンコードされる．例えば，動詞が副詞の修飾句を取る場合，[u-dep/obl](), [u-dep/advcl](), または [u-dep/advmod]() のいずれか1つで表される．

<div id="fss1" class="sd-parse">
John talked in the movie theatre
case(theatre, in)
det(theatre, the)
compound(theatre, movie)
obl(talked, theatre)
</div>

<div id="fss2" class="sd-parse">
John talked while we were watching the movie
mark(watching, while)
nsubj(watching, we)
aux(watching, were)
advcl(talked, watching)
det(movie, the)
obj(watching, movie)
</div>

<div id="fss3" class="sd-parse">
John talked very quickly
advmod(quickly, very)
advmod(talked, quickly)
</div>

同じように，必須の文法関係は節を成す必須項から名詞句であるもの (例: [u-dep/nsubj](), [u-dep/obj]()) を区別する．
<!--以下，元々コメントアウトされている部分-->
<!-- ### Voice

Relation names attempt to differentiate canonical voice (where the proto-agent argument is the subject) from non-canonical voice constructions (where another argument is the subject). This is marked as appropriate on both the subject argument (e.g., nsubjpass) and auxiliaries indicating this (auxpass). Marking both is helpful, as either may be missing.
-->

### Clausal Dependents

節内にある述語の依存部を分類するため，UDの分類法は以下の原則に準拠する:

- 必須項を必須でない項と付加詞から区別すること (上記の "Core arguments vs. oblique modifiers" を参照)
- 主語を補部から区別すること
- 義務的なコントロールを受ける節を，他の主語の認可 (subject licensing) を受ける節から区別すること
- 主語への付加要素と名詞句への付加要素を区別すること
- 関係節の形式をとらない，名詞に対する修飾節を捉えること

さらなる区別 (例えばヴォイスに関するもの) は言語特有の下位タイプによって捉えられる (受動化した動詞の主語に対する `nsubj:pass` のように)．
UDの分類法では，定節と不定節の区別を試みないことに注意されたい．

### Coordination

等位構造 (coordinate structures) は非対照的に扱う:
主辞は先頭の等位要素 (conjunct) であり，他の全ての要素は主辞に依存する．これは，関係 [u-dep/conj]() によって示される．等位接続詞および，等位要素を限定するカンマは，それぞれ [u-dep/cc]() と [u-dep/punct]() を用いて **後続する** 要素に付加される．  

~~~ sdparse
He came home , took a shower and immediately went to bed .
conj(came, took)
conj(came, went)
punct(took, ,-4)
cc(went, and)
~~~

### Multiword Expressions

複合表現 (multiword expressions; MWWs) は，(ある側面において程度差はあるが) 構成的な統語句というより語彙単位として振る舞うような語の組み合わせである．UDの分類法ではMEWsの分析用に3つの特別な関係を含む:

* [u-dep/fixed]() は _in spite of_ のように，文法化した機能語であるMWEsを分析するために用いられる
* [u-dep/flat]() は _Barack Obama_ のように，明らかな主辞を持たない，外心的 (exocentric) で半ば固定したMEWsを分析するために用いられる
* [u-dep/compound]() は ，_phrase_ が 主辞となる _noun phrase_ のような (主辞を持つ/内心的である) 複合語を分析するために用いられる

[u-dep/fixed]() と [u-dep/flat]() から分析される構造は定義的に主辞を欠いており，これらは先頭の要素にその他の要素が付加することでタグ付けされる．<!--only allowing outgoing dependents from the first element-->

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

対照的に，[compounds](compound) は，主辞 (head) の概念を含む修飾構造を明示するためにタグ付けされる:

<div id="s9" class="sd-parse">
I bought a computer disk drive enclosure .
nsubj(bought, I)
det(enclosure, a)
compound(drive, computer)
compound(drive, disk)
compound(enclosure, drive)
obj(bought, enclosure)
</div>

### Special Relations

必須の依存関係，機能関係，等位を分析する関係やMEWや句読点に加えて，UDの分類法にはテクストの誤字，話しでの非流暢性 (disfluencies) や内部に統語構造を持たないリスト構造を扱うような特別な関係を備えている．

<!--以下，元々コメントアウトされている文書-->
<!--Some of the universal relations do not really encode syntactic dependency relations but are used to represent
punctuation, various kinds of multiword units, or unanalyzable segments. The use of these relations is subject
to special restrictions explained below.

Tokens with the relation [u-dep/punct]() always attach to content words (except in cases of ellipsis) and can never have dependents.

Since `punct` is not a normal dependency relation, the usual criteria for determining the head word do not apply.
Instead, we use the following principles:

1. A punctuation mark separating coordinated units is attached to the first conjunct.
2. A punctuation mark preceding or following a subordinated unit is attached to this unit.
3. Within the relevant unit, a punctuation mark is attached at the highest possible node that preserves projectivity.
4. Paired punctuation marks (quotes and brackets) should be attached to the same word unless that would create non-projectivity. This word is usually the head of the phrase enclosed in the paired punctuation.

<div id="punct1" class="sd-parse">
We have apples , pears , oranges , and bananas .
obj(have, apples)
conj(apples, pears)
conj(apples, oranges)
conj(apples, bananas)
cc(apples, and)
punct(apples, ,-4)
punct(apples, ,-6)
punct(apples, ,-8)
</div>

<div id="punct2" class="sd-parse">
Der Mann , den Sie gestern kennengelernt haben , kam wieder .
punct(kennengelernt, ,-3)
punct(kennengelernt, ,-9)
punct(kam, .)
</div>

<div id="punct3" class="sd-parse">
A.K.A. , AKA , or a\/k\/a may refer to : “ Also known as ” , used to introduce pseudonyms , aliases , etc. ( Compare f.k.a. for “ formerly known as ” . )
punct(A.K.A., ,-2)
punct(A.K.A., ,-4)
punct(refer, :)
punct(known-13, “-11)
punct(known-13, ”-15)
punct(used, ,-16)
punct(pseudonyms, ,-21)
punct(pseudonyms, ,-23)
punct(Compare, (-25)
punct(Compare, )-35)
punct(known-31, “-29)
punct(known-31, ”-33)
punct(Compare, .-34)
</div>
-->
