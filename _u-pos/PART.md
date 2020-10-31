---
layout: postag
title: 'PART'
shortdef: 'particle'
udver: '2'
---

### Definition

不変化詞 (particles) とは，他の語や句と連結することで意味を与え，他の品詞 (e.g. [adpositions](ADP), [coordinating conjunctions](CCONJ), [subordinating conjunctions](SCONJ) もしくは[auxiliary verbs](AUX)) の定義を満たさないような機能語を指す．不変化詞は否定，ムード，時制といった文法カテゴリをエンコードすることがあり，例外はあるものの，通常は屈折しない．

`PART`タグは，ゲルマン諸語における，_give <b>in</b>_や_end <b>up</b>_といった_小辞 (verbal particles)_ と呼ばれるものを包括することができない．
これらは元々側置詞や副詞であるため，[ADP]() や [ADV]() としてタグ付けされる．ゲルマン諸語における分離可能な動詞接頭辞 (separable verb prefixes) の扱いは類推から与えられる．

日本語において伝統的に助詞と呼ばれる機能語の全てが自動的に`PART`タグの資格を持つわけではない．`PART`として扱うものには，例えば疑問助詞 か/_ka_ があり，他の助詞 (e.g. に/_ni_，の/no) は他言語における側置詞 (adpostion) と並行的であるため，[ADP]() としてタグ付けされる．

一般的に，`PART`タグの適用は限定すべきで，他のタグが適用できない場合に限り用いるべきである．言語特有のドキュメンテーションでは，`PART`として分類される語をリストしておくことが望ましい．

### Examples

- 所有マーカー (possessive marker): [en] _'s_
- 否定辞 (negation particle): [en] _not;_ [de] _nicht_
- 疑問助詞 (question particle): [ja] か / _ka_ (adding this particle to the end of a clause turns the clause into a question); [tr] _mu_
- 文のモダリティ (sentence modality): [cs] _ať, kéž, nechť_ (_Let's_ do it! _If only_ I could do it over. _May you_ have an enjoyable stay!)

### References

- [Loos, Eugene E., et al. 2003. Glossary of linguistic terms: What is a particle?](http://www-01.sil.org/linguistics/GlossaryOfLinguisticTerms/WhatIsAParticle.htm)
- [Wikipedia](http://en.wikipedia.org/wiki/Grammatical_particle)
