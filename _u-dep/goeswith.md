---
layout: relation
title: 'goeswith'
shortdef: 'goes with'
udver: '2'
---

関係`goeswith`は，編集がうまく行われず，語の2つ以上の部分に分離しているものを結合する関係を指す．これらの部分は当該言語の書記法において，1つの語として記載されるべきである．その主辞は常に先頭の部分であり，他の部分は関係`goeswith`を用いて先頭要素へ付加させる (記述の一貫性に配慮し，[flat](), [fixed]() および [conj]() に似せてある)．
また，最後の部分は`SpaceAfter=No`とタグ付けされる場合があるため注意したい．

~~~ sdparse
They come here with out legal permission
goeswith(with-4, out-5)
~~~

~~~ sdparse
never the less/[SpaceAfter=No] ,
goeswith(never, the)
goeswith(never, less)
~~~
