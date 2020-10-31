---
layout: postag
title: 'ADJ'
shortdef: 'adjective'
udver: '2'
---

### Definition

形容詞は．典型的に名詞を修飾し，その特性や属性を指定するような語を指す:

_The **oldest French** bridge_

形容詞は述語機能を果たすこともある::

_The car is **green**._

`ADJ`タグは通常の形容詞のみを意図している．限定詞に関しては [DET]() を，(基数) 数に関しては [NUM]() を参照したい．`ADJ`は*European*といった“真正な形容詞”に対してのみ用いられる．

**数 対 形容詞:** 一般的に，基数は品詞 [NUM]() をとる一方，_序数 (ordinal numbers)_ (より正確には，_形容詞的_序数) は`ADJ`タグをとる．

数詞 (numeral) と伝統的に呼ばれる語はいくつかの言語 (e.g., チェコ語) にみられるが，UDのタグ付けスキーマでは形容詞として扱う．特に，_形容詞的_序数 (注意: チェコ語は副詞的なものを備えている) は，形態的にも統語的にも形容詞として振る舞うため，`ADJ`とタグ付けされる． 

**名詞 対 形容詞:** 別の名詞に修飾することで複合名詞 (compound noun) を形成するような名詞は，`ADJ` ではなく [NOUN]() タグが与えられる．

**分詞:** 分詞 (participles) は，その特性や用法を形容詞，名詞および動詞と共有するような語形を指す．言語やコンテクストによって，分詞は`ADJ`，[NOUN]() もしくは [VERB]() として分類される．

**形容詞を修飾する形容詞:** 一般的に，`ADJ`は [ADV]() (_**very** strong_) によって修飾される．しかし，場合によっては`ADJ`を修飾する語が`ADJ`としてみなされることがある．これらのケースは
次のものを含む: (i) 最上級の形容詞を修飾する序数 (_the **third** oldest bridge_) (ii) 2つの形容詞が複合形容詞を形成するとき (_an **African American** mayor_).


### Examples

- _big_
- _old_
- _green_
- _African_
- _incomprehensible_
- _first, second, third_

### References

- [Loos, Eugene E., et al. 2003. Glossary of linguistic terms: What is an adjective?](https://glossary.sil.org/term/adjective)
- [Wikipedia](http://en.wikipedia.org/wiki/Adjective)
