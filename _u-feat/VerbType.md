---
layout: feature
title: 'VerbType'
shortdef: 'verb type'
---

POSのレベルで既に助動詞とそれ以外を区別してきたが，タグセットによっては他の区別をさらに設定する．

### Aux: 助動詞 (auxiliary verb)

周辺的な動詞形 (時制，受動など) をつくるのに用いられる．多くの言語では助動詞とそれ以外の用法とで曖昧性が存在するので，同じ動詞形がコンテクストによって異なるタグや素性が付与されることもある．

### Cop: コピュラ動詞

形容詞，名詞もしくは分詞から名詞述語 (nominal predicates) をつくるのに用いられる．言語によっては，コピュラを省略したり，他の手段を用いて名詞述語をつくることがある．コピュラを有する言語においては，それは"to be"や"to become"に相当する意味を持つことが多い．

例: It *is* purple. He just *became* father.

### Mod: 法動詞

法動詞 (modal verb) は，いくつかの言語の文法において伝統的に設定されてきた動詞グループである．法動詞は他の動詞不定形 (不定詞を標示する接続詞を伴う言語と，そうでない言語がある) を項にとり，その動詞に可能性や必然性といった意味を加える.
他にも不定詞を項にとる動詞が存在するが，それらは法動詞とは考えられない (e.g. 句動詞 "to *begin* to do something")．ある言語内で法動詞は閉じたクラスを成すため，種類を数え上げることが可能である．

いくつかの言語 (e.g. トルコ語) では，動詞を法動詞と結合させる代わりに，主動詞の特殊な形式を用いる．

ドイツ語の例:: dürfen (may), können (can), mögen (want/like to),
müssen (must), sollen (shall), wollen (want to), wissen (know to)

チェコ語の例: muset (must), mít (shall, have to), moci (can), smět
(may, be allowed to), umět (know to), chtít (want to)

### Light: 軽動詞・補助動詞

軽動詞もしくは補助動詞は動詞-名詞構文 (verbo-nominal constructions) に用いられ，主たる意味が補部名詞から与えられる．英語の例 _to take a nap,_ では， _take_ が軽動詞である．軽動詞は当該の言語において普通の動詞としても機能することが多い (cf. _to take two dollars_).
軽動詞構文が多用されるような言語 (e.g. ヒンディー語，日本語) だったり，軽動詞としてしか用いられない動詞が存在する場合には，軽動詞専用の素性の値を設定するのが良いだろう．

日本語の例: suru (する)
