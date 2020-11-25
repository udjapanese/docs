---
layout: relation
title: 'obl'
shortdef: 'oblique nominal'
udver: '2'
---

関係`obl`は，必須でない項 (斜格; oblique) や付加詞 (adjunct) として機能するような名詞句 (名詞，代名詞，名詞句) に対して用いられる．このことは，必須でない項が動詞，形容詞，もしくは他の副詞に付加する副詞と機能的に対応することを意味する．

関係`obl`は格 (case) によってさらなる指定を受ける．関係 [case]() と同様，`obl`は以下の事例に対して一貫した分析を提供する:

- フィンランド語の例に示される，格，前置詞もしくは後置詞による名詞の異形 (variant):

~~~ sdparse
etsiä ilman johtolankaa \n to_search without clue.PARTITIVE
obl(etsiä, johtolankaa)
case(johtolankaa, ilman)
~~~

~~~ sdparse
etsiä taskulampun kanssa \n to_search torch.GENITIVE with
obl(etsiä, taskulampun)
case(taskulampun, kanssa)
~~~

~~~ sdparse
etsiä johtolangatta \n to_search clue.ABESSIVE
obl(etsiä, johtolangatta)
~~~

- 二重目的語構文 (double object construction) に類似した分析を受ける，与格交替 (dative alternation)

~~~ sdparse
give the children the toys
obj(give, toys)
iobj(give, children)
~~~

~~~ sdparse
give the toys to the children
obj(give, toys)
obl(give, children)
case(children, to)
~~~

~~~ conllu
# give the toys to the children
1     donner    donner   VERB   _   VerbForm=Inf               0   root   _   give
2     les       le       DET    _   Definite=Def|Number=Plur   3   det    _   the
3     jouets    jouet    NOUN   _   Gender=Masc|Number=Plur    1   obj   _   toys
4-5   aux       _        _      _   _                          _   _      _   _
4     à         à        ADP    _   _                          6   case   _   to
5     les       le       DET    _   Definite=Def|Number=Plur   6   det    _   the
6     enfants   enfant   NOUN   _   Gender=Masc|Number=Plur    1   obl   _   children
~~~

`obl` は時間や場所を表す名詞修飾語に対しても用いられる:

~~~ sdparse
Last night , I swam in the pool
obl(swam, night)
obl(swam, pool)
~~~

また，動詞受身形の行為者 (任意的であり，サブタイプ obl:agentを伴う) に対しても用いられる．

~~~ sdparse
the cat was chased by the dog
nsubj:pass(chased, cat)
obl:agent(chased, dog)
~~~
