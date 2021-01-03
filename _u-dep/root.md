---
layout: relation
title: 'root'
shortdef: 'root'
udver: '2'
---

文法関係`root`は文の根 (root) を指す．根に関して，仮想的なノード`ROOT`は支配項として用いられるが，文で生起する語のインデックスは1から始まるので，`ROOT`のインデックスは0となる (`ROOT`のノードはCoNLL-Uでは明示的に表されない)．

~~~ sdparse
ROOT I love French fries .
root(ROOT, love)
~~~

**v2から:** どのツリーであっても，依存関係`root`を結ぶ1つのノードが存在しなければならない．主述語 (main predicate) が (省略によって) 生起しない場合，そして"orphaned dependent"が複数存在する場合，それらのうち1つが主辞 (根) へと昇格 (promote) し，他の"orphan"はそれに付加される. (この規則はv1.2から続くが，v1の元々のガイドラインでは明言されていない)．

~~~ sdparse
ROOT And Robert the fourth place .
root(ROOT, Robert)
cc(Robert, And)
orphan(Robert, place)
punct(Robert, .)
amod(place, fourth)
det(place, the)
~~~
