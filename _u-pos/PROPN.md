---
layout: postag
title: 'PROPN'
shortdef: 'proper noun'
udver: '2'
---

### Definition

固有名詞 (proper noun) とは，特定の人物，場所，物体に対して名称を与える名詞を指す．

`PROPN`が使用できるのは，名称として用いられ，特殊な統語的性質 (英語において，冠詞を伴わずに単数形が生起する) をみせるような名詞の下位クラスに限定される．他の句や文が名称として用いられるとき，構成要素の語は元々のタグを保持する．例えば，_Cat on a Hot Tin Roof_では_Cat_は[NOUN](), _on_が[ADP](), _a_が[DET]()，など．

この手法を採る利点は，語源的に形容詞や分詞である語が_the Yellow Pages_, _United Airlines_や_Thrall Manufacturing Company_のように，表現全体が固有名詞として機能する複合表現の部分であるとき，これらの語を固有名としてみなすことが珍しくないことにある．これは，英語のPennツリーバンクのタグセットの慣習に基づく．

_UN_や_NATO_といった頭文字語 (acronym) の固有名詞は，`PROPN`としてタグ付けされる．数字 (製品名など) を含む場合であっても，[SYM]() ではなく`PROPN`としてタグ付けされる: _130XE_, _DC10_, _DC-10_．
しかし，トークン全体が桁数から構成される (_Windows 7_の_7_のように) 場合，[NUM]() とタグ付けされる．

### Examples

- _Mary_, _John_
- _London_
- _NATO_, _HBO_

### References

- [Loos, Eugene E., et al. 2003. Glossary of linguistic terms: What is a proper noun?](https://glossary.sil.org/term/proper-noun)
- [Wikipedia](http://en.wikipedia.org/wiki/Proper_noun)
