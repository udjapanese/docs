---
layout: base
title:  'Typos and Other Errors in Underlying Text'
permalink: u/overview/typos.html
udver: '2'
---

<!--
(See also issues [#330](https://github.com/UniversalDependencies/docs/issues/330), [#513](https://github.com/UniversalDependencies/docs/issues/513), and [#544](https://github.com/UniversalDependencies/docs/issues/544).)
-->

# Typos and Other Errors in Underlying Text

時として，UDツリーバンクに収納しているテキストが当該言語の標準的なスペリングや他の文法規則に従わない場合があり，大抵はエラーをそのままにしておくことが望ましい．データからモデル学習を行うタガーとパーサーは，ノイズを含む入力も扱えたほうが良いからである．同時に，エラーをエラーであると記し，正しい綴りを示しておくことも望ましい．そうすることで，アプリケーションは必要に応じて，誤りを含んだ文を隠し，正しい文を表示することが可能となる．

本ページの推奨法は偶発的なエラーに対して作られている．技術的には，エラーを多分に含む学習者コーパスに対しても適用可能かもしれない; しかし，学習者コーパスには工夫が必要で，次の疑問に答える必要が生じる: 書き手が当該言語をより理解していたのなら何を書こうとしたか，を予測したいのか? それとも，理解度が深い言語と当該言語の混合だと思われる"心内の文法"へ近似させたいのか? 

タイポ (typo) の扱いに類似するメカニズムは歴史コーパスにおける歴史的な綴りにも用いることが可能かもしれない; 詳細は [以下の](#historical-spelling) セクションを参照されたい．

## Misspelled Word

最も容易に起きるエラーは語の単純なタイポで，特に語を成さないようなものについてである．(別の語，例えば英語で_two_の代わりに_too_と表記しているとき，書き手が本当に他のことを言いたかったのかを判断する必要があるが，明らかでない場合もある．)

文頭におけるFORMのフィールドと`text`の属性では，常に原文に生起した形式を含んでいる必要がある．一方で，LEMMAのフィールドには標準の綴りを用いる; テキスト上で_cats_の代わりに_kats_と表記していれば，語彙素 (lemma) は_cat_となり，_kat_ではない．そして，タイポを記すために [Typo]()`=Yes` を形態素性に含めるべきである．これは重要となる: [Typo]()`=Yes` は正しい語形と 語彙素 + 品詞 (part-of-speech) タグ + 形態素性 の唯一の対応づけが存在することを保証する．`Typo=Yes` がなければ，コーパス上において，英語の名詞_cat_の正しい複数形が_kats_であると考えられてしまう．(全ての綴り間違いは同一の素性`Typo=Yes`によって表示されるため，誤った語形における対応付けは唯一のものとならない．)

当該位置での正しい綴りが何であるかは語彙素と形態素性からは不明である．正しい語形をリストに収めたいが，これは形態素性でないため，代わりにMISCのカラムで表示させる:`CorrectForm=cats`.
例は以下の通り:

<pre>
# text = I have two kats.
1	I	I	PRON	_	Case=Nom|Number=Sing|Person=1|PronType=Prs	2	nsubj	_	_
2	have	have	VERB	_	Mood=Ind|Number=Sing|Person=1|Tense=Pres|VerbForm=Fin	0	root	_	_
3	two	two	NUM	_	NumType=Card	4	nummod	_	_
4	kats	cat	NOUN	_	Number=Plur|Typo=Yes	2	obj	_	CorrectForm=cats|SpaceAfter=No
5	.	.	PUNCT	_	_	2	punct	_	_

</pre>

## Wrongly Split Word

語に誤ったスペースが挿入される場合，間違ったトークンが複数生起することになる．UDのバージョン2以降でスペースつきの語を認めるとはいえ，複数のトークンをスペース付きの単一トークンへ結合することはしない．この選択肢は，当該の言語で境界的だが (ベトナム語を除いて) _予測可能である_非常に限られた状況下で適用され，恣意的なエラーには適用できない．その代わり，UDでは関係 [goeswith]() を語の部分を結合するものと定義しておき，先頭部分が常に主辞となり，他の部分は`goeswith`を介して主辞へ付加するように扱う．

主辞は品詞タグと語全体の形態タグを持つ必要がある．“通常の”タイポが存在しない限り，すなわち語の部分を結合したものが正しい形式をもたらさないのならば，MISCカラムに`Typo`素性と`Correction`素性を加える必要はない．例:

<pre>
# text = This spel ling is wrong.
1	This	this	DET	_	Number=Sing|PronType=Dem	2	det	_	_
2	spel	spelling	NOUN	_	Number=Sing	5	nsubj	_	_
3	ling	_	X	_	_	2	goeswith	_	_
4	is	be	AUX	_	Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin	5	cop	_	_
5	wrong	wrong	ADJ	_	_	0	root	_	SpaceAfter=No
6	.	.	PUNCT	_	_	5	punct	_	_

</pre>

## Wrongly Merged Words

UDには，2語がスペースで分割されていないことを捉えるためのメカニズムを2つ備えている: MISCカラムの属性`SpaceAfter=No`および複数語 (multi-word) のトークン．前者は通常，語と句読点に対して用いられる．後者は実在する2語が結合しているが標準の文法規則に従っている場合，すなわち恣意的なエラーでないものに用いられる．また，複数語のトークンに対するタグ付けは<!--non-concatenative fusions-->を許すため，技術的に複雑となる．編集が十分でないテキストのタグ付けについては，属性`SpaceAfter`が適しているように思われる．

<!--As with `Typo=Yes` and `CorrectForm=X`, it is desirable to indicate that the space is missing by error. Therefore, `SpaceAfter=No` should be accompanied by `CorrectSpaceAfter=Yes`.-->

同様のメカニズムは (`CorrectSpaceAfter=No`を用いて) 句読点周辺の余分なスペースを表示するためにも用いられる．句読点と語の結合は語を形成しないため，句読点は`goeswith`を介して別の接点へ結合させるべきでない．例:

<pre>
# text = This spellingis wrong .
1	This	this	DET	_	Number=Sing|PronType=Dem	2	det	_	_
2	spelling	spelling	NOUN	_	Number=Sing	4	nsubj	_	SpaceAfter=No|CorrectSpaceAfter=Yes
3	is	be	AUX	_	Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin	4	cop	_	_
4	wrong	wrong	ADJ	_	_	0	root	_	CorrectSpaceAfter=No
5	.	.	PUNCT	_	_	4	punct	_	_

</pre>

## A Combination of the Above

一文に複数タイプのエラーを含む，より複雑な例:

<pre>
# text = This spel lingi$ wrong .
1	This	this	DET	_	Number=Sing|PronType=Dem	2	det	_	_
2	spel	spelling	NOUN	_	Number=Sing	5	nsubj	_	_
3	ling	_	X	_	_	2	goeswith	_	SpaceAfter=No|CorrectSpaceAfter=Yes
4	i$	be	AUX	_	Mood=Ind|Number=Sing|Person=3|Tense=Pres|Typo=Yes|VerbForm=Fin	5	cop	_	CorrectForm=is
5	wrong	wrong	ADJ	_	_	0	root	_	CorrectSpaceAfter=No
6	.	.	PUNCT	_	_	5	punct	_	_

</pre>

## Missing Word

1つ以上の語がテキストから欠けている場合，それらは [省略 (ellipsis)](specific-syntax.html#ellipsis) として扱われる．すなわち，不完全な部分木 (subtree) から構成素を一つ選択し，それを主辞へと昇格 (promote) させると共に，他の要素を依存部として主辞へ付加させるのである．省略された動詞の項が昇格するならば，他の項や付加詞は関係 [orphan]() を介して昇格要素へ付加させる．<!--otherwise the relation type is used that would go out of the head if the missing material were present-->

省略に近いタグを付与するよう推奨するとはいえ，時には語が省略によってではなく本当にエラーで欠けていることがあるため注意を要する．例えば，文の分割に誤りがあると，文末を意図しないピリオドの直後で文が途中で終わってしまう．

## Extra Word

あるべきでない誤った語をテキストが含むときは，話し言葉の非流暢性 (speech disfluences) と似たような扱いを受ける．すなわち，その語は [reparandum]() を介して後続する構成素へ付加される．書き言葉で比較的多い事例には，1つの語が連続して2回タイプされることがある．

## Wrong Morphology or Syntax

例えば，文法上は与格 (dative) を要求するが実際の形式が主格 (nominative) であったり，複数形の代わりに単数形が生起する_(the cars is produced in Detroit)_ことがある．そのようなエラーは単なるタイポとも扱えるが，直感的には同じカテゴリではない (とはいえ，_the cars iss produced…_のようにタイポと共起することもある)．常に正しい形式が何かが分かるわけではないが，_cars_を_car_に，もしくは_is_を_are_に修正することもできるだろう (しかし，同時には不可能)．同様に，実際の語形が主格で誤りが明白かもしれないが，コンテクスト次第では他の格が適切な場合もある．

特定の言語では方言もしくは変種の可能性があるため，実際にエラーとして分類されるべきかが時には判然としないこともある．(特定のタイポには実際に適用されてしまう: _color_はアメリカ英語で正しい綴りだが，イギリス英語では_colour_となる．)

提案: 語を元のテキストのままにすること．正しいと考えられる形式ではなく，実際の形式に対応する形態素性を加えること: 英語の_is_は`Number=Sing`が付与され，_cars_ には `Number=Plur`が付与される．(決定が難しい場合もあるため注意を要する．例えば，チェコ語の_auto_“car”は主格単数と対格単数が同形である．もしもコンテクストが与格_(autu)_を要求するならば，実際の形式が誤っていることは分かるが，それが`Case=Nom`か`Case=Acc`のどちらなのかは判明しない．このときは`Case=Acc,Nom`とタグ付けするしかないだろう．与格だけでなく場所格 (locative) も意味し得る_autu_が正しい形式として存在する場合は，コンテクストによって区別可能なので，`Case=Dat,Loc`ではなく`Case=Dat`とタグ付けする．)

<!--MISCのカラムでは，単純なタイポで行ったのと同じく正しい形式を表示させる: `CorrectForm=autu`．また，MISCカラムには，FEATカラムの素性に接頭辞“Correct”を付与したもの (e.g. `CorrectCase=Dat`) を加える． We also add in the MISC column those features from the FEAT column that would differ for the correct form, and prefix them with “Correct”, e.g. `CorrectCase=Dat`.-->ただし，FORMカラムにおける語形 (word form) はFEATカラムにおける形態素性の値を反映させているので，FEATカラムには`Typo=Yes`を加えない．統語タグ付けに関しては，従うのが容易で単純な規則は存在しないように思われる．各々の文は，実際の表層形と意図されたと仮定できる読みとの間の妥協点を見出すことで，個別に決定するしかないだろう．例えば，与格名詞を要求するチェコ語の前置詞_k_“to”はどうだろうか．テキストで (正しい)_k autu_ではなく (誤って)_k auto_が含まれる場合，主格_auto_が前置詞と共起できない (非文法的) ことに関係なく，唯一可能なのは`case(auto, k)`としてタグ付けすることである．

<pre>
# text = The cars is produced in Detroit.
1	The	the	DET	_	Definite=Def|PronType=Art	2	det	_	_
2	cars	car	NOUN	_	Number=Plur	4	nsubj:pass	_	_
3	is	be	AUX	_	Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin	4	aux:pass	_	CorrectForm=are|CorrectNumber=Plur
4	produced	produce	VERB	_	Tense=Past|VerbForm=Part	0	root	_	_
5	in	in	ADP	_	_	6	case	_	_
6	Detroit	Detroit	PROPN	_	Number=Sing	4	obl	_	SpaceAfter=No
7	.	.	PUNCT	_	_	4	punct	_	_

</pre>

## Historical Spelling

同様のメカニズムは古代のテキストにおける歴史的綴りを表示する場合にも適用が可能である．例えば，ドイツ語の_sein_ "to be" は_seyn_と綴られてきたが，これは当時のテキストで正しい形式だったため，タイポではない．旧来の形式であることを表示するためにはFEATSのカラムで [Style]()`=Arch` を用いる場合があり，その時MISCカラムには `ModernForm=sein` と付け加えることが可能である (タイポを表示する`CorrectForm=sein`との類推で)．