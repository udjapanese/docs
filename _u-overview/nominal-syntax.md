---
layout: base
title:  'Nominals'
permalink: u/overview/nominal-syntax.html
udver: '2'
---

# Nominals

UDのタグ付けでは，名詞類 (nominal) もしくは名詞句 (noun phrase) は全ての言語において確認される基本構造の一つと仮定する．名詞句は，少なくとも名詞，固有名詞 (proper noun), もしくは代名詞 (pronoun) から構成される．

~~~ sdparse
hon såg filmen . \n she saw the-film
obj(såg, filmen)
~~~
~~~ sdparse
hon såg Batman \n she saw Batman
obj(såg, Batman)
~~~
~~~ sdparse
hon såg den \n she saw it
obj(såg, den)
~~~

## Modifier Dependents

名詞句の主辞 (head) は必須項 (core arguments) をとらないが，様々なタイプの修飾語 (modifiers) と結びつくことがある．

1. `nmod` は，ある名詞句を修飾する別の名詞句を指し，特別な格マーカー (case marker) を伴う場合がある．Treebankでは，後置詞を用いない所有 (non-adpositional possessives) と区別するため，任意に  `nmod:poss` を使う場合がある．
2.  `appos` は，別の名詞句の主辞に後続する名詞句を指し，同一指示 (co-reference) もしくは，他の等価関係 (equivalence relation) を表す．
3.  `amod` は名詞句の主辞を修飾する形容詞を指す.
4. `nummod` 名詞句の主辞を修飾する数詞 (numeral) を指す．
5.  `acl` は名詞句の主辞を修飾する節を指し，重要な下位タイプとして関係節 `acl:relcl` がある．
~~~ sdparse
the office of the Chair
nmod(office-2, Chair-5)
~~~

~~~ sdparse
the Chair 's office
nmod:poss(office-4, Chair-2)
~~~

~~~ sdparse
Sam , the manager
appos(Sam, manager)
~~~

~~~ sdparse
Sam eats red meat
amod(meat, red)
~~~

~~~ sdparse
Sam spent forty dollars
nummod(dollars, forty)
~~~

~~~ sdparse
Sam spent everything he had
acl:relcl(everything, had)
~~~

~~~ sdparse
Sam spent everything that he had
acl:relcl(everything, had)
obj(had, that)
~~~

## Function Word Dependents

さらに，名詞句は以下の典型的な機能語依存部 (function word dependents) を含むことがある．

* 限定詞 (Determiners) は名詞句の主辞に付加され， `det` によって表される．
* 後置詞 (Adpositions) は名詞句の主辞に付加され， `case` によって表される.
* 助数詞 (Classifiers) は数詞もしくは所有形 (possessive) <!-- 属格? -->に付加され， `clf` によって表される.
~~~ sdparse
the Chair 's office
det(Chair-2, the-1)
nmod(office-4, Chair-2)
case(Chair-2, 's-3)
~~~

~~~ sdparse
the office of the Chair
det(office-2, the-1)
nmod(office-2, Chair-5)
case(Chair-5, of-3)
det(Chair-5, the-4)
~~~

~~~sdparse
sān gè xuéshēng \n three clf student
nummod(xuéshēng, sān)
clf(sān, gè)
~~~
