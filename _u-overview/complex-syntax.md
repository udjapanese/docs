---
layout: base
title:  'Basic Dependencies: Complex Clauses'
permalink: u/overview/complex-syntax.html
udver: '2'
---

# 複雑な節 (Complex Clauses)

* [Coordinated clauses](#coordination)
* [Subordinate clauses](#subordination)
* [Secondary predicates](#secondary-predicates)

## 等位関係 (Coordination)

２つの主節もしくは，２つの従属節が同じレベルで等位構造 (coordinate structures) を成す場合，等位関係を持つ複合節 (complex clauses) が生起する (等位接続詞 (coordinating conjunction) が表層に現れるとは限らない)．
先頭の接続詞を主辞 (head) とし，他の全ての接続詞は [u-dep/conj]() を用いて主辞に付加させることによって，等位構造は非対称的に扱われる．
%%
等位接続詞および等位項 (conjuncts)  を限定するカンマ等の句読点は，後続する等位項へ付加される．前者は関係 [u-dep/cc]() が，後者は関係  [u-dep/punct]() がそれぞれ用いられる．

~~~ sdparse
He came home , took a shower and immediately went to bed .
conj(came, took)
conj(came, went)
punct(took, ,-4)
cc(went, and)
~~~

等位接続詞が表層に現れない場合，等位接続の省略 (asyndetic coordination) が起こる．

~~~ sdparse
Veni , vidi , vici .
conj(Veni, vidi)
conj(Veni, vici)
punct(vidi, ,-2)
punct(vici, ,-4)
~~~

特別な場合として，先頭の等位項が暗示されたり<!--implicit-->，先行する文の部分であることがある．

~~~ sdparse
And then we left .
cc(left, And)
~~~

### 節の等位接続における省略 (Ellipsis)

<!--等位関係は _省略要素 (ellipsis)_ と結合することがよくある．省略要素は通常必須の構成素であり，もう片方の連言子 (conjunct) の内容から推測可能であるため省略される．
Coordination is often combined with _ellipsis_, where one or more of the normally obligatory constituents
of a clause or omitted because they can be inferred from material in another conjunct.-->

一次述語 (main predicate) が省略された場合，関連する `aux` か `cop` が節の主辞へと昇格 (promoted) する.

~~~ sdparse
Sue likes pasta and Peter does , too .

nsubj(likes-2, Sue-1)
obj(likes-2, pasta-3)
conj(likes-2, does-6)
nsubj(does-6, Peter-5)
advmod(does-6, too-8)
~~~

~~~ sdparse
Sue is hungry and Peter is , too .

nsubj(hungry-3, Sue-1)
cop(hungry-3, is-2)
conj(hungry-3, is-6)
nsubj(is-6, Peter-5)
advmod(is-6, too-8)
~~~

述語は省略されるが `aux` or `cop` が現れないような複雑な例において，昇格 (promotion) は不自然かつ混乱を招くような関係をもたらすことがある．例えば，以下の文では _you_ が _coffee_ の主語であり，2番目の節が省略された述語というより動詞を用いない述語 (noverbal predication) を含むことが示される．

~~~ sdparse
I like tea and you coffee .

nsubj(like-2, I-1)
obj(like-2, tea-3)
nsubj(coffee-6, you-5)
conj(like-2, coffee-6)
~~~

よって，そのような例では `orphan` という特別な関係を用いて昇格した要素に<!--attach siblings-->付加することにする．

~~~ sdparse
I like tea and you coffee .

nsubj(like-2, I-1)
obj(like-2, tea-3)
conj(like-2, you-5)
cc(you-5, and-4)
orphan(you-5, coffee-6)
~~~

~~~ sdparse
Mary wants to buy a book and Jenny a CD .

nsubj(wants-2, Mary-1)
xcomp(wants-2, buy-4)
obj(buy-4, book-6)
conj(wants-2, Jenny-8)
orphan(Jenny-8, CD-10)
~~~

~~~ sdparse
They had left the company , many for good .

nsubj(left, They)
obj(left, company)
conj(left, many)
orphan(many, good)
~~~

~~~ sdparse
Mary wants to buy a book . ROOT And Jenny a CD .

nsubj(wants-2, Mary-1)
xcomp(wants-2, buy-4)
obj(buy-4, book-6)
root(ROOT, Jenny)
orphan(Jenny, CD)
~~~

だが，関係 `orphan` は通常の関係が誤解を招く (例えば，目的語が主語に付加される場合) ときに限って用いられることに注意されたい．特に， 通常は関係 `cc` が等位接続に用いられるべきであり， それは `orphan` の依存関係 (dependency) によって形成された擬似的な構成素 (pseudo-constituent) に付加される.

## 従属関係 (Subordination)

主要な，ないしは主要でない依存部 (dependent) が節構造として実現されるため，従属関係 (subordination) に関与する複雑な節 (complex clauses) が発生する．これは，以下の4つの基本タイプに区別される．:

1. 節の主語 (Clausal subjects) ([u-dep/csubj]()).
2. 補文節 (Clausal complements; 目的語) で，コントロール (control) を義務的に受けるもの ([u-dep/xcomp]()) と ([u-dep/ccomp]()) に分かれる.
3. 副詞節を形成する修飾句 (Adverbial clause modifiers) ([u-dep/advcl]()).
4. 名詞を後置修飾する節 (Adnominal clause modifiers) ([u-dep/acl]()) (多くの言語では，関係節 (relative clauses) が4の重要な下位タイプである).

さらに，_二次述語 (secondary predicates)_ についても議論の対象となり，これは節の補部ないしは名詞に後置される節を形成する修飾句として分析される．

### 節の主語 (Clausal Subjects)

節の主語 (clausal subject) は節の統語的な主語であり，その統率子 (governor) となるのは，動詞もしくは動詞を用いない述語 (nonverbal predicate) の場合がある．統率子が受動態 (passive) にある場合，下位タイプの `csubj:pass` が用いられる場合がある．


~~~ sdparse
What she said makes sense
csubj(makes, said)
~~~

~~~ sdparse
What she said is interesting
csubj(interesting, said)
~~~

~~~ sdparse
What she said was well received
csubj:pass(received, said)
~~~

### 補文節 (Clausal Complements; 目的語)

動詞や形容詞の補文節は依存部の節であり，必須項 (core argument) である. すなわち，それは動詞や形容詞の目的語のように機能する．

~~~ sdparse
He says that you like to swim
ccomp(says, like)
mark(like, that)
~~~

~~~ sdparse
He says you like to swim
ccomp(says, like)
~~~

補文節は定節 (finite) もしくは不定節 (infinite) であるが，不定節の主語がコントロールを受ける (つまり，上位の節と主語や目的が同一であり，他の解釈を受けない) 場合，[xcomp]() が適切な関係となる．

~~~ sdparse
The boss said to start digging
ccomp(said, start)
mark(start, to)
xcomp(start, digging)
~~~

~~~ sdparse
We started digging
xcomp(started, digging)
~~~

上の2つの文には重要な違いがある．1つ目の文では，誰が掘ること (digging) を始めたのかは照応 (anaphora) が問題とすることである (文脈上で関連性のある個人や集団を指し，ここでは上司 (the boss) を含むかもしれない)．その一方で，どちらの文においても，何かを始めた人物と掘ることを始めた人物は必ず同一となる (すなわち，第2文では __digging__ の主語は __we__ に限られる)． `ccomp` と `xcomp` に区別をもたらすのは，この違いである．

[xcomp]() のコントロールされた主語は，  [obj]() にもなりうる — すなわち，当該の要素が現れる場合，それは [obj]() である (Visserの一般化)．UDでは，そのような構文を不定節を伴う目的語 (目的語の上昇 ("raising to object")) として分析する (近年の生成文法 (generative grammar) で多くみられる，小節 ("small clause") もしくは欠格 ("exceptional case marking") による分析を採らない)． よって，主節の目的語と従属節の主語が義務的にコントロールの関係を形成する例において，UDは以下のような分析を用いる．:

~~~ sdparse
Sue persuaded Fred to accept the job.
obj(persuaded, Fred)
mark(accept, to)
xcomp(persuaded, accept)
~~~

~~~ sdparse
Please let us know
discourse(let, Please)
obj(let, us)
xcomp(let, know)
~~~

そして，`ccomp` は完全な節に関与する等価構文 (equational constructions) におけるコピュラ動詞 (copulas) に用いられる．

~~~ sdparse
The important thing is to keep calm.
ccomp(is, keep)
nsubj(is, thing)
~~~

~~~ sdparse
The problem is that this has never been tried .
ccomp(is, tried)
nsubj(is, problem)
~~~

(このような例において，コピュラ動詞は，節境界の緊密性 (integrity) を保持し，1つの述語が2つの主語に割り当てられることを避けるため，主辞として扱われる．名詞句が関与して，そのうちの1つが主辞として扱われるような等価構文の分析を考えたとき，上記の分析が最適とは言えないが，現在のところ推奨される解決策である．)


### 副詞節を形成する修飾句 (Adverbial Clause Modifiers)
 
副詞節を形成する修飾句 (adverbial clause modifier) は，動詞や他の述語 (形容詞など) を修飾する節を指し，必須の補部 (core compliment) ではなく，修飾句 (modifier) として分析される．これには，時間を表す節，結論 (consequence) や条件を表す節，目的を表す節などが含まれる．その依存部は必ず節であり (もしくは  [advmod]()) )，[advcl]() の依存部はその節内の一次述語である．<!--The dependent must be clausal (or else it is an [advmod]()) and the dependent is the main predicate of the clause. は理解ができるが，訳に困った．-->

~~~ sdparse
The accident happened as night was falling
advcl(happened, falling)
~~~

~~~ sdparse
If you know who did it, you should tell the teacher
advcl(tell, know)
~~~

~~~ sdparse
He talked to him in order to secure the account
advcl(talked, secure)
~~~

~~~ sdparse
He was upset when I talked to him
advcl(upset, talked)
~~~

### 名詞を後置修飾する節 (Adnominal Clause Modifiers)

名詞を後置修飾する節 (An adnominal clause modifier) は，名詞句を修飾する節である． 

~~~ sdparse
the issues as he sees them
acl(issues, sees)
~~~

~~~ sdparse
Cette affaire à suivre \n This case to follow
acl(affaire, suivre)
~~~

この関係は任意の描写述語 (optional depictives) に対しても用いられる．以下の例では，形容詞が名詞句を修飾するものとして扱われ，名詞句の二次述語 (secondary predication) として働く．

~~~ sdparse
She entered the room sad
acl(She, sad)
~~~

~~~ sdparse
He painted the model naked
acl(model, naked)
~~~

関係節は後置節の特殊なタイプであり，これは，定性 (finiteness) や，埋め込み節 (embedded clause) において通常起こる被修飾名詞の省略から特徴づけられる．いくつかの言語では関係節の伝統的なクラスにおける，言語特有の下位タイプを用いる．

~~~ sdparse
I saw the man you love
acl(man, love)
~~~

また，いくつかの言語では，*fact* や *report* といった名詞の部分集合に対して定の補文節を許すことがある．これらは，おおよそ関係節に類似しているが，依存部の節において<!--ロール (role)--> の省略を許さない (これはHuddleston and Pullum (2002) における "content clauses" のクラスである)．このような補文節も，同様に `acl` として分析される．

~~~ sdparse
the fact that nobody cares
acl(fact, cares)
~~~

## 二次述語 (Secondary Predicates)

節は_二次述語 (secondary predication)_ や <!--_述語相当のもの (predicative)_-->を含む．このような効果が叙述名詞 (predicative noun) や前置詞が標示された句によって生まれたとしても，最も一般的な例は形容詞である．

* _She declared the cake **beautiful**._
* _She declared the cake **a success**._
* _She entered the room **sad**._
* _She hammered the metal **flat**._

このような文には2つの述語，すなわち一次述語と二次述語があり，後者は *the cake* が *beatiful* であったり， *She* が *sad* であることを表す.


Huddleston and Pullum (2002) の “The Cambridge Grammar of the English Language”  4章の5.3節では，述語相当の要素を任意的なものと義務的なものに分けており，それらは描写的 (depictives) であるか結果的 (resultatives) であるかのどちらかに属し，自動詞節か他動詞節に現れる．よって，以下の8つの可能性がある．:

* _He looked **fantastic**._ [obligatory, depictive, intransitive host]
* _She kept Kim **warm**._ [obligatory, depictive, transitive host]
* _The boss became **angry**._ [obligatory, resultative, intransitive host]
* _This made me **furious**._ [obligatory, resultative, transitive host]
* _He died **young**._ [optional, depictive, intransitive host]
* _He ate the steak **almost raw**._ [optional, depictive, transitive host]
* _The pond froze **solid**._ [optional, resultative, intransitive host]
* _He painted the house **blue**._ [optional, resultative, transitive host]

UDでは，義務的な述語は常に `xcomp` として扱われる: 二次述語は一次述語の `xcomp` として付加される．大抵の場合では，描写的な形容詞と同じ位置に，動詞か名詞句で表される述語を用いることができる (例 _He looked [an idiot]_; _This made me [seethe with anger]_)．

~~~ sdparse
She declared the cake beautiful .
nsubj(declared, She)
obj(declared, cake)
xcomp(declared, beautiful)
~~~

精密な表示では二次述語を表す主語の関係が示され，それは上位の節における義務的な役割である．:

~~~ sdparse
She declared the cake beautiful .
nsubj(declared, She)
obj(declared, cake)
xcomp(declared, beautiful)
nsubj(beautiful, cake)
~~~

チェコ語の例 :

~~~ sdparse
jmenovat někoho generálem \n to-appoint someone as-a-general
obj(jmenovat, někoho)
xcomp(jmenovat, generálem)
~~~


関係 `xcomp` は節の述語の必須項であり，二次述語の他のインスタンスとしては用いられない．任意の描写述語 (optional depictives) は付加詞 (adjuncts) として分析され，述語が意味的に修飾する名詞句 (それが現れるならば) に対して [acl]() が形成される．

例えば _She entered the room sad_ では，二重の述定 (predication) を持つ (彼女はその部屋に入った; 彼女は悲しんだ)．
しかし，_sad_ は _enter_ の必須項ではない; _sad_ を省略したとしても文法的には影響を与えず，動詞 _enter_ の意味にも大きな変化をもたらすことがない．
その一方で，_She declared the cake beautiful_ の _beautiful_ を省略した場合，文が文法的でなくなるか，_decleared_ の解釈が異なったものとなるだろう．
その結果， _She entered the room sad_ では _sad_ が _She_ に依存することとなり，`xcomp` のかわりに関係 [acl]() が用いられる．

~~~ sdparse
She entered the room sad .
obj(entered, room)
acl(She, sad)
~~~

~~~ sdparse
He painted the model naked .
obj(painted, model)
acl(model, naked)
~~~

もしも名詞句の主辞がない場合，二次述語が [adverb](../pos/ADV.html) ではなく [adjective](../pos/ADJ.html) であったとしても，それは動詞述語の [advcl]() として付加されなければならない．
以下の例では2番目の述定があって形容詞が述定の主辞を成しており (*She is sad* のように)，2番目の述定を表現する他の語は存在しない:

~~~ sdparse
Vstoupila do místnosti smutná . \n She-entered to room sad .
advcl(Vstoupila, smutná)
advcl(She-entered, sad)
~~~

残った例としては任意の結果述語 (resultatives) があり，これらには一貫して  `xcomp` を用いる:

~~~ sdparse
He painted the house blue .
obj(painted, house)
xcomp(painted, blue)
~~~

上記の例で結果述語が任意だとしても，それは上位にある動詞の補部 (項) である (彼が何かを青色に塗っている) という主張があるかもしれない．
そのように，任意の結果述語を必須項として捉える分析は， Huddleston and Pullum (p. 262) によって英語に適用されている．また，LFGの用語を用いるなら，動詞が語彙規則を適用した結果，新しい下位範疇フレーム (subcategorization frame) を得ることとなり，このフレームは追加の `xcomp` 項を包含する．このような分析は， _to bark_ のような自動詞が通常， `obj` や  `xcomp` の両方を加えて新たな下位範疇を得ることにより，類似した結果述語を形成できるという事実によって支持される．これは，以下の例が示す通りである．

~~~ sdparse
The dog barked the neighbors awake .
obj(barked, neighbors)
xcomp(barked, awake)
~~~

