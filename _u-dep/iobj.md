---
layout: relation
title: 'iobj'
shortdef: 'indirect object'
udver: '2'
---

動詞の間接目的語 (indirect object) は，動詞の必須項 (core argument) ではあるが，主語や (直接) [object](obj) ではないような名詞句を指す．典型例には，交換を表す，二重目的語を取る動詞の受領者 (recipient) がある:

~~~ sdparse
She gave me a raise
iobj(gave, me)
nsubj(gave, She)
~~~

しかし，多くの言語では他の意味役割も間接目的語として許容する．最も一般的な事例としては受益者 (benefactive) があるが，他言語では他の役割，例えば，以下のKinyarwanda語の例が示す道具 (instrument)，もしくはcomitative といったものも含む．もう一方の極として，あらゆる間接目的語を欠く言語も存在する．

~~~ sdparse
Umukoóbwa a-ra-andik-iish-a íbárúwa íkárámu \n girl 1-PRS-write-APPL-ASP letter pen
obj(a-ra-andik-iish-a, íbárúwa)
iobj(a-ra-andik-iish-a, íkárámu)
~~~

形態 [cases](u-feat/Case) を区別する言語において，間接目的語は与格 (dative case) として標示されることが多い．しかし，動詞の結合価 (valency) が，直接目的語が与格を持つ，あるいは間接目的語が他の様々な形式をとるように定めることもある．

以下のチェコ語の例では，動詞が項を2つとり，両者が共に対格 (accusative case) として実現している．そのうち一方は直接目的語 (被動作主) であり，もう一方は間接目的語 (聞き手) である．これは，英語の対訳に対して与えられるタグ付け (形態格の標示がない場合において) と平行的であり，授与動詞 (verbs of giving) の分析とも平行的である (類似した文として，_he gave my daughter a class of maths_を考えてほしい).

~~~ sdparse
On učí mou dceru matematiku . \n He teaches my daughter.Acc maths.Acc .
obj(učí, matematiku)
iobj(učí, dceru)
obj(teaches, maths.Acc)
iobj(teaches, daughter.Acc)
~~~

一般的に，目的語が1つしか存在しない場合，形態格や意味役割の種類に関わらず [obj]() とタグ付けされる．例えば，英語の_teach_は，教科 (subject matter) や生徒 (recipient) のどちらであっても唯一の目的語にとれる．よって，両者は共に [obj]() として分析される:

~~~ sdparse
She teaches introductory logic
obj(teaches, logic)
~~~

~~~ sdparse
She teaches the first-year students
obj(teaches, students)
~~~

この分析は，Huddleston and Pullum (2002) “The Cambridge Grammar of the English Language”, 4章4節 (p. 251) のものと整合している．この文献で述べられるように，自動詞/他動詞の交替において，同じ意味役割が主語になったり目的語になったりしても，それには違いが生じない.

<!--以下，もともとコメントアウト部分
The one exception is when there is a clausal complement.
Then the clausal complement is regarded as a “clausal object” and an object nominal will be an iobj, parallel to
the simple ditransitive case:

~~~ sdparse
She told the students that they needed to study this evening
iobj(told, students)
ccomp(told, needed)
~~~

~~~ sdparse
She told the students the plan
iobj(told, students)
obj(told, plan)
~~~

If there are two or
more objects, one of them should be [obj]() and the others should be
`iobj`. In such cases it is necessary to decide what is the
most directly affected object _(patient)._ If possible,
language-specific documentation should help identify direct and
indirect objects.
-->
