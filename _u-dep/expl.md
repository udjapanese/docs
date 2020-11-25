---
layout: relation
title: 'expl'
shortdef: 'expletive'
udver: '2'
---

関係`expl`は虚辞 (expletive) や冗語 (pleonastic) を表す名詞句を指す．これらは述語の項位置に生起する名詞句ではあるが，それら自身は述語のいずれの意味役割 (semantic role) を満たさない．節の主述語 (動詞，叙述形容詞もしくは名詞) が支配項となる．英語において，*it* や *there* のいくつかは虚辞に該当する: 外置 (extraposition construction) における存在の*there*や*it*.
(*it*や*there*は虚辞でない用法もある)

~~~ sdparse
There is a ghost in the room
expl(is, There)
~~~

~~~ sdparse
It is clear that we should decline .
expl(clear, It)
~~~

自由なpro-drop (顕在的な代名詞の代わりにゼロ照応 (zero-anaphora) を使えること) を有する英語のような虚辞を持たない．
Some languages do not have expletives of the English sort, including most languages with free pro-drop (the ability to use zero anaphora rather than overt pronouns). 

この種の虚辞を持つ言語では，虚辞は必須項が生起する場所に位置することができる: 以下の例に見られる，主語と直接目的語 (間接目的語も) のスロット．これらの例の分析において，後置主語 (postposed subject) や節の項は規則的な必須項として扱われ，虚辞は`expl`として標示される．

~~~ sdparse
There is a ghost in the room
expl(is, There)
nsubj(is, ghost)
obl(is, room)
~~~

~~~ sdparse
I believe there to be a ghost in the room
nsubj(believe, I)
expl(believe, there)
xcomp(believe, be)
nsubj(be, ghost)
obl(be, room)
~~~

~~~ sdparse
It is clear that we should decline .
expl(clear, It)
csubj(clear, decline)
~~~

~~~ sdparse
That we should decline is clear .
csubj(clear, decline)
~~~

~~~ sdparse
I mentioned it to Mary that Sue is leaving
nsubj(mentioned, I)
expl(mentioned, it)
obl(mentioned, Mary)
ccomp(mentioned, leaving)
~~~

関係`expl`に関連する第二の使用法は，真正な二重接語 (true clitic doubling) に関するものである．接語や語彙的名詞句が相補的分布を示す言語 –"Kayneの一般化"に従うようなフランス語等の言語–において，接語と語彙的名詞句のどちらが生起したとしても，[obj]() もしくは [iobj]()といった適切な意味役割を受ける．口語フランス語など，そのような言語で接辞の二重化が起きた場合，語彙的名詞句を [dislocated]() としてみなすことが正しい分析の仕方となる (例を参照)，そのような事例では，当該の分析がAs such, the analysis will be the same as when a noun phrase doubles another noun phrase or a regular pronoun that fills a nominal argument position. However, other languages, such as Greek and Bulgarian, standardly allow doubling of a lexical nominal and a pronominal clitic, with the former still appearing in its regular role as an argument of the predicate. In these cases, if only one of the lexical nominal and the clitic appear in a clause, then whichever appears will be given the grammatical role of [obj](), [iobj](), etc. – parallel to the treatment of lexical nominals and pronouns in other languages, modulo the clitic pronoun having a different position in the sentence.  However, if both occur, the lexical nominal will be given the grammatical role of [obj](), [iobj](), etc., and the clitic will be treated as a pronominal copy, which does not receive its own semantic role, and hence will get the role `expl`. Modulo the different word order, this is fairly parallel to the treatment of _it_ and _there_ in English mentioned above, where another phrase satisfies the semantic role of the predicate. Examples from Greek and Bulgarian follow:

~~~ sdparse
Της τον έδωσε της Καίτης τον αναπτήρα \n PRON.Fem.Gen PRON.Masc.Acc gave ART.Fem.Gen Keti.Gen ART.Masc.Acc lighter.Acc
expl(έδωσε, Της-1)
iobj(έδωσε, Καίτης)
det(Καίτης, της-4)
expl(έδωσε, τον-2)
obj(έδωσε, αναπτήρα)
det(αναπτήρα, τον-6)
~~~

~~~ sdparse
Marija mu izprati pismo na rabotnika \n Maria 3.S.M.IO sent letter to the.worker
expl(izprati, mu)
obj(izprati, pismo)
iobj(izprati, rabotnika)
case(rabotnika, na)
~~~

## Reflexives

虚辞の関係は再帰動詞 (reflexive verbs) へ付加付加する再帰代名詞 (reflexive pronouns) にも用いらる (素性 [u-feat/Reflex]() を参照せよ)．再帰代名詞とは再帰代名詞なしでは生起しない動詞を指し，ゆえに代名詞が通常の目的語の役割を果たさない (一方で，再帰代名詞は通常の代名詞や他の名詞句との置き換えが可能である).

UDでは再帰代名詞 (接語) に複数の機能を認めており，これらは関係`expl`のサブタイプを用いることで区別される (このアプローチが認められることは [2015 Uppsala discussion of clitics](/2015-08-23-uppsala/clitics.html) を参照されたい.):

* [expl:pv]() は，元々が再帰動詞であるもの (いくつかの文法において代名詞動詞 (pronominal verbs) と呼ばれるもの) に付加する再帰接語 (reflexive clitics) に対して用いられる
* [expl:pass]() は，他動詞に付加する再帰接語に用いられ，ヴォイスのマーカー (受身や逆使役を表す) としてふるまう
* [expl:impers]() は，亜人格的な使用 (impersonal usage) に対して用いられる (自動詞と共に用いられる場合もある)
チェコ語の例:

~~~ sdparse
Martin se bojí zvířat . \n Martin REFLEX fears animals .
expl:pv(bojí, se)
expl:pv(fears, REFLEX)
~~~

虚辞のさらなる一般的は議論については Postal, P. M., and G. K. Pullum (1988) “Expletive Noun Phrases in Subcategorized Positions,” _Linguistic Inquiry_ 19(4): 635–670 を参照されたい.
二重接語 (clitic doubling) のステータスや，代名詞コピーの一種である接辞の項となる語彙的名詞句に対する議論については，特にBoris Harizanov (2014) [Clitic doubling at the syntax-morphology interface: A-movement and morphological merger in Bulgarian](http://stanford.edu/~bharizan/pdfs/Harizanov_2014_NLLT.pdf). _Natural Language and Linguistic Theory_ に現れる. 