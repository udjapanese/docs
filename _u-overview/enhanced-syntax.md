　---
layout: base
title:  'Enhanced Dependencies'
permalink: u/overview/enhanced-syntax.html
udver: '2'
---

# Enhanced Dependencies

UD (Universal Dependency) は，関係の抽出や生物医学的な事象抽出といった，shallow 自然言語理解タスクに用いることを志向する．そのようなタスクでは，特定のエンティティ間の関係 (e.g., 2者の関係，単一のタンパク質が他方へ交流するかどうか，など) が典型的に興味対象となる．UDのツリーには内容語間の直接的な関係を多数含んでいて，依存関係ラベルは二語間の関係タイプの情報を多く提供するため，UDはそのようなタスクに適している．しかし，いくつかの構文では，当該の二語間の依存関係の経路がツリー内で長大になる場合があり，内容語同士の関係を決定するのが複雑となる．さらに，[`obl`](u-dep/obl) や [`nmod`](u-dep/nmod) といった依存関係タイプは様々な項や修飾語に対して用いられるため，依存関係自体の情報度が高いとは言えない．これらの理由から，_拡張された_表示 (enhanced representation) に対するガイドラインを提供する．拡張表示は語間の関係を明示化し，項や修飾語のタイプの曖昧性を解消するように依存ラベルを補強するものである．


_拡張版_のUDのグラフは以下の拡張を含みうるもので，それぞれ以下のセクションで論じられる．

* [省略要素の空のノード](#ellipsis)
* [等位接続の伝播](#propagation-of-conjuncts)
* [コントロール構文，上昇構文のための追加の主語関係](#controlledraised-subjects)
* [関係詞節内の同一指示](#relative-clauses)
* [前置詞や格標示の情報を含む修飾ラベル](#case-information)

* [Null nodes for elided predicates](#ellipsis)
* [Propagation of conjuncts](#propagation-of-conjuncts)
* [Additional subject relations for control and raising constructions](#controlledraised-subjects)
* [Coreference in relative clause constructions](#relative-clauses)
* [Modifier labels that contain the preposition or other case-marking information](#case-information)

注意が必要なのは，_拡張_グラフは必ずしも基本的なツリーのスーパーグラフとは限らないことである．すなわち，そのグラフは基本的な依存関係の全てを含む必要はない．この理由より，拡張グラフのあらゆる関係 (基本のツリーにある関係も) はCoNLL-Uファイルの_DEPS_カラムに含めておく必要がある．詳細は [CoNLL-U](/format.html) のファイルフォーマットの指定法を参照すること．

さらに，DEPS内の拡張グラフにおける依存関係ラベルは，DEPRELカラム内にある基本関係タイプでは許されない，特定の拡張を含むことがある．DEPREL内の関係を限定する正規表現は極めて単純である;
ラベルには小文字の英字と最大1つのコロンのみを含み，コロンによって言語普遍的なラベルと言語特有のものとを区別する: `^[a-z]+(:[a-z]+)?$`. 対照的に，DEPS内の関係ラベルはコロンを3つまで含むので，ラベルは最大で4つに分割される．ラベルの一部分 (先頭部分を除いて) には，ユニコード文字とアンダースコアも含むことがある:
`^[a-z]+(:[a-z]+)?(:[\p{Ll}\p{Lm}\p{Lo}\p{M}]+(_[\p{Ll}\p{Lm}\p{Lo}\p{M}]+)*)?(:[a-z]+)?$`.
普遍的関係 (universal relation) はラベルの先頭部分でのみ必須である．他の部分では任意的であるが，以下に記される生起順序に従う．より詳細な解説は本ページ後半のセクションで行う; 概略は次の通り:

1. 普遍的依存関係．基本的表示において定義される [37関係](http://universaldependencies.org/u/dep/index.html) に加えて，<tt><a href="#relative-clauses">ref</a></tt> も可能である.
2. 基本的表示から記録された [関係のサブタイプ](/ext-dep-index.html) (言語特有のものか，一般的なものであっても) ．
3. [格情報](#case-information) –
   等位接続詞や接続詞で，`case` もしくは `mark` の依存部adposition or conjunction that occurs as a `case` or `mark` dependent of the node whose relation to its
   parent is being enhancedただし，拡張関係ラベル内でアスキー文字でないものが生起できる部分に限られることに注意．
   語は標準化される (小文字にする，タイポを直す) べきであり，つまり，語彙素を (lemma) を用いる．格/標示の依存部が固定化した複合表現である場合，必ずしも当該表現の語彙素が要素の個々の語彙素から構成されるとは限らない.例えば，英語表現“As Opposed To”を表す文字列は`as_opposed_to`と表記される．すなわち，レターケースは“As”から“as”へと標準化されるが，この表現は固定表現であるため，“opposed”は“oppose”の語彙素によって置き換えることができない．要素の語を結合する際はアンダースコア (“_”) を用いる.
4. [格情報](#case-information) –
   その親の関係が拡張されるような，ノードにおける形態格．値は格素性に対応するが，
   小文字で表記する (e.g., `Gen`の代わりに`gen`)．形態素性とは異なり，カンマを伴う多値な格情報 (`Case=Acc,Dat`) は拡張関係内に存在するが，十分に曖昧さを取り除いておく必要がある．


## Ellipsis


([ellipsis](specific-syntax.html#ellipsis) のガイドラインも参照.)

_拡張_表示では，述語が省略された節において特別な空のノード (null nodes) が追加される．

<table id="ellipsis-example1"> <!--I like tea and you E5.1 rum .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 6 orphan color:green
# visual-style 2 5 conj color:green
# visual-style 5 4 cc color:green
1 I      _ _ _ _ 2 nsubj  _ _
2 like   _ _ _ _ 0 root   _ _
3 tea    _ _ _ _ 2 obj    _ _
4 and    _ _ _ _ 5 cc     _ _
5 you    _ _ _ _ 2 conj   _ _
6 coffee _ _ _ _ 5 orphan _ _
7 .      _ _ _ _ 2 punct  _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 6 7 obj color:blue
# visual-style 6 5 nsubj color:blue
# visual-style 2 6 conj color:blue
# visual-style 6 4 cc color:blue
1 I      _ _ _ _ 2 nsubj _ _
2 like   _ _ _ _ 0 root  _ _
3 tea    _ _ _ _ 2 obj   _ _
4 and    _ _ _ _ 6 cc    _ _
5 you    _ _ _ _ 6 nsubj _ _
6 E5.1   _ _ _ _ 2 conj  _ _
7 coffee _ _ _ _ 6 obj   _ _
8 .      _ _ _ _ 2 punct _ _
</div>
</td></tr></tbody>
</table>

<table id="ellipsis-example2"> <!--Mary wants to buy a book and Jenny E8.1 E8.2 a CD .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 8 10 orphan color:green
# visual-style 2 8 conj color:green
# visual-style 8 7 cc color:green
1  Mary  _ _ _ _ 2  nsubj  _ _
2  wants _ _ _ _ 0  root   _ _
3  to    _ _ _ _ 4  mark   _ _
4  buy   _ _ _ _ 2  xcomp  _ _
5  a     _ _ _ _ 6  det    _ _
6  book  _ _ _ _ 4  obj    _ _
7  and   _ _ _ _ 8  cc     _ _
8  Jenny _ _ _ _ 2  conj   _ _
9  a     _ _ _ _ 10 det    _ _
10 CD    _ _ _ _ 8  orphan _ _
11 .     _ _ _ _ 2  punct  _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 9 8 nsubj color:blue
# visual-style 10 12 obj color:blue
# visual-style 9 10 xcomp color:blue
# visual-style 9 7 cc color:blue
# visual-style 4 1 nsubj color:blue
# visual-style 10 8 nsubj color:blue
1  Mary  _ _ _ _ 2  nsubj 4:nsubj _
2  wants _ _ _ _ 0  root  _ _
3  to    _ _ _ _ 4  mark  _ _
4  buy   _ _ _ _ 2  xcomp _ _
5  a     _ _ _ _ 6  det   _ _
6  book  _ _ _ _ 4  obj   _ _
7  and   _ _ _ _ 9  cc     _ _
8  Jenny _ _ _ _ 9  nsubj 10:nsubj _
9  E8.1  _ _ _ _ 2  conj  _ _
10 E8.2  _ _ _ _ 9  xcomp _ _
11 a     _ _ _ _ 12 det   _ _
12 CD    _ _ _ _ 10 obj   _ _
13 .     _ _ _ _ 2  punct _ _
</div>
</td></tr></tbody>
</table>

これは，_基本_ツリーが_拡張_UDグラフにない関係`orphan`を含んでいるため，_拡張_UDグラフが_基本_ツリーのスーパーグラフではない事例であることに注意したい．


## Propagation of Conjuncts

_基本_表示においては，支配項 (governor) と並列句の依存部が両方とも最初の等位要素に付加されている．これは，内容語間の長大な依存関係の経路を生み出す．ゆえに，_拡張_表示には他の等位要素，句における支配項や依存部も含める．

### Conjoined verbs and verb phrases

2つの動詞が目的語 (もしくは他の補部) を共有しているとき，等位関係にある動詞の主語と目的語は全ての接続要素に付加される．


<table> <!--The store buys and sells cameras .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 The     _ _ _ _ 2 det   _ _
2 store   _ _ _ _ 3 nsubj _ _
3 buys    _ _ _ _ 0 root  _ _
4 and     _ _ _ _ 5 cc    _ _
5 sells   _ _ _ _ 3 conj  _ _
6 cameras _ _ _ _ 3 obj   _ _
7 .       _ _ _ _ 3 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 2 nsubj color:blue
# visual-style 5 6 obj color:blue
1 The     _ _ _ _ 2 det   _ _
2 store   _ _ _ _ 3 nsubj 5:nsubj _
3 buys    _ _ _ _ 0 root  _ _
4 and     _ _ _ _ 5 cc    _ _
5 sells   _ _ _ _ 3 conj  _ _
6 cameras _ _ _ _ 3 obj   5:obj _
7 .       _ _ _ _ 3 punct _ _
</div>
</td></tr></tbody>
</table>

しかし，2番目の動詞の補部が共有されていない場合，全ての等位要素に付加されるのは共有された依存部のみである．

<table> <!--She was reading or watching a movie .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 She      _ _ _ _ 3 nsubj _ _
2 was      _ _ _ _ 3 aux   _ _
3 reading  _ _ _ _ 0 root  _ _
4 or       _ _ _ _ 5 cc    _ _
5 watching _ _ _ _ 3 conj  _ _
6 a        _ _ _ _ 7 det   _ _
7 movie    _ _ _ _ 5 obj   _ _
8 .        _ _ _ _ 3 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 1 nsubj color:blue
# visual-style 5 2 aux color:blue
1 She      _ _ _ _ 3 nsubj 5:nsubj _
2 was      _ _ _ _ 3 aux   5:aux _
3 reading  _ _ _ _ 0 root  _ _
4 or       _ _ _ _ 5 cc    _ _
5 watching _ _ _ _ 3 conj  _ _
6 a        _ _ _ _ 7 det   _ _
7 movie    _ _ _ _ 5 obj   _ _
8 .        _ _ _ _ 3 punct _ _
</div>
</td></tr></tbody>
</table>

同様に，拡張表示は最初の動詞のみに対する依存部を区別することが可能である．ただし，このケースでは基本表示から自動的に推測することができないので注意したい．

<table> <!--She was reading or watching a movie .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 She      _ _ _ _ 3 nsubj _ _
2 was      _ _ _ _ 3 aux   _ _
3 watching _ _ _ _ 0 root  _ _
4 a        _ _ _ _ 5 det   _ _
5 movie    _ _ _ _ 3 obj   _ _
6 or       _ _ _ _ 7 cc    _ _
7 reading  _ _ _ _ 3 conj  _ _
8 .        _ _ _ _ 3 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 7 1 nsubj color:blue
# visual-style 7 2 aux color:blue
1 She      _ _ _ _ 3 nsubj 7:nsubj _
2 was      _ _ _ _ 3 aux   7:aux _
3 watching _ _ _ _ 0 root  _ _
4 a        _ _ _ _ 5 det   _ _
5 movie    _ _ _ _ 3 obj   _ _
6 or       _ _ _ _ 7 cc    _ _
7 reading  _ _ _ _ 3 conj  _ _
8 .        _ _ _ _ 3 punct _ _
</div>
</td></tr></tbody>
</table>

### Conjoined subjects and objects

主語が等位関係にある名詞句であるとき，等位要素はそれぞれ述語へ付加される．


<table> <!--Paul and Mary are running .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Paul    _ _ _ _ 5 nsubj _ _
2 and     _ _ _ _ 3 cc    _ _
3 Mary    _ _ _ _ 1 conj  _ _
4 are     _ _ _ _ 5 aux   _ _
5 running _ _ _ _ 0 root  _ _
6 .       _ _ _ _ 5 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 3 nsubj color:blue
1 Paul    _ _ _ _ 5 nsubj _ _
2 and     _ _ _ _ 3 cc    _ _
3 Mary    _ _ _ _ 1 conj  5:nsubj _
4 are     _ _ _ _ 5 aux   _ _
5 running _ _ _ _ 0 root  _ _
6 .       _ _ _ _ 5 punct _ _
</div>
</td></tr></tbody>
</table>

これは，等位関係にある目的語においても同様である．

<table> <!--Paul bought apples and oranges .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Paul    _ _ _ _ 2 nsubj _ _
2 bought  _ _ _ _ 0 root  _ _
3 apples  _ _ _ _ 2 obj   _ _
4 and     _ _ _ _ 5 cc    _ _
5 oranges _ _ _ _ 3 conj  _ _
6 .       _ _ _ _ 2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 5 obj color:blue
1 Paul    _ _ _ _ 2 nsubj _ _
2 bought  _ _ _ _ 0 root  _ _
3 apples  _ _ _ _ 2 obj   _ _
4 and     _ _ _ _ 5 cc    _ _
5 oranges _ _ _ _ 3 conj  2:obj _
6 .       _ _ _ _ 2 punct _ _
</div>
</td></tr></tbody>
</table>

これは，集合的 (collective) な主語や目的語においては幾分奇妙な依存関係を生むことになる．

<table> <!--Paul and Mary are meeting .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Paul    _ _ _ _ 5 nsubj _ _
2 and     _ _ _ _ 3 cc    _ _
3 Mary    _ _ _ _ 1 conj  _ _
4 are     _ _ _ _ 5 aux   _ _
5 meeting _ _ _ _ 0 root  _ _
6 .       _ _ _ _ 5 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 3 nsubj color:blue
1 Paul    _ _ _ _ 5 nsubj _ _
2 and     _ _ _ _ 3 cc    _ _
3 Mary    _ _ _ _ 1 conj  5:nsubj _
4 are     _ _ _ _ 5 aux   _ _
5 meeting _ _ _ _ 0 root  _ _
6 .       _ _ _ _ 5 punct _ _
</div>
</td></tr></tbody>
</table>

<table> <!--Mary is eating mac and cheese .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Mary   _ _ _ _ 3 nsubj _ _
2 is     _ _ _ _ 3 aux    _ _
3 eating _ _ _ _ 0 root  _ _
4 mac    _ _ _ _ 3 obj   _ _
5 and    _ _ _ _ 6 cc  _ _
6 cheese _ _ _ _ 4 conj  _ _
7 .      _ _ _ _ 3 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 3 6 obj color:blue
1 Mary   _ _ _ _ 3 nsubj _ _
2 is     _ _ _ _ 3 aux    _ _
3 eating _ _ _ _ 0 root  _ _
4 mac    _ _ _ _ 3 obj   _ _
5 and    _ _ _ _ 6 cc  _ _
6 cheese _ _ _ _ 4 conj  3:obj _
7 .      _ _ _ _ 3 punct _ _
</div>
</td></tr></tbody>
</table>

ただし，分散読み (distributive reading) と集合読み (collective reading) の違いは文脈に依存することがよくあるので，ここでは単純なアプローチを採り，全ての等位要素を述語へと付加させる．

主語が，コントロール構文もしくは上昇構文の述語の主語であるとき，主節動詞 (matrix verb) と等位要素間の依存関係が存在し，埋め込み動詞 (embedded verb) と等位要素間の依存関係が存在する．

<table> <!--Mary and John wanted to buy a hat .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Mary   _ _ _ _ 4 nsubj _ _
2 and    _ _ _ _ 3 cc    _ _
3 John   _ _ _ _ 1 conj  _ _
4 wanted _ _ _ _ 0 root  _ _
5 to     _ _ _ _ 6 mark  _ _
6 buy    _ _ _ _ 4 xcomp _ _
7 a      _ _ _ _ 8 det   _ _
8 hat    _ _ _ _ 6 obj   _ _
9 .      _ _ _ _ 4 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 4 3 nsubj color:blue
# visual-style 6 1 nsubj color:blue
# visual-style 6 3 nsubj color:blue
1 Mary   _ _ _ _ 4 nsubj 6:nsubj _
2 and    _ _ _ _ 3 cc    _ _
3 John   _ _ _ _ 1 conj  4:nsubj|6:nsubj _
4 wanted _ _ _ _ 0 root  _ _
5 to     _ _ _ _ 6 mark  _ _
6 buy    _ _ _ _ 4 xcomp _ _
7 a      _ _ _ _ 8 det   _ _
8 hat    _ _ _ _ 6 obj   _ _
9 .      _ _ _ _ 4 punct _ _
</div>
</td></tr></tbody>
</table>

### Conjoined modifiers

等位関係にある修飾句の各要素は，修飾句の支配項へ付加される．例えば，次の句では等位関係を成す形容詞句が名詞を修飾していおり，拡張表示では，関係`amod`が名詞_river_と2番目の形容詞_wide_の間に成立する．

<table> <!--a long and wide river-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 a     _ _ _ _ 5 det  _ _
2 long  _ _ _ _ 5 amod _ _
3 and   _ _ _ _ 4 cc   _ _
4 wide  _ _ _ _ 2 conj _ _
5 river _ _ _ _ 0 root _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 4 amod color:blue
1 a     _ _ _ _ 5 det  _ _
2 long  _ _ _ _ 5 amod _ _
3 and   _ _ _ _ 4 cc   _ _
4 wide  _ _ _ _ 2 conj 5:amod _
5 river _ _ _ _ 0 root _ _
</div>
</td></tr></tbody>
</table>


## Controlled/raised subjects

_基本_ツリーは，コントロールされた動詞とコントローラー間，もしくは埋め込み動詞と上昇した主語間にある依存関係を欠いている．_拡張_グラフには，埋め込み動詞と主節主語間の依存関係が存在する．

<table id="control-raising-example1"> <!--Mary wants to buy a book .-->
<thead><tr><th>Basic</th><th>Enhanced</th></tr></thead>
<tbody><tr><td width="600">
<div class="conllu-parse">
1 Mary  _ _ _ _ 2 nsubj _ _
2 wants _ _ _ _ 0 root  _ _
3 to    _ _ _ _ 4 mark  _ _
4 buy   _ _ _ _ 2 xcomp _ _
5 a     _ _ _ _ 6 det   _ _
6 book  _ _ _ _ 4 obj   _ _
7 .     _ _ _ _ 2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 4 1 nsubj color:blue
1 Mary  _ _ _ _ 2 nsubj 4:nsubj _
2 wants _ _ _ _ 0 root  _ _
3 to    _ _ _ _ 4 mark  _ _
4 buy   _ _ _ _ 2 xcomp _ _
5 a     _ _ _ _ 6 det   _ _
6 book  _ _ _ _ 4 obj   _ _
7 .     _ _ _ _ 2 punct _ _
</div>
</td></tr></tbody>
</table>

<table id="control-raising-example2"> <!--She seems to be reading a book .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 She     _ _ _ _ 2 nsubj _ _
2 seems   _ _ _ _ 0 root  _ _
3 to      _ _ _ _ 5 mark  _ _
4 be      _ _ _ _ 5 aux   _ _
5 reading _ _ _ _ 2 xcomp _ _
6 a       _ _ _ _ 7 det   _ _
7 book    _ _ _ _ 5 obj   _ _
8 .       _ _ _ _ 2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 1 nsubj color:blue
1 She     _ _ _ _ 2 nsubj 5:nsubj _
2 seems   _ _ _ _ 0 root  _ _
3 to      _ _ _ _ 5 mark  _ _
4 be      _ _ _ _ 5 aux   _ _
5 reading _ _ _ _ 2 xcomp _ _
6 a       _ _ _ _ 7 det   _ _
7 book    _ _ _ _ 5 obj   _ _
8 .       _ _ _ _ 2 punct _ _
</div>
</td></tr></tbody>
</table>


## Relative clauses

_基本_ツリーでは，関係代名詞は関係節の主述語へと付加される (典型的には関係`nsubj`か`obj`を用いて)．対応する_拡張_グラフでは，関係代名詞は特別な関係`ref`を用いて先行詞へと付加され，先行詞は項として関係詞の主述語へ付加される．関係代名詞が生起しないケースでは，後者のアーク (枝) のみが追加される．そのようなグラフには閉路 (cycle) が含まれることに注意されたい．

<table> <!--the boy who lived-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 4 3 nsubj color:green
1 the   the   DET _ Definite=Def|PronType=Art 2 det       _ _
2 boy   boy   NOUN _ Gender=Masc|Number=Sing 0 root      _ _
3 who   who   PRON _ PronType=Rel 4 nsubj     _ _
4 lived lived VERB _ Mood=Ind|Tense=Past|VerbForm=Fin 2 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 4 2 nsubj color:blue
# visual-style 2 3 ref color:blue
1 the   the   DET  _ Definite=Def|PronType=Art 2 det       _ _
2 boy   boy   NOUN _ Gender=Masc|Number=Sing 0 root      4:nsubj _
3 who   who   PRON _ PronType=Rel 2 ref       _ _
4 lived lived VERB _ Mood=Ind|Tense=Past|VerbForm=Fin 2 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

<table> <!--the book that I read-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 3 obj color:green
1 the   the  DET  _ Definite=Def|PronType=Art 2 det       _ _
2 book  book NOUN _ Gender=Neut|Number=Sing 0 root      _ _
3 that  that PRON _ PronType=Rel 5 obj       _ _
4 I     I    PRON _ Number=Sing|Person=1|PronType=Prs 5 nsubj     _ _
5 read  read VERB _ Mood=Ind|Number=Sing|Person=1|Tense=Pres|VerbForm=Fin 2 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 2 obj color:blue
# visual-style 2 3 ref color:blue
1 the   the DET _ Definite=Def|PronType=Art 2 det       _ _
2 book  book NOUN _ Gender=Neut|Number=Sing 0 root      5:obj _
3 that  that PRON _ PronType=Rel 2 ref       _ _
4 I     I PRON _ Number=Sing|Person=1|PronType=Prs 5 nsubj     _ _
5 read  read VERB _ Mood=Ind|Number=Sing|Person=1|Tense=Pres|VerbForm=Fin 2 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

<table> <!--the book I read-->
<tbody><tr><td width="600">
<div class="conllu-parse">
1 the   the  DET  _ Definite=Def|PronType=Art 2 det       _ _
2 book  book NOUN _ Gender=Neut|Number=Sing 0 root      _ _
3 I     I    PRON _ Number=Sing|Person=1|PronType=Prs 4 nsubj     _ _
4 read  read VERB _ Mood=Ind|Number=Sing|Person=1|Tense=Pres|VerbForm=Fin 2 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 4 2 obj color:blue
1 the   the DET _ Definite=Def|PronType=Art 2 det       _ _
2 book  book NOUN _ Gender=Neut|Number=Sing 0 root      4:obj _
3 I     I PRON _ Number=Sing|Person=1|PronType=Prs 4 nsubj     _ _
4 read  read VERB _ Mood=Ind|Number=Sing|Person=1|Tense=Pres|VerbForm=Fin 2 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

副詞的関係詞 (adverbial relativizers) も同じ扱いを受ける．

<table> <!--the episode where Monica sings-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 3 advmod color:green
1 the the DET DT Definite=Def|PronType=Art 2 det _ _
2 episode episode NOUN NN Number=Sing 0 root _ _
3 where where ADV WRB PronType=Rel 5 advmod _ _
4 Monica Monica PROPN NNP Number=Sing 5 nsubj _ _
5 sings sing NOUN NNS Number=Plur 2 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 3 ref color:blue
# visual-style 5 2 obl color:blue
1 the the DET DT Definite=Def|PronType=Art 2 det _ _
2 episode episode NOUN NN Number=Sing 0 root 5:obl _
3 where where ADV WRB PronType=Rel 2 ref _ _
4 Monica Monica PROPN NNP Number=Sing 5 nsubj _ _
5 sings sing NOUN NNS Number=Plur 2 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

拡張関係は深い (deep) 統語関係を含んでいる．ゆえに，格標示言語では，拡張依存関係は表層の統語論からは要請される形態格にはない動詞依存部と結合する．次のチェコ語の例では関係詞を形成する修飾句_v&nbsp;němž_ “in which” は場所格 (lacative) の形式を必須とする(`Case=Loc`)．それが主節にある場合，_dům_ “house” の指示対象も場所格となる: _v&nbsp;domě_ “in house”．ただし，この例には主格 (nominative) があり (`Case=Nom`)，チェコ語の形態統語論的規則に照らすと，主格依存部に対して適用される拡張依存関係`obl`が生起することは予期されない．
<!--The enhanced relations include deep syntactic relations. Therefore, in case marking languages the enhanced dependencies may link verb dependents that are not in the expected morphological case, required by surface syntax. In the following Czech example, the relative modifier phrase _v&nbsp;němž_ “in which” is obligatorily in the locative case form (`Case=Loc`). If it were a main clause, the referent _dům_ “house” would have to be in locative too: _v&nbsp;domě_ “in house”. However, here it is in the nominative (`Case=Nom`), and the enhanced dependency `obl` going to a nominative dependent is something we would not expect to see, given the morpho-syntactic rules of the language.-->

<table> <!--dům, v němž žijeme = the house we live in (lit. house, in that we-live)-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 4 obl color:green
1 dům house NOUN _ Animacy=Inan|Case=Nom|Gender=Masc|Number=Sing 0 root       _ _
2 , , PUNCT _ _ 5 punct      _ _
3 v in ADP _ _ 4 case       _ _
4 němž that PRON _ Case=Loc|Gender=Masc|Number=Sing|PronType=Rel 5 obl     _ _
5 žijeme live VERB _ Aspect=Imp|Mood=Ind|Number=Plur|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 1 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 1 obl color:blue
# visual-style 1 4 ref color:blue
1 dům house NOUN _ Animacy=Inan|Case=Nom|Gender=Masc|Number=Sing  0 root 5:obl _
2 , , PUNCT _ _ 5 punct      _ _
3 v in ADP _ _ 4 case       _ _
4 němž that PRON _ Case=Loc|Gender=Masc|Number=Sing|PronType=Rel 1 ref     _ _
5 žijeme live VERB _ Aspect=Imp|Mood=Ind|Number=Plur|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 1 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

The relative element does not always depend directly on the predicate of the relative clause.
It may be embedded deeper as in the following example.

<table> <!--muž, v jehož domě žijeme = the man whose house we live in (lit. man, in whose house we-live)-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 4 det color:green
1 muž man NOUN _ Animacy=Anim|Case=Nom|Gender=Masc|Number=Sing 0 root       _ _
2 , , PUNCT _ _ 6 punct      _ _
3 v in ADP _ _ 5 case       _ _
4 jehož whose DET _ Gender[psor]=Masc|Number[psor]=Plur|Poss=Yes|PronType=Rel 5 det     _ _
5 domě house NOUN _ Animacy=Inan|Case=Loc|Gender=Masc|Number=Sing 6 obl _ _
6 žijeme live VERB _ Aspect=Imp|Mood=Ind|Number=Plur|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 1 acl:relcl _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 1 nmod color:blue
# visual-style 1 4 ref color:blue
1 muž man NOUN _ Animacy=Anim|Case=Nom|Gender=Masc|Number=Sing 0 root 5:nmod _
2 , , PUNCT _ _ 6 punct      _ _
3 v in ADP _ _ 5 case       _ _
4 jehož whose DET _ Gender[psor]=Masc|Number[psor]=Plur|Poss=Yes|PronType=Rel 1 ref     _ _
5 domě house NOUN _ Animacy=Inan|Case=Loc|Gender=Masc|Number=Sing 6 obl _ _
6 žijeme live VERB _ Aspect=Imp|Mood=Ind|Number=Plur|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 1 acl:relcl _ _
</div>
</td></tr></tbody>
</table>

関係詞が叙述名詞を持つとき，その関係代名詞は節内の主辞 (head) 位置を占めることがある．そのようなケースでは，親 (parent) と同一指示対象に新たな関係が導入されることない (両者は同一ノードにあるので)．先行詞と関係節の`nsubj`のは，関係`nsubj`のみが追加される (そして，関係代名詞と主語間の対応する関係`nsubj`を取り除く)．`acl:relcl`は基本依存関係と同様のままにしておく．

<!-- https://github.com/UniversalDependencies/docs/issues/531 -->
<table> <!--He became chairman, which he still is-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 6 nsubj color:green
1 He       he       PRON  _ Case=Nom|Gender=Masc|Number=Sing|Person=3|PronType=Prs 2 nsubj _ _
2 became   become   VERB  _ Mood=Ind|Tense=Past|VerbForm=Fin 0 root _ _
3 chairman chairman NOUN  _ Number=Sing 2 xcomp _ SpaceAfter=No
4 ,        ,        PUNCT _ _ 5 punct _ _
5 which    which    PRON  _ PronType=Rel 3 acl:relcl _ _
6 he       he       PRON  _ Case=Nom|Gender=Masc|Number=Sing|Person=3|PronType=Prs 5 nsubj _ _
7 still    still    ADV   _ _ 5 advmod _ _
8 is       be       AUX   _ Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin 5 cop _ SpaceAfter=No
9 .        .        PUNCT _ _ 2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 3 6 nsubj color:blue
# visual-style 3 5 ref color:blue
1 He       he       PRON  _ Case=Nom|Gender=Masc|Number=Sing|Person=3|PronType=Prs 2 nsubj _ _
2 became   become   VERB  _ Mood=Ind|Tense=Past|VerbForm=Fin 0 root _ _
3 chairman chairman NOUN  _ Number=Sing 2 xcomp _ SpaceAfter=No
4 ,        ,        PUNCT _ _ 5 punct _ _
5 which    which    PRON  _ PronType=Rel 3 acl:relcl 3:ref _
6 he       he       PRON  _ Case=Nom|Gender=Masc|Number=Sing|Person=3|PronType=Prs 3 nsubj _ _
7 still    still    ADV   _ _ 5 advmod _ _
8 is       be       AUX   _ Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin 5 cop _ SpaceAfter=No
9 .        .        PUNCT _ _ 2 punct _ _
</div>
</td></tr></tbody>
</table>


## Case Information

必須項でない依存部 (non-core dependents) の関係に対して前置詞 (もしくは格の情報) を加えることで，その意味役割 (semantic role) の曖昧性が除去できる場合が多いため，修飾部の格情報を用いて依存関係を補完する．補完される関係は`nmod`，`acl`，`obl`および`advcl`である; 理解の助けになるなら，言語によっては必須の関係も補完される: `obj`, `iobj`, `ccomp`．
格の情報は，関係`case`を介して付加される側置詞 (adposition) の見出し語 (lemma) から表示される．節に対しては，対応する情報が依存部`mark`の見出し語によって表示される．
<!--もともとコメントアウトの部分→ DZ: Do we really want to include cc dependents here? How are they related to case? Don't we want to make them augment conj relations instead? -->
格情報は形態素性 [Case](/u/feat/Case.html) の値 (value) によって表示される．側置詞と形態格の両方が存在する言語もあり，それらの組み合わせは拡張関係へ反映されなければならない．

以下の形式規則が適用される (本ページ冒頭の概要からコピーしたもの):

* 側置詞もしAdposition or conjunction that occurs as a `case` or `mark` <!--or `cc` ?--> dependent of the node whose relation to its
  parent is being enhanced. Note that this is the only part where non-ASCII letters are permitted within the enhanced relation label.
  The word should be normalized (lowercased, no typos), i.e., in general we take its lemma. However, if the case/mark dependent is
  a fixed multi-word expression, the lemma of the expression is not necessarily composed of lemmas of the individual member words.
  For instance, the string representing the English expression “As Opposed To” is `as_opposed_to`. That is, the casing is normalized
  from “As” to “as” etc., but “opposed” is not replaced by its lemma “oppose” because the expression is fixed. We use the underscore
  character (“_”) to connect member words.
  * Multiple `case` or `mark` nodes may occur even if it is not a fixed expression. For example, a type of adverbial clause
    in Dutch uses two markers _om_ and _te_, the first one roughly corresponding to English “so that”, the second one being
    an infinitive marker. The incoming dependency of the subordinate clause will then be labeled `advcl:om_te`.
* Morphological case of the node whose relation to its parent is being enhanced. Value corresponds to the value of
  the Case feature but it is lowercased (e.g., `gen` instead of `Gen`). Unlike in morphological features, multivalues with comma
  (`Case=Acc,Dat`) are not allowed. Case information in enhanced relations must be fully disambiguated.

<table> <!--the house on the hill-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 2 5 nmod color:green
1 the   _ _ _ _ 2 det  _ _
2 house _ _ _ _ 0 root _ _
3 on    _ _ _ _ 5 case _ _
4 the   _ _ _ _ 5 det  _ _
5 hill  _ _ _ _ 2 nmod _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 5 nmod:on color:blue
1 the   _ _ _ _ 2 det     _ _
2 house _ _ _ _ 0 root    _ _
3 on    _ _ _ _ 5 case    _ _
4 the   _ _ _ _ 5 det     _ _
5 hill  _ _ _ _ 2 nmod:on _ _
</div>
</td></tr></tbody>
</table>

<table> <!--He went to a diner after leaving work .-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 2 5 obl color:green
# visual-style 2 7 advcl color:green
1  He      _ _ _ _ 2 nsubj _ _
2  went    _ _ _ _ 0 root  _ _
3  to      _ _ _ _ 5 case  _ _
4  the     _ _ _ _ 5 det   _ _
5  dinner  _ _ _ _ 2 obl   _ _
6  after   _ _ _ _ 7 mark  _ _
7  leaving _ _ _ _ 2 advcl _ _
8  work    _ _ _ _ 7 obj   _ _
9  .       _ _ _ _ 2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 5 obl:to color:blue
# visual-style 2 7 advcl:after color:blue
1  He      _ _ _ _ 2 nsubj       _ _
2  went    _ _ _ _ 0 root        _ _
3  to      _ _ _ _ 5 case        _ _
4  the     _ _ _ _ 5 det         _ _
5  dinner  _ _ _ _ 2 obl:to      _ _
6  after   _ _ _ _ 7 mark        _ _
7  leaving _ _ _ _ 2 advcl:after _ _
8  work    _ _ _ _ 7 obj         _ _
9  .       _ _ _ _ 2 punct       _ _
</div>
</td></tr></tbody>
</table>

<table> <!--die Zerstörung der Stadt \n the destruction the.GEN city.GEN-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 2 4 nmod color:green
# text = the destruction of the city
1  die        the         DET  _ Case=Gen 2 det  _ _
2  Zerstörung destruction NOUN _ Case=Nom 0 root _ _
3  der        the         DET  _ Case=Gen 4 det  _ _
4  Stadt      city        NOUN _ Case=Gen 2 nmod _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 4 nmod:gen color:blue
# text = the destruction of the city
1  die        the         DET  _ Case=Gen 2 det      _ _
2  Zerstörung destruction NOUN _ Case=Nom 0 root     _ _
3  der        the         DET  _ Case=Gen 4 det      _ _
4  Stadt      city        NOUN _ Case=Gen 2 nmod:gen _ _
</div>
</td></tr></tbody>
</table>

<table> <!--Er sitzt auf dem Boden. \n He sits on the floor.-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 2 5 obl color:green
# text = He sits on the floor
1  Er     he     PRON  _ Case=Nom 2 nsubj _ _
2  sitzt  sits   NOUN  _ _        0 root  _ _
3  auf    on     ADP   _ _        5 case  _ _
4  dem    the    DET   _ Case=Dat 5 det   _ _
5  Boden  floor  NOUN  _ Case=Dat 2 obl   _ SpaceAfter=No
6  .      .      PUNCT _ _        2 punct _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 5 obl:auf:dat color:blue
# text = He sits on the floor
1  Er     he     PRON  _ Case=Nom 2 nsubj       _ _
2  sitzt  sits   NOUN  _ _        0 root        _ _
3  auf    on     ADP   _ _        5 case        _ _
4  dem    the    DET   _ Case=Dat 5 det         _ _
5  Boden  floor  NOUN  _ Case=Dat 2 obl:auf:dat _ SpaceAfter=No
6  .      .      PUNCT _ _        2 punct       _ _
</div>
</td></tr></tbody>
</table>

<table> <!--Er setzt sich auf den Boden. \n He sits down on the floor.-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 2 6 obl color:green
# text = He sits down on the floor
1  Er     he      PRON  _ Case=Nom 2 nsubj   _ _
2  setzt  sets    NOUN  _ _        0 root    _ _
3  sich   himself PRON  _ Case=Acc 2 expl:pv _ _
4  auf    on      ADP   _ _        6 case    _ _
5  den    the     DET   _ Case=Acc 6 det     _ _
6  Boden  floor   NOUN  _ Case=Acc 2 obl     _ SpaceAfter=No
7  .      .       PUNCT _ _        2 punct   _ _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 2 6 obl:auf:acc color:blue
# text = He sits down on the floor
1  Er     he      PRON  _ Case=Nom 2 nsubj       _ _
2  setzt  sets    NOUN  _ _        0 root        _ _
3  sich   himself PRON  _ Case=Acc 2 expl:pv     _ _
4  auf    on      ADP   _ _        6 case        _ _
5  den    the     DET   _ Case=Acc 6 det         _ _
6  Boden  floor   NOUN  _ Case=Acc 2 obl:auf:acc _ SpaceAfter=No
7  .      .       PUNCT _ _        2 punct       _ _
</div>
</td></tr></tbody>
</table>

<table> <!--В течение долгого времени изучал язык майя. \n For a long time he studied the Maya language.-->
<tbody><tr><td width="600">
<div class="conllu-parse">
# visual-style 5 4 obl:tmod color:green
# visual-style 6 7 nmod color:green
# text = For a long time he studied the Maya language.
1  В        In        ADP    _  _         4  case      _  _
2  течение  duration  NOUN   _  Case=Loc  1  fixed     _  _
3  долгого  long      ADJ    _  Case=Gen  4  amod      _  _
4  времени  time      NOUN   _  Case=Gen  5  obl:tmod  _  _
5  изучал   studied   VERB   _  _         0  root      _  _
6  язык     language  NOUN   _  Case=Acc  5  obj       _  _
7  майя     Maya      PROPN  _  Case=Gen  6  nmod      _  SpaceAfter=No
8  .        .         PUNCT  _  _         5  punct     _  _
</div>
</td><td width="600">
<div class="conllu-parse">
# visual-style 5 4 obl:tmod:в_течение:gen color:blue
# visual-style 6 7 nmod:gen color:blue
# text = For a long time he studied the Maya language.
1  В        In        ADP    _  _         4  case                    _  _
2  течение  duration  NOUN   _  Case=Loc  1  fixed                   _  _
3  долгого  long      ADJ    _  Case=Gen  4  amod                    _  _
4  времени  time      NOUN   _  Case=Gen  5  obl:tmod:в_течение:gen  _  _
5  изучал   studied   VERB   _  _         0  root                    _  _
6  язык     language  NOUN   _  Case=Acc  5  obj                     _  _
7  майя     Maya      PROPN  _  Case=Gen  6  nmod:gen                _  SpaceAfter=No
8  .        .         PUNCT  _  _         5  punct                   _  _
</div>
</td></tr></tbody>
</table>

## Additional enhancements

数量限定詞 (quantificational determiners) のように振る舞う軽名詞 (light nouns) の降格 (demoting) といったポストプロセス (例えば，[Schuster and Manning (2016)](http://www.lrec-conf.org/proceedings/lrec2016/pdf/779_Paper.pdf) にあるような) は，下流のアプリケーションにおける依存グラフの有用性を高める．しかし，このような追加は大いに言語特有のものであるため，表示に関して言語普遍的なガイドラインを設けることはしない．そして，上記の追加を超えるものは標準的なUDの要素とは言えず，公式にリリースされるツリーバンクには搭載されない．