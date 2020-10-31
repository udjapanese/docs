---
layout: postag
title: 'DET'
shortdef: 'determiner'
udver: '2'
---

### Definition

限定詞 (determiners) は [nouns](NOUN) や名詞句を修飾するような語を指し，コンテクスト上で名詞句の指示対象を表す．つまり，限定詞が示しているのは，当該の名詞が表す対象が定か不定か，近くにあるのか遠くにあるのか，特定の人物や物なのか，もしくは特定の数や数量なのか，といったことである．

この定義のもと，限定詞は，_冠詞 (articles)_ と_代名詞的形容詞 (pronominal adjectives)_ と呼ばれる，ふだん英語で限定詞としてみなされるものよりも広いものを含む．特に，名詞句を修飾できるのは一つの限定詞に限られる，といった条件は存在しないが，言語によってはこのような制約に対する強い傾向を示す．(例えば，英語の名詞句は普段一つだけの修飾語`DET`のみを許すが，時には_追加の限定詞 (addeterminers)_ と呼ばれるものが通常の限定詞の外に生起する場合がある．追加の限定詞には，[en] _all_ in _<b>all</b> the children survived_ といったものがあり，_all_と_the_は両方ともPOSタグにおいて`DET`と表記される．)

`DET`タグは (代名詞的な) _数量詞 (quantifiers)_ ( _many, few, several_のような語) を含み，限定詞とみなす言語もあれば，数詞としてみなす言語もあることに注意したい．しかし，狭義の_基数詞 (cardinal numeral; e.g. one, five, hundred)_ は，これを数量詞に含める人もいるが，`DET`は与えられない．基数は独自のタグ [NUM]() を持つからである．

さらに，限定詞の概念は伝統文法では不明な言語もある (e.g. チェコ語); これらの言語では，英語の限定詞に相当する語が [pronouns](PRON) および/もしくは [numerals](NUM) として分類される．同じ対象をどの言語でも同じようにタグ付けするには，限定詞の上記の定義を満たす語は，チェコ語のような言語でも`DET`としてタグ付けするのが望ましい．

代名詞と限定詞の境目が常に明瞭だとは限らない．UD v1とは異なり，これらの語の区別はコンテクストのみに基づくわけではなく，_典型的な_統語分布 (適用可能なら形態論的なものも) に基づき，辞書によって`PRON`もしくは`DET`の分類が予め決定されることもある．言語特有のドキュメンテーションでは (閉じたクラスである) 全ての限定詞をリスト化し，可能ならば曖昧な点を挙げるべきである．

限定詞の決定に関するヒントとしては，[general principles on pronominal words](../overview/morphology.html#pronominal-words) も参照されたい．
詳しい情報:

* 冠詞 _(the, a, an)_ は常に`DET`としてタグ付けされる; それらの [PronType](/u/feat/PronType.html) は`Art`である.
* 代名詞的数詞 (数量詞) は`DET`としてタグ付けされる; `PronType`に加えて, 数量詞には素性 [NumType](/u/feat/NumType.html) を用いる.
* 形容詞のように振る舞う語は`DET`である. 類似した振る舞い:
  * 名詞句として用いられる (名詞句と置換できる) よりも，限定修飾として用いられる (名詞句を修飾する) ことの方が多い．ただし，単独で生起することもあり，これは，省略 (ellipsis) や，_All [visitors] must pay._のように，想定できる被修飾名詞が指定されないか一般的なものを表していることに起因する．
  * 屈折 (inflection) は (適用可能であるなら)，名詞ではなく形容詞に類似している．修飾する名詞と一致 (agree) し，特に，性 (gender) に関して屈折する特性は形容詞や限定詞で典型的である．(名詞の性は語彙的に決定される．限定詞では，文法から名詞との性の一致が要請される; よって，限定詞は性に関して屈折する必要がある．)
* 所有表現 (possessives) は言語で異なる．言語によっては，上記のテストによって所有表現が`DET`カテゴリに入ることがある．すなわち，所有表現は特定の格 (属格 (genitive) が多い) をとる人称代名詞や，側置詞 (adposition) を伴う人称代名詞に類似する; よって，`PRON`とタグ付けされる．

### Examples

- 冠詞 (閉じたクラスで，定性 (definiteness) や特定性 (specificity) もしくは情報の新旧 (giveness) を示すようなもの): _a, an, the_
- 所有限定詞 (名詞句を修飾する): [cs] _můj, tvůj, jeho, její, náš, váš, jejich_; [en] _my, your_
- 指示限定詞 (demonstrative determiners): _I saw <b>this</b> car yesterday._ の_this_
- 疑問限定詞 (interrogative determiners): _"<b>Which</b> car do you like?"_の_which_
- 関係限定詞 (relative determiners): _"I wonder <b>which</b> car you like."_の_which_
- 数量限定詞 (quantity determiners; 数量詞): 不定の_any_, 普遍量化子: _all_, _"We have <b>no</b> cars available."_の_no_

### References

- [Loos, Eugene E., et al. 2003. Glossary of linguistic terms: What is a determiner?](http://www-01.sil.org/linguistics/GlossaryOfLinguisticTerms/WhatIsADeterminer.htm)
- [Wikipedia](http://en.wikipedia.org/wiki/Determiner)
