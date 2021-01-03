---
layout: feature
title: 'AbsErgDatPolite'
shortdef: 'politeness agreement with absolutive/ergative/dative argument'
---

## Polite[abs], Polite[erg], Polite[dat]

印欧諸語の多くで，定動詞 (finite verbs) は人称 (person) と数 (number) が主語と一致 (agree) する;
二人称主語は，レジスターの丁寧さ (politeness) にも影響を及ぼす.
バスク語 (<a href="http://en.wikipedia.org/wiki/Polypersonal_agreement">複数人称言語 (polypersonal language)</a>) では，特定の動詞が最大3つの項 (arguments) との一致を標示する: 絶対[格](u-feat/Case)，能格 (ergative)，与格 (dative).
よって，_dakarkiogu_ “we bring it to him/her” の_akar_は語幹 (stem; _ekarri_ = “bring”) を表し，_d_は“it”を表す (絶対格項は他動詞の直接目的語). そして，_ki_は与格，_o_は“he”，_gu_は“we”を表す (能格項は他動詞主語).

* `Polite[abs]` は，動詞の絶対格項の丁寧さを表す．Interset 2.041で対応する素性は`abspoliteness`と呼ばれる．
* `Polite[erg]` は，動詞の能格項の丁寧さを表す，Interset 2.041で対応する素性は`ergpoliteness`と呼ばれる．
* `Polite[dat]` は，動詞の与格項の丁寧さを表す．Interset 2.041で対応する素性は`datpoliteness`と呼ばれる．

`Polite[abs]`の代わりに，単に`Polite`を使いたくなるかもしれないが，これには問題が2つ存在する (少なくともバスク語で)．
まず，絶対格項は常に主語となるわけではない．他動詞では絶対格項が目的語となるため，主格-対格言語 (nominative-accusative languages) との並行性を見出す根拠は薄い．次に，`Number[abs]` (`Number`と`Number[abs]`の両方が一つの語に生起可能) の使用が不可避であるため，両方の素性が同じ一致レイヤーに属すことを示すためにも`Polite[abs]`を用い続ける．

### Inf: インフォーマル

例: [eu] _ezan, ezak_ `Polite[erg]=Inf`

### Pol: 丁寧，フォーマル

例: [eu] _ezazu_ `Polite[erg]=Pol` (丁寧さに関して中立的な形式は_ezazue_)
