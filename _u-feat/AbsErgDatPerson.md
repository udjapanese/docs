---
layout: feature
title: 'AbsErgDatPerson'
shortdef: 'person agreement with absolutive/ergative/dative argument'
---

## Person[abs], Person[erg], Person[dat]

多くの印欧諸語において，定動詞は[人称 (person)](u-feat/Person)，数 (number) に関して主語と一致 (agree) する．バスク語 (<a href="http://en.wikipedia.org/wiki/Polypersonal_agreement">複数人称言語 (polypersonal language)</a>) では，特定の動詞が3つまでの項 (arguments) との一致を標示する: 絶対[格](u-feat/Case)，能格 (ergative)，与格 (dative).
よって，_dakarkiogu_ “we bring it to him/her” の_akar_は語幹 (stem; _ekarri_ = “bring”) を表し，_d_は“it”を表す (絶対格項は他動詞の直接目的語). そして，_ki_は与格，_o_は“he”，_gu_は“we”を表す (能格項は他動詞主語).

* `Person[abs]` は動詞の絶対格項の人称を表す．is the person of the absolutive argument of the verb. Interset 2.041で対応する素性は`absperson`と呼ばれる．
* `Person[erg]` は動詞の能格項の人称を表す．Interset 2.041で対応する素性は`ergperson`である．
* `Person[dat]` は動詞の与格項の人称を表す．Interset 2.041で対応する素性は`datperson`である．

`Person[abs]`ではなく，単に`Person`を用いたくなるかもしれないが，それには問題が2点存在する (少なくともバスク語において)．まず，絶対格項は常に主語となるわけではない．他動詞では絶対格項が目的語となるため，主格-対格言語 (nominative-accusative languages) との並行性を見出す根拠は薄い．
また，`Number[abs]` (`Number`と`Number[abs]`の両方が一つの語に生起可能) の使用が不可避であるため，両方の素性が同じ一致レイヤーに属することを示すためにも`Person[abs]`を用い続ける．

### 1: 1人称

例: [eu] _dakarkio<b>gu</b>_ `Person[erg]=1`

### 2: 2人称

例: [eu] _dakarkio<b>zu</b>_ `Person[erg]=2`

### 3: 3人称

例: [eu] _<b>d</b>akarki<b>o</b>gu_ `Person[abs]=3|Person[dat]=3`
