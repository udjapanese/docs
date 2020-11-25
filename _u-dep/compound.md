---
layout: relation
title: 'compound'
shortdef: 'compound'
udver: '2'
---

関係`compound`は，複合表現 (multiword expressions; MEWs) の3つの関係のうち1つ (他の2つは`fixed` と `flat`) を指す．`compounds`は以下の例に対して用いられる;

- 任意のX<sup>0</sup> 複合: 複合名詞 (例: *phone book*) や，英語以外の言語でより一般的な動詞・形容詞の複合語 (ペルシア語や日本語における軽動詞構文 (light verb construction)) といったもの)

~~~ sdparse
Phone book
compound(book, Phone)
~~~

- 不変化詞 (particle) を伴う動詞 (サブタイプ`compound:prt`として記述される):

~~~ sdparse
put up
compound:prt(put, up)
~~~

- 動詞の連結 (サブタイプ`compound:svc`として記述される):

~~~ sdparse
Musa bé lá èbi \n Musa came took knife
nsubj(bé, Musa)
compound:svc(bé, lá)
obj(bé, èbi)
~~~

関係`compound` は (他のサブタイプを含めて) 不変化詞を伴う動詞との類似性があるものの，再帰形 (reflexive morpheme) を伴う再帰動詞とのリンクを構成しない．現行のUDガイドラインでは，この構文を関係 [expl]() の [subtype](/2015-08-23-uppsala/clitics.html) として定めている.