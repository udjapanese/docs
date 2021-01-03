---
layout: feature
title: 'NumType'
shortdef: 'numeral type'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Card">Card</a></td>
  <td><a href="#Dist">Dist</a></td>
  <td><a href="#Frac">Frac</a></td>
  <td><a href="#Mult">Mult</a></td>
  <td><a href="#Ord">Ord</a></td>
  <td><a href="#Range">Range</a></td>
  <td><a href="#Sets">Sets</a></td>
</tr>
</table>

いくつかの言語 (特にスラヴ語で) は，[数 (numerals)](u-pos/NUM) の複雑な体系を備える．例えば，チェコ語の学校文法では"numeral"という数についての主要な品詞があり，これは数えることに関してほとんど全てのものを包含し，いくつものサブタイプが存在する．また，これには，数 (_kolik / how many, tolik / so many, několik / some, a few_といった語) を指示する疑問詞 (interrogative), 関係詞 (relative), 不定の指示語 (indefinite and demonstrative words) も含まれ，[PronType]()において，これらは空でない値を持つだろう (英語では，これらの語は数量詞 (quantifier) と呼ばれ，[限定詞 (determiners)](u-pos/DET) の下位グループに属する)．

統語論の観点からいえば，形容詞のようにふるまうnumtypeもあれば，副詞のようにふるまうものもある．それぞれ，[u-pos/ADJ]()と[u-pos/ADV]()のようにタグ付けされる．このように，素性`NumType`はさまざまな品詞に適用される:

* [u-pos/NUM](): 基数 (cardinal numerals)
* [u-pos/DET](): 数量詞 (quantifiers)
* [u-pos/ADJ](): 限定形容詞 (definite adjectival; e.g. 序数 (ordinal numerals))
* [u-pos/ADV](): 副詞的な数詞 (e.g. 序数詞，倍数詞)で，限定的なものと代名詞的なものの両方をもつ

### <a name="Card">`Card`</a>: 基数 (ordinal number) か，それに対応する疑問詞 / 関係詞 / 不定詞 / 指示語

いくつかの印欧語では，_thousand_, _million_ や_billion_に相当する語は数詞か名詞どちらに属すかが明瞭でない．

#### 例

* [en] _one, two, three_
* [cs] _jeden, dva, tři_ "one, two, three"; _kolik_ "how many";
  _několik_ "some"; _tolik_ "so many"; _mnoho_ "many"; _málo_ "few"
* [cs] _<b>čtvero, patero, desatero</b>_ (four, five, tenの特定の形式; これらは形態的，統語的，そして文体的にみてもデフォルト形式の_čtyři, pět, deset_とは区別される; チェコ語の文法では，これらは "generic numerals" と呼ばれ, 他のあまり見られないタイプも包含する; 普遍的なタイプの中でこれに最も近いのは`Card`である.)

<!--↓元々コメントアウト部分
Czech:        <feat name="NumType" value="Gen" upos="ADJ">62</feat><!-- dvojí, obojí, dvojím, dvojího, obojím, trojí, dvojími, obého
Czech CAC:    <feat name="NumType" value="Gen" upos="ADJ">33</feat><!-- dvojí, obojí, dvojím, trojí, dvojího, trojím, dvojímu, obojího, obojím
Croatian:     <feat name="NumType" value="Gen" upos="NUM">85</feat><!-- obje, oba, obiju, 50%, deseci, objema, 20%, 30%, 9%, dvoje
Slovenian:    <feat name="NumType" value="Gen" upos="ADJ">4</feat><!-- dvojnega, dvojnim, dvojno, trojnim
SlovSST:      <feat name="NumType" value="Gen" upos="ADJ">3</feat><!-- dvojni, dvojno, trojni
Italian:      <feat name="NumType" value="Gen" upos="NUM">21</feat><!-- 6', 1'13'', 1.00'16'', 1.19'59'', 10'', 11'06'', 13', 19'43'', 2'42'', 20'01''
Greek:        <feat name="NumType" value="Gen" upos="NUM">19</feat><!-- δεκάδες, χιλιάδες, εκατοντάδες, χιλιάδων, διπλάσιο, εκατοντάδων
-->

### <a name="Ord">`Ord`</a>: 序数 (ordinal number) か，それに対応する疑問詞 / 関係詞 / 不定詞 / 指示語

これは，形容詞か (いくつかの言語では) 副詞である．

#### 例

* [en] _first, second, third;_
* [cs] adjectival: _první_ "first"; _druhý_ "second", _třetí_ "third";
  _kolikátý_ lit. _how manieth_ "which rank"; _několikátý_ "some
  rank"; _tolikátý_ "this/that rank"
* [cs] adverbial: _poprvé_ "for the first time"; _podruhé_ "for the
  second time"; _potřetí_ "for the third time"; _pokolikáté_ "for
  which time", _poněkolikáté_ "for x-th time", _potolikáté_

### <a name="Mult">`Mult`</a>: multiplicative numeral or corresponding interrogative / relative / indefinite / demonstrative word

これは，形容詞か副詞のサブタイプである．

#### 例

* [sl] _dvojen_ "double, twofold"; _trojen_ "triple, threefold"; _četveren_ "fourfold"
* [cs] _dvojí_ "twofold"; _trojí_ "threefold" (multiplicative adjectives)
* [cs] _jednou_ "once"; _dvakrát_ "twice"; _třikrát_ "three times";
  _kolikrát_ "how many times", _několikrát_ "several times";
  _tolikrát_ "so many times" (multiplicative adverbs)

### <a name="Frac">`Frac`</a>: 分数 (fraction)

基数のサブタイプに属し，コーパスによっては設定されることがある．これは分数もしくは単に分母を表し，さまざまな言語で形態的，統語的に名詞もしくは序数詞としてふるまう．

#### 例

* [en] _three-quarters_
* [cs] _půl / polovina_ "half"; _třetina_ "one third"; _čtvrt /
  čtvrtina_ "quarter"

### <a name="Sets">`Sets`</a>: 集合の数・集合数詞 (number of sets of things; collective numeral)

これは数詞の独立したクラスであり，事物の集合を数えるために用いられる数詞か，絶対複数 (pluralia tantum) を示す名詞である．研究者によってはこのタイプを集合数詞 (collective numeral) と呼ぶことがある．

#### 例

* [cs] _<b>dvoje</b> / <b>troje</b> boty_ "<b>two</b> / <b>three</b>
  [pairs of] shoes"; 通常の基数詞とは区別される: _dvě / tři
  boty_ "two / three shoes"

### <a name="Dist">`Dist`</a>: 配分される数 (distributive numeral)

同じ量が特定のターゲット内の各成員に配分されることを表す.

#### 例

* [hu] _három-három in gyermekenként <b>három-három</b> ezer
  forinttal_ "three thousand forint per child"

### <a name="Range">`Range`</a>: 数値の範囲

基数のサブタイプと考えられ，コーパスによっては設定されることがある．

#### 例

* [en] _two-five_ "two to five" (トークン化の際，全体を1つのトークンとして扱う.)
