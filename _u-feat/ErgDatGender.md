---
layout: feature
title: 'ErgDatGender'
shortdef: 'gender agreement with ergative/dative argument'
---

## Gender[erg], Gender[dat]

多くの印欧語では，定動詞 (finite verb) は人称 (person) と数 (number) に関して主語と一致 (agree) する．バスク語 (a <a href="http://en.wikipedia.org/wiki/Polypersonal_agreement">polypersonal language</a>) では，特定の動詞が最大3つの項との一致を明示的に表す: 絶対 [格](u-feat/Case) (absolute case)，能格 (ergative case)，与格 (dative).
よって，_dakarkiogu_ “we bring it to him/her” において，_akar_は語幹 (_ekarri_ = “bring”) であり，_d_ は “it” を表し (絶対格項は他動詞の直接目的語)，_ki_は与格を表し，_o_は “he” を表す．そして，_gu_は “we” を示している (能格項は他動詞の主語).

インフォーマルな使用域 (register) では，男性 (masculine) と女性 (feminine) について独立した形式を持つ．しかし，他の場合では[性 (gender)](u-feat/Gender) が区別されない．

* `Gender[erg]` は動詞の能格項の性を示す．Interset 2.041 で対応する素性は `erggender` と呼ばれる．
* `Gender[dat]` は動詞の与格項の性を示す．Interset 2.041 で対応する素性は`datgender` と呼ばれる.

### Masc: 男性

例: [eu] _ukan <b>ezak</b>_ “have it” `Gender[erg]=Masc|Number[abs]=Sing|Number[erg]=Sing|Person[abs]=3|Person[erg]=2|Polite[erg]=Inf`
(男性に呼びかける命令法 (imprerative))

### Fem: 女性

例: [eu] _ukan <b>ezan</b>_ “have it” `Gender[erg]=Fem|Number[abs]=Sing|Number[erg]=Sing|Person[abs]=3|Person[erg]=2|Polite[erg]=Inf`
(女性に呼びかける命令法)