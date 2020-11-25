---
layout: relation
title: 'discourse'
shortdef: 'discourse element'
udver: '2'
---

関係`discourse`は [interjections](u-pos/INTJ) や 談話の [particles](u-pos/PART) を示すのに用いられる (表現に関わるものを除き，文構造と結び付けられることはない). UDではPennツリーバンクがINTJと認定するものに対するガイドラインに従う．  この定義では，次のものが含まれる: 間投詞 (interjection; *oh*, *uh-huh*, *Welcome*)，フィラー (*um*, *ah*)，談話標識 (discourse markers; *well*, *like*, *actually* しかし，*you know*は含まない)

これらの談話要素は，関連性が最も高い節の主辞へ付加される．この理由から，談話要素は動詞の依存部でないのにも関わらず，必須でない節の依存部とグループ化される．

~~~ sdparse
Iguazu is in Argentina :)
discourse(is-2, :)-5)
~~~
