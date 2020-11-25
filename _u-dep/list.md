---
layout: relation
title: 'list'
shortdef: 'list'
udver: '2'
---

`list`は列挙される項目に用いられる関係を指す．2つより多くの項目を含むリストにおいて，全ての項目は先頭の項目を修飾するものとして考えられる．インフォーマルなテキストやウェブ上のテキストにはリストとして解されるフレーズを含むことが多いが，単一の文としてパージングされる．電子メールの署名では，このような構造を連絡情報という形式で表すことが多い: 別の連絡情報は，それぞれが`list`としてラベル付けされる; キーと値のペア関係は [appos]() としてラベル付けされる．

~~~ sdparse
Steve Jones Phone: 555-9814 Email: jones@abc.edf
flat:name(Steve-1, Jones-2)
list(Steve-1, Phone:-3)
list(Steve-1, Email:-5)
appos(Phone:-3, 555-9814-4)
appos(Email:-5, jones@abc.edf-6)
~~~

`list`が用いられる他の箇所として，レビューのタイトルとして用いられる，所属や記載事項の欄がある (製品やレストランのレビューなど):

~~~ sdparse
Long Lines , Silly Rules , Rude Staff , Ok Food
list(Lines, Rules)
list(Lines, Staff)
list(Lines, Food)
~~~

ただし，`list`の過剰な使用は避けるべきである．等位接続が用いられるなど，通常の文に適用される文法関係から容易に分析できる構文においては，リストのような体裁を持っていても通常の関係から分析するべきである．