---
layout: relation
title: 'appos'
shortdef: 'appositional modifier'
udver: '2'
---

名詞の同格修飾句 (appositional modifier) とは先頭の名詞の直後に後続する名詞を指し，名詞に対して定義，修飾，名付け，もしくは記述を行うものである．同格修飾語には括弧内にある要素や略語も含まれる．

~~~ sdparse
Sam , my brother , arrived
appos(Sam-1, brother-4)
~~~

~~~ sdparse
Bill ( John 's cousin )
appos(Bill-1, cousin-5)
~~~

~~~ sdparse
The Australian Broadcasting Corporation ( ABC )
appos(Corporation-4, ABC-6)
~~~

`appos` は2つの名詞の間に用いられる．概して，同格構造における2つの要素は交替が可能であるため，例えば_My brother, Sam, arrived._と言うことができる．
この構文に類似するものとして，肩書き (titles) といったものがある．肩書きは_state senator Paul Mnuchin_ のように完全な名詞句ではなく，交替が不可能であったり，完全な名詞句を形成するためには限定詞の挿入が必要だったりする．ラテン語由来である文法の伝統において，そのような_state senator_は「固定同格構造」と呼ばれ，名前 (Paul Mnuchin) が主辞として扱われる．しかし，ここでは名詞句が2つではなく，1つしか生起しないと考えられる．例:

> President Obama

> \*Obama President

> state senator Paul Mnuchin

> \*Paul Mnuchin state senator

そのような事例では`appos`を用いるべきでないが，通常は完全形に変えることが可能である．これはラテン語の伝統である「緩い同格構造」に相当し，完全な句が2つ生起することとなる．その場合，関係`appos`は適格である:

~~~ sdparse
Paul Mnuchin , the senior Oregon state senator
appos(Mnuchin-2, senator-8)
~~~

大体の場合では適格だが，境界となる事例も存在する．フォーマルな文書では同格構造を示す印として句読点 (punctuation) が用いられるが，句読点が無い同格構造の事例も確かに存在する:

~~~ sdparse
the leader of the militant Lebanese Shiite group Hassan Nasrallah
appos(group-8, Hassan-9)
flat(Hassan-9, Nasrallah-10)
~~~

同格構造を判別する良いテストとして，2つの要素が共に名詞かどうか，交替可能かどうか，格や一致 (agreement) が存在するかどうか (形態論が豊富な言語において) を確認することが挙げられる:

~~~ sdparse
I met the French actor Gaspard Ulliel
nsubj(met-2, I-1)
det(actor-5, the-3)
amod(actor-5, French-4)
obj(met-2, actor-5)
appos(actor-5, Gaspard-6)
flat(Gaspard-6, Ulliel-7)
~~~

~~~ sdparse
I met Gaspard Ulliel the French actor 
nsubj(met-2, I-1)
obj(met-2, Gaspard-3)
flat(Gaspard-3, Ulliel-4)
det(actor-7, the-5)
amod(actor-7, French-6)
appos(Gaspard-3, actor-7)
~~~

~~~ sdparse
I met Gaspard Ulliel , the French actor 
nsubj(met-2, I-1)
obj(met-2, Gaspard-3)
flat(Gaspard-3, Ulliel-4)
punct(Gaspard-3, ,-5)
det(actor-8, the-6)
amod(actor-8, French-7)
appos(Gaspard-3, actor-8)
~~~

~~~ sdparse
I met French actor Gaspard Ulliel
nsubj(met-2, I-1)
amod(actor-4, French-3)
obj(met-2, actor-4)
flat(actor-4, Gaspard-5)
flat(actor-4, Ulliel-6)
~~~

省略 (abbreviations) といった項目は概して交替可能であるが，上記で示した限定詞テストはうまく作用しない．限定詞は同格構造の主要な項目に属するものと考えられるからである:

~~~ sdparse
The ABC ( Australian Broadcasting Corporation )
appos(ABC-2, Corporation-6)
~~~

1つより多い同格名詞句が現れることは稀であり，それらの名詞は全て，先頭の名詞を修飾するものとして標示される．

~~~ sdparse
Sam , my brother , John 's cousin , arrived
appos(Sam-1, brother-4)
appos(Sam-1, cousin-8)
~~~

しかし，埋め込まれた同格構造を完全に排除することはできない．それは等位接続との組み合わせで生起することがある:

~~~ sdparse
You can choose between four subjects , language ( German or French ) , economy , technology and art .
appos(subjects, language)
conj(language, economy)
conj(language, technology)
conj(language, art)
cc(art, and)
appos(language, German)
conj(German, French)
cc(French, or)
~~~

`appos` は住所や署名ブロックなどにおける，キー・値を結合するときにも用いられる．([list]() ラベルも参照):

~~~ sdparse
Steve Jones Phone: 555-9814 Email: jones@abc.edf
flat:name(Steve-1, Jones-2)
list(Steve-1, Phone:-3)
list(Steve-1, Email:-5)
appos(Phone:-3, 555-9814-4)
appos(Email:-5, jones@abc.edf-6)
~~~
