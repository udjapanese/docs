---
layout: feature
title: 'PronType'
shortdef: 'pronominal type'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Art">Art</a></td>
  <td><a href="#Dem">Dem</a></td>
  <td><a href="#Emp">Emp</a></td>
  <td><a href="#Exc">Exc</a></td>
  <td><a href="#Ind">Ind</a></td>
  <td><a href="#Int">Int</a></td>
  <td><a href="#Neg">Neg</a></td>
  <td><a href="#Prs">Prs</a></td>
  <td><a href="#Rcp">Rcp</a></td>
  <td><a href="#Rel">Rel</a></td>
  <td><a href="#Tot">Tot</a></td>
</tr>
</table>

この素性は典型的に [代名詞 (pronouns)](u-pos/PRON),
代名詞的形容詞 (pronominal adjectives) ([限定詞 (determiners)](u-pos/DET)), 代名詞的 [数詞 (numerals)](u-pos/NUM) (数量詞 (quantifiers)) および代名詞的 [副詞 (adverbs)](u-pos/ADV) に対して適用される.

### <a name="Prs">`Prs`</a>: 人称代名詞，所有代名詞，限定詞

通常の人称代名詞が所有代名詞と区別されることについては[Poss]()を参照されたい．`Prs`は再帰代名詞/所有代名詞 (reflexive
personal/possessive pronouns) を含むことに注意されたい (e.g. [cs] _se / svůj;_素性[Reflex]()を参照).

#### 例

* [en] _I, you, he, she, it, we, they, my, your, his, her, its, our,
  their, mine, yours, hers, ours, theirs_
* [cs] _já, ty, on, ona, ono, my, vy, oni, ony, se, můj, tvůj, jeho, její, náš,
  váš, jejich, svůj_

### <a name="Rcp">`Rcp`</a>: 相互代名詞 (reciprocal pronoun)

この値は特に相互的である代名詞に対して用いられる．相互的意味が再帰代名詞によって表される場合，当該の語は依然として再帰代名詞としてラベル付けされる (`PronType=Prs|Reflex=Yes`). コンテクスト上で相互的な意味が現れる場合は，相互代名詞としては標示されない．

相互的とは，複数を表す主語がある場合に各成員が述語 (predicate) の指す行為を行うことを意味する．そのような意味を表すため，相互代名詞が目的語の位置において用いられる．

#### 例

* [de] _einander_ “each other”
* [da] _hinanden_ “each other”

### <a name="Art">`Art`</a>: 冠詞 (article)

冠詞は限定詞の特殊な事例であり，[定性 (definiteness)](Definite)の素性を持つ (他言語では，この素性は名詞に対して直接標示される.

#### 例

* [en] _a, an, the_ 
* [de] _ein, eine, der, die, das_ 
* [es] _un, una, el, la_

### <a name="Int">`Int`</a>: 疑問 (interrogative) 代名詞，限定詞，数詞，副詞

所有疑問代名詞 (_whose_) は素性[Poss]()から区別される場合がある．

#### 例:

* [cs/en] _kdo / who, co / what, který / which, čí / whose, kolik /
  how many, how much, kolikátý / how-maniest_ (基数の数量詞),
  _kolikrát / how many times, kde / where, kam / where to, kdy / when,
  jak / how, proč / why_

### <a name="Rel">`Rel`</a>: 関係 (relative) 代名詞，限定詞，数詞，副詞

多くの言語において，このクラスは疑問詞 (interrogatives) と大いに重複する．とはいえ，関係詞のみに属する代名詞も存在し，言語 (ブルガリア語，ヒンディー語) によっては2つのクラスが独立している場合もある．

#### 例: 

* [cs] _jenž, což_ “which”, “that” (疑問代名詞ではなく関係代名詞); _jehož_ “whose” (所有関係代名詞）

### <a name="Exc">`Exc`</a>: 感嘆の限定詞 (exclamative determiner)

感嘆の限定詞<!--Exclamative pro-adjectives (determiners)-->は，それが修飾している名詞に対する話者の驚きを表す (e.g. _what_ in “What a surprise!”) 多くの言語で感嘆の限定詞は疑問限定詞 (interrogative determiners) から選ばれるので，これらを区別しないタグセットも存在する．

#### Examples: 

* [it] _che_
* [cs] _jaký_ as in “Jaké překvapení!”
* [en] _what_ as in “What a surprise!”

### <a name="Dem">`Dem`</a>: demonstrative pronoun, determiner, numeral or adverb

These are often parallel to interrogatives. Some tagsets might also
distinguish a separate feature of distance (_here / there_; [es] _aquí
/ ahí / allí_).

#### 例

* [cs/en] _tento / this, tamten / that, takový / such, týž / same,
  tolik / so much, tolikátý / so-maniest_ (基数), _tolikrát
  / so many times, tady / here, tam / there, teď / now, tehdy / then,
  tak / so_

### <a name="Emp">`Emp`</a>: 強調の限定詞 (emphatic determiner)

強調の限定詞<!--Emphatic pro-adjectives (determiners)-->は，それが依存している名詞を強調する．これらは再帰代名詞や指示代名詞/限定詞に類似している．

#### 例

* [ro] _însuși_
* [cs] _sám_
* [en] _himself_ “He himself did it.” 内の

### <a name="Tot">`Tot`</a>: 集合 (collective) 代名詞，限定詞，副詞

#### 例

* [cs/en] _každý / every, everybody, everyone, each, všechno /
  everything, all, všude / everywhere, vždy / always_

### <a name="Neg">`Neg`</a>: 否定 (neganitve) 代名詞，限定詞，副詞

否定代名詞は否定[不変化詞 (particles)](u-pos/PART)や極性 (polarity) に関して屈折する語 (動詞，形容詞など) とは区別される. これらの語には`PronType=Neg`を持ちいず，かわりに`Polarity=Neg`を用いる．詳細については[Polarity]()を参照されたい．

#### 例:

* [cs/en] _nikdo / nobody, nic / nothing, nijaký / no, ničí / no
  one's_ (否定の所有限定詞 (possessive negative determiner)), _žádný / no, none, nikde /
  nowhere, nikdy / never, nijak / no way_ (lit. “no-how”)

### <a name="Ind">`Ind`</a>: 不定の代名詞，限定詞，数詞，副詞

タグセットによっては，このカテゴリに“some”と“any”などの区別によって下位分類を設けることがある．そのような区別は普遍的素性 (universal features) に含まれないが，特定の言語に拡張したものには追加されるかもしれない．

#### 例

* [cs/en] _někdo / somebody, něco / something, některý / some, něčí /
  someone's_ (不定の所有代名詞), _několik / a few,
  several_ (不定の数詞/数量詞), _několikátý / “a fewth”,
  “severalth”_ (不定の基数詞), _několikrát / a few
  times, several times, někde / somewhere, někdy / sometimes, nějak /
  somehow_
* [cs/en] _kdokoli / anybody, cokoli / anything, kterýkoli / any,
  číkoli / anyone's_ (不定の所有代名詞), _kdekoli /
  anywhere, kdykoli / any time, jakkoli / anyhow_
* [cs/en] _málokdo / few people, leckdo / quite a few people, kdosi /
  somebody…_
