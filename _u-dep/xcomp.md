---
layout: relation
title: 'xcomp'
shortdef: 'open clausal complement'
udver: '2'
---

動詞および形容詞の開いた節補部 (open clausal complement; `xcomp`)とは，それ自身が主語を持たない述語・節の補部を指す．
よって，その主語は必然的にxcompの外部にある項から決定される (通常は上位節の目的語だが，主語からも決定される)．これを指して，*義務的コントロール (obligatory control)*と呼ぶことが多い．これらの節は多くの言語において不定節 (non-finite) をとる傾向が強いが，定形節も存在する．`xcomp`という名前はLFG (Lexical-Functional Grammar) からの借用である．

~~~ sdparse
He says that you like to swim
ccomp(says, like)
~~~

~~~ sdparse
Sue asked George to respond to her offer
xcomp(asked, respond)
obj(asked, George)
~~~

~~~ sdparse
You look great
xcomp(look, great)
~~~

~~~ sdparse
I started to work there yesterday
xcomp(started, work)
~~~

~~~ sdparse
I consider him a fool
xcomp(consider, fool)
~~~

~~~ sdparse
I consider him honest
xcomp(consider, honest)
~~~

~~~ sdparse
We expect them to change their minds
xcomp(expect, change)
obj(expect, them)
~~~

上記の条件“それ自身が主語を持たない”とは，単に主語が_明示されていない_ため当該の節が`xcomp`になるということではない．主語は上位節から継承されるのであって，下位節の主語が上位節の特定の役割から独立したという解釈が存在しないのである．以下の例にある，欠けた主語が上位節の特定の役割から独立する事例では`ccomp`が代わりに用いられる．これには恣意的な主語 (arvitrary aubjects) や照応のコントロール (anaphoric control) も含まれる

~~~ sdparse
The boss said to start digging
ccomp(said, start)
~~~

pro-drop言語には，主語が独立した語として生起しない節が存在することもあるが，この節は上位節の項に依存しているわけではない (内在的には主語があり，それは動詞形から推測が可能である)．よって，以下のチェコ語の例では主語が明示されておらず，2つ目の例のみが`xcomp`を有する．

~~~ sdparse
Píšu , protože jsem to slíbil . \n I-write , because I-have it promised .
advcl(Píšu, slíbil)
advcl(I-write, promised)
~~~

~~~ sdparse
Slíbil jsem psát . \n Promised I-have to-write .
xcomp(Slíbil, psát)
xcomp(Promised, to-write)
~~~

### Secondary Predicates

関係`xcomp`は_二次述語 (secondary predicates)_ もしくは_述語類 (predicatives)_と呼ばれる.
例:

* _She declared the cake beautiful._
* _She declared the cake a success._

上記の例は従属節を用いてパラフレーズが可能である: _She declared that the cake was beautiful._
1つの節に2つの述語が混ざって生起している: 1. she declared something 2. the cake was beautiful (彼女の意見によると).
当該の二次述語は`xcomp`として主述語に付加される．

~~~ sdparse
She declared the cake beautiful .
nsubj(declared, She)
obj(declared, cake)
xcomp(declared, beautiful)
~~~

拡張版では，二次述語を示す主語が追加される．

~~~ sdparse
She declared the cake beautiful .
nsubj(declared, She)
obj(declared, cake)
xcomp(declared, beautiful)
nsubj(beautiful, cake)
~~~

チェコ語の例:

~~~ sdparse
jmenovat někoho generálem \n to-appoint someone as-a-general
obj(jmenovat, někoho)
xcomp(jmenovat, generálem)
~~~

`xcomp`は節の述語における必須項 (core arguments) に用いられ，二次述語の他の要素には用いられない．例えば，_She entered the room sad_は述語を2重に持つ (she entered the room; she was sad) が，_sad_は_enter_の必須項ではない:_sad_は_enter_に対する文法的な影響や意味の変更をもたらさない．一方，_she declared the cake beautiful_の_beautiful_をそのままにしておくと，文が文法的でくなったり，_declared_の異なった解釈を生み出したりする．
a
つまり,_She entered the room sad_の_sad_は_She_に依存するのであって，その関係は`xcomp`ではなく[acl]()となる．