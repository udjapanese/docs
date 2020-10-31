---
layout: postag
title: 'PRON'
shortdef: 'pronoun'
udver: '2'
---

### Definition

代名詞 (pronouns) とは，[nouns](NOUN) もしくは名詞句を置き換える語を指し，その意味は言語的または言語外のコンテクストから復元可能である．

この定義のもとでは，代名詞は名詞のように機能する．いくつかの言語では，_代名詞_という用語を拡張し，[adjectives](ADJ) と置き換えるようにしてあることに注意したい．そのような語は，UDのタグ付けスキームでは`PRON`とタグ付けされず，言語間で同じ手法を採るべく [determiners](DET) のタグを付与する．

代名詞と限定詞の境目が常に明瞭だとは限らない．UD v1とは異なり，これらの語の区別はコンテクストのみに基づくわけではなく，_典型的な_統語分布 (適用可能なら形態論的なものも) に基づき，辞書によって`PRON`もしくは`DET`の分類が予め決定されることもある．言語特有のドキュメンテーションでは (閉じたクラスである) 全ての限定詞をリスト化し，可能ならば曖昧な点を挙げておくべきである．

限定詞の決定に関するヒントとしては，[general principles on pronominal words](../overview/morphology.html#pronominal-words) も参照されたい
詳しい情報:

* 所有格でない人称代名詞 (non-possessive personal)，再帰代名詞 (reflexive)，相互代名詞 (reciprocal), は必ず`PRON`とタグ付けされる．
* 所有表現は言語で異なり，上記のテストによって所有表現が`DET`カテゴリに入る言語もある．すなわち，所有表現は特定の格 (属格 (genitive) が多い) をとる人称代名詞や，側置詞 (adposition) を伴う人称代名詞と類似する; よって，`PRON`とタグ付けされる

### Examples

- 人称代名詞 (personal pronouns): _I, you, he, she, it, we, they_
- 再帰代名詞 (reflexive pronouns): _myself, yourself, himself, herself, itself, ourselves, yourselves, theirselves_
- 疑問代名詞 (interrogative pronouns): _who, what_ as in _<b>What</b> do you think?_
- 関係代名詞 (relative pronouns): _who, what_ as in _I wonder <b>what</b> you think._ ([en]_that_のような，関係節を導入する語は従属接続詞 (文献によっては“補文標識 (complimentizers)“と呼ばれる) として分析した方が適切な場合があり，それらは [SCONJ]() としてタグ付けされる.)
- 不定代名詞 (indefinite pronouns): _somebody, something, anybody, anything_
- 総称代名詞 (total pronouns): _everybody, everything_
- 否定代名詞 (negative pronouns): _nobody, nothing_
- 所有代名詞 (possessive pronouns; 名詞句として単独で生起する): _mine, yours, (his), hers, (its), ours, theirs_

### References

- [Loos, Eugene E., et al. 2003. Glossary of linguistic terms: What is a pronoun?](http://www-01.sil.org/linguistics/GlossaryOfLinguisticTerms/WhatIsAPronoun.htm)
- [Wikipedia](http://en.wikipedia.org/wiki/Pronoun)
