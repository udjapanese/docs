---
layout: relation
title: 'advmod'
shortdef: 'adverbial modifier'
udver: '2'
---

語の副詞的修飾句 (advervial modifier) とは，[adverb](u-pos/ADV) もしくは，述語や修飾語として働く副詞句を指す．

いくつかの伝統文法においては，_副詞的修飾句 (adverbial modifier)_ という用語は，副詞，側置詞句 (adpositionnal phrases) や特定の形態的 [cases](u-feat/Case) のいずれかとして実現されるような，副詞として機能する構成要素 (constituents) を包括するものである．UDでは副詞類を，副詞として実現する _(advmod)_ と，名詞句や側置詞句 ([obl]()) として実現するものの間に区別を設ける．ただし，述語の修飾句 (狭義の副詞類) と，他の形容詞や副詞における修飾句 (修飾語句 (qualifiers) と呼ばれることがある) は区別されない．これらは全て`advmod`に包含される．

~~~ sdparse
Genetically modified food
advmod(modified, Genetically)
~~~

~~~ sdparse
less often
advmod(often, less)
~~~

~~~ sdparse
Where/ADV do/AUX you/PRON want/VERB to/ADP go/VERB later/ADV ?/PUNCT
advmod(go, Where)
advmod(go, later)
~~~

~~~ sdparse
About 200 people came to the party
advmod(200, About)
~~~

