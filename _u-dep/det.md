---
layout: relation
title: 'det'
shortdef: 'determiner'
udver: '2'
---

限定詞 (`det`) は名詞句の主辞と [determiner](u-pos/DET) の関係を形成する．一般的に，POSタグの `DET` は関係`det`を持ち，その逆も成立する．知られている例外には次のものがある:

* データセットのいくつかでは [en] _my_ といった所有限定詞 (possessive determiner) にPOSタグの`DET`だけでなく[nmod]() も付与されるため，他の所有構文と並行的に扱われることになる．ただし，言語間では完全に並行的とはいえない; いくつかの言語では，どのように所有限定詞を形容詞と関係づけるかが英語よりも明確である場合があり，このことは当然関係`nmod`にも該当する．

~~~ sdparse
The man is here
det(man, The)
~~~

~~~ sdparse
Which book do you prefer ?
det(book, Which)
~~~
