---
layout: relation
title: 'dislocated'
shortdef: 'dislocated elements'
udver: '2'
---

関係`dislocated`は前置もしくは後置した要素に用いられ，必須である文の文法関係を満たさない. これらの要素は文の周辺部 (periphery) に生起することが多く，カンマやイントネーションによって分離する場合がある．

この関係は文のトピックを導入するような前置要素に用いられ，以下の日本語およびギリシア語の例から示される．転移要素 (dislocated element) は節の主辞に付加される:

~~~ sdparse
象 は 鼻 が 長い \n zoo wa hana ga naga-i \n elephant TOPIC nose SUBJ long-PRES
dislocated(長い-5, 象-1)
~~~

~~~ sdparse
to jani ton kserume poli kala \n the John-Acc him know-1pl very well 
dislocated(kserume, jani)
~~~

しかし，トピックの標示を受け，当該文の主語でもあるような名詞には用いられない; この場合，[nsubj]() となる.

また，この関係は後置要素にも用いられる．転移要素は同一の支配項 (governor) に付加され，右方転移要素 (Right dislocated elements) は話言葉で頻繁に用いられる．<!--The dislocated elements attach to the same governor as the dependent that they double for.-->以下はフランス語とギリシア語の例である．

~~~ sdparse
Il faut pas la manger , la plasticine \n It must not it eat , the playdough
obj(manger, la-4)
dislocated(manger, plasticine)
obj(eat, it-13)
dislocated(eat, playdough)
~~~

~~~ sdparse
ton kserume oli mas edho poli kala, to jani 
dislocated(kserume, jani)
~~~
