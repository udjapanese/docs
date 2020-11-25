---
layout: relation
title: 'clf'
shortdef: 'classifier'
udver: '2'
---
`clf` (類別詞 (classifier) ) は，特定の統語環境において名詞に付随する語を指す．最も標準的な使用法は数の類別詞 (numeral classifiers) であり，対象物を数えるために用いられる．通常，類別詞は名詞におけるある種の概念分類を反映しており，それは原理的に指示物 (referents) の特性に基づいている．
類別詞は語源的に名詞であるため，それらは名詞としても独立に用いられる．しかし，類別詞として用いた場合は，その意味が希薄となる．
大抵の場合で，類別詞に対してはNOUNが最も適したUPOSとなるが，類別詞としての特別なステータスを示すための素性を与えたくなるかもしれない．(類別詞に対する普遍的な素性は存在しないが，`NounType=Clf`が適しているだろう.)
関数`clf`は，類別詞の文法化した体系を備える言語に対して利用することを志向している．そのような傾向が最も強い言語はアジア諸語である．
主要な類別詞だけでなく、"massifiers"と呼ばれる，類別詞に類似した数の数え方をする他の語が存在する．，
これらには容器 ("cup", "box") や単位 ("mouth", "inch") が含まれ，中国語の一袋米 [one bag rice] ‘a bag of rice’における袋 ‘bag’ といったものが該当する.
類別詞を用いる言語においては，これらの語を類別詞として分析することが最も適切である．
他の言語では数を数える際に単位 (units) を用いるが，英語といった言語に対しては`clf`は用いられず，標準的な名詞句の関係が依然として用いられる (英語を含め，多くの事例で文法化の兆候がみられるとしても)
英語の例については，本ページの最後を参照されたい．
See the examples for English at the end.

以下，関東語/普通話中国語の例である:

* 三个学生 (三個學生) sān gè xuéshēng = “three students”, literally “three [human-classifier] student”
* 三棵树 (三棵樹) sān kē shù = “three trees”, literally “three [tree-classifier] tree”
* 三只鸟 (三隻鳥) sān zhī niǎo = “three birds”, literally “three [bird-classifier] bird”
* 三条河 (三條河) sān tiáo hé = “three rivers”, literally “three [long-wavy-classifier] river”

統語的には，この類別詞は名詞ではなく数詞とグループ<!--動詞group-->を形成する．ゆえに，新たな関係`clf`を用いて，類別詞は数詞 (所有格表現) の機能的依存部として扱われる．(これはGreenbergの普遍性の一種であり，他の全ての事例にも該当する．いくつかの例外は Aikhenvald (2000: 105) の _Classifiers_ (OUP) で言及されているが，この文献で取り上げられる言語において，いわゆる主辞名詞は属格形で顕著にみられる.)

<div class="sd-parse">
sān gè xuéshēng \n three clf student
nummod(xuéshēng, sān)
clf(sān, gè)
</div>

ときおり，類別詞が指示詞と名詞の間に挿入されることがある (数詞や名詞のかわりに) [zh]:

<div class="sd-parse">
乘坐 這 輛 巴士 \n Chéngzuò zhè liàng bāshì \n Take this CLF bus
obj(乘坐, 巴士)
det(巴士, 這)
clf(這, 輛)
obj(Chéngzuò, bāshì)
det(bāshì, zhè)
clf(zhè, liàng)
obj(Take, bus)
det(bus, this)
clf(this, CLF)
</div>

類別詞を示す語は様々な構文でも生起するが，個別言語における類別詞とUDで提案されたものを区別することが重要である．ここで，中国語の類別詞の例についてさらに検討したい．

名詞が生起せず，数や類別詞だけが生起する場合がある．このとき，類別詞が欠けた名詞の役割を埋め，類別詞を主辞へ昇格 (promote) させる．よって， 我 買 兩 本 “I am buying two” は “I am buying two [books-CLF]” とみなされる.

<div class="sd-parse">
我 買 兩 本 \n I buy two CLF
obj(買, 本)
nummod(本, 兩)
</div>

中国語を含むいくつかの言語では類別詞が数を伴わずに生起することがあり，ある種の決定詞の機能を表すことが頻繁にある．そのような類別詞の使用においては`det`が用いられる．例えば広東語の‘She bought a/the book’は次のように分析される:

<div class="sd-parse">
佢 買 咗 本 書 \n keoi maai zo bun syu \n 3sg buy PERF CLF book
obj(買, 書)
det(書, 本)
</div>

高度に文法化した類別詞の体系を備えない言語においては，事物が ("massifiers" を伴って) グループとして数えられる場合であっても，標準の名詞修飾関係が用いられる．例えば，英語では:

<div class="sd-parse">
three cups of rolled oats
nummod(cups, three)
case(oats, of)
amod(oats, rolled)
nmod(cups, oats)
</div>

<div class="sd-parse">
three cups rolled oats
nummod(cups, three)
amod(oats, rolled)
nmod(cups, oats)
</div>
