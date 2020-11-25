---
layout: relation
title: 'fixed'
shortdef: 'fixed multiword expression'
udver: '2'
---

関係`fixed`は，複合表現 (multiword expressions; MWEs) に用いられる3つの関係のうち，その1つを指す (他の2つは[flat]() および [compound]()).
`fixed`は機能語もしくは短い副詞句として振る舞うような，文法化した固定表現に対して用いられる．


**New from v2:** 関係の適用範囲に対する誤解を防ぐ目的で，関係`fixed`は従来の`mwe`と置き換えられる

MWEにおける`fixed`の適用範囲は，おおよそ [Sag et al.](http://lingo.stanford.edu/pubs/WP-2001-03.pdf) の*fixed expressions*カテゴリに相当し，準固定表現 (semi-fixed) や可変性のあるMEW (flexible MWEs) は排除される．

固定したMEWは平板構造 (flat structure) としてタグ付けされる．MWEにおいて先頭の語に後続するすべての語は，ラベル`fixed`を用いて先頭の語に付加させる．これらの表現は内部の統語構造を持たず (歴史的な観点を除くと)，構造のタグ付けは原理的に恣意的になってしまう．ただし実践上の理由から，全ての言語において一貫したタグ付けを固定したMWEに与えることが望ましい．

~~~ sdparse
I like dogs as well as cats
fixed(as-4, well-5)
fixed(as-4, as-6)
~~~

~~~ sdparse
He cried because of you
fixed(because, of)
~~~

~~~ sdparse
Je préfère prendre un dessert plutôt qu' une entrée \n I prefer getting a dessert rather than an appetizer
fixed(plutôt, qu')
~~~

