---
layout: relation
title: 'parataxis'
shortdef: 'parataxis'
udver: '2'
---

並置関係 (parataxis relation; ギリシア語で"place side by side"を意味する) とは，語や他の要素 (文括弧や“:” “;”の後の節. 主辞との等位関係 (coordenation)，従属関係 (subordination)，項関係が明示されない.) の間にある関係を指す．並置関係は談話上の等位接続に相当し，類像的な順序(iconic ordering) に従 ．よって，当該言語の主辞性 (headedness) を満たすかどうかに関わらず，通常は文の先頭部分が主辞となり，2番目の部分が並置関係の依存部となる．しかし，要素間に現れる括弧といった要因から事態はより複雑になる．

~~~ sdparse
Let 's face it we 're annoyed
parataxis(Let, annoyed)
~~~

~~~ sdparse
The guy , John said , left early in the morning
parataxis(left, said)
punct(said, ,-3)
punct(said, ,-6)
~~~

## 並置関係が適用される構文のリスト

### Side-by-side sentences ("run-on sentences")

並置関係は独立文であり得るが単一文として扱われるような文のペアに対して用いられる．この関係は，文末記号によって区切りが表され，コロンやカンマによって (もしくは，記号を用いることなしに) 複数の節が組み合わさることで成立する．話ことばコーパスでは，文としてラベル付けされるものが発話のターン (utterance turn) によって表現される．また，ツリーバンク使用者が文境界を設定するとき，2つの節を結合する談話的関係が明確である場合にもこの関係は成立する．この関係を設定する場合，等位接続に用いる分析との類似性を高めるために後部要素は全て1番目の要素の依存部として扱われる．

~~~ sdparse
Bearded dragons are sight hunters , they need to see the food to move .
parataxis(hunters, need)
punct(need, ,)
~~~

この関係は対象のユニットが文よりも小さい場合でも成立することがある:

~~~ sdparse
Divided world the CIA
amod(world, Divided)
parataxis(world, CIA)
det(CIA, the)
~~~

### 報告文 (reported speech) の扱い

報告文の例:

~~~ sdparse
The guy , John said , left early in the morning
parataxis(left, said)
punct(said, ,-3)
punct(said, ,-6)
~~~

パラフレーズによって基本的に同じ意味を伝達することができるが，それらの統語構造は異なる．報告文が従属節に埋め込まれる (補文標識_that_の有無に関わらず) とき，その従属節は発言動詞 (speech verb) の[ccomp]()となる．発言動詞に報告文が後続し，それがコロンによって分離される場合，報告文は主節を形成し，先行する主節と[並置 (parataxis)]()関係を結ぶ．しかし，発言動詞が括弧ないに生起する場合その関係は逆転し，発言動詞は報告文の[並置 (parataxis)]()として扱われる．この分析に議論がないわけではないが，ここではHuddleston and Pullum (2002), _The Cambridge Grammar of the English Language_ (11章9節を参照) といった著名な研究に従うことにしたい．

~~~ sdparse
John said that the guy left early in the morning .
ccomp(said, left)
~~~

~~~ sdparse
John said the guy left early in the morning .
ccomp(said, left)
~~~

~~~ sdparse
John said : “ The guy left early in the morning . ”
parataxis(said, left)
punct(left, :)
punct(left, “)
punct(left, ”)
~~~

~~~ sdparse
“ The guy left early in the morning ” , John said .
parataxis(left, said)
punct(said, ,)
punct(left, “)
punct(left, ”)
~~~

~~~ sdparse
The guy left early in the morning , John said .
parataxis(left, said)
punct(said, ,)
~~~

~~~ sdparse
The guy , he said , left early in the morning .
parataxis(left, said)
punct(said, ,-3)
punct(said, ,-6)
~~~

この分析の考え方とは，埋め込みとして分析された文ならば節全体にさらなる埋め込みを形成でき (_I was taken aback when John said the guy left early in the morning._)，中間部もしくは文末に発言動詞が生起する場合は埋め込みが形成できない (_*I was taken aback when the guy left early this morning, John said._)，というものである．

### ニュース記事の署名欄 (News article bylines)

並置関係は，ニュース記事の署名欄にも設定される．他に優れた関係が存在しないように思われるからである．

~~~ sdparse
Washington ( CNN ) :
parataxis(Washington, CNN)
punct(CNN, ()
punct(CNN, ))
punct(CNN, :)
~~~

### 間投詞的な節 (Interjected clauses)

単一語もしくは句の挿入 (interjections) は[discourse]()として分析されるが，節全体が挿入される場合は並置関係を用いる．

~~~ sdparse
Calafia has great fries ( they are to die for ! )
parataxis(has, are)
punct(are, ()
punct(are, ))
~~~

~~~ sdparse
Just to let you all know Matt has confirmed the booking for 3rd Dec is OK .
parataxis(confirmed, let)
~~~

2番目の例では，2番目の要素 (Matt has _confirmed_ ..) を依存関係の主辞として扱う．1番目の要素 (Just to _let_ ..)は節全体の挿入と考えられ，発話の主節ではないと思われるからである．<!--わかりにくいので括弧内を書き足したが必要なければ削除-->

### 付加疑問 (Tag questions)

並置関係は_isn't it?_や_haven't you?_といった付加疑問にも用いられる．

~~~ sdparse
It 's not me , is it ?
parataxis(me, is)
punct(is, ,)
~~~
