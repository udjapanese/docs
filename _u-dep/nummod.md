---
layout: relation
title: 'nummod'
shortdef: 'numeric modifier'
udver: '2'
---

名詞に対する数の修飾語は [number](u-pos/NUM) であり，名詞を数量によって修飾する．

~~~ sdparse
Sam ate 3 sheep
nummod(sheep, 3)
~~~

~~~ sdparse
Sam spent forty dollars
nummod(dollars, forty)
~~~

~~~ sdparse
Sam spent $ 40
nummod($, 40)
~~~

_few や many_ といった不定の数量詞 (quantifier) は [u-pos/NUM]() ではなく，[u-pos/DET]() としてタグ付けされることに注意．よって，このような数量化をうけた名詞は`nummod`ではなく，[det]() としてタグ付けされる:

~~~ sdparse
Sam ate many sheep
det(sheep, many)
~~~
