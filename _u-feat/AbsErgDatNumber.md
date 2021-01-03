---
layout: feature
title: 'AbsErgDatNumber'
shortdef: 'number agreement with absolutive/ergative/dative argument'
---

## Number[abs], Number[erg], Number[dat]

印欧諸語の多くで，定動詞 (finite verbs) は人称 (person) と[数 (number)](u-feat/Number) に関して主語と一致 (agree) する．バスク語 (<a href="http://en.wikipedia.org/wiki/Polypersonal_agreement">複数人称言語 (polypersonal language)</a>) では，特定の動詞が最大3つまでの項 (arguments) との一致を標示する: 絶対[格 (case)](u-feat/Case)，能格 (ergative)，与格 (dative).

よって，_dakarkiogu “we bring it to him/her” _の_akar_は語幹 (stem; _ekarri_ = “bring”) を表し，_d_は“it”を表す (絶対格項は他動詞の直接目的語). そして，_ki_は与格，_o_は“he”，_gu_は“we”を表す (能格項は他動詞主語).

* `Number[abs]` は動詞の絶対格項の数 (number) を表す．Interset 2.041で対応する素性は`absnumber`と呼ばれる．
* `Number[erg]` は動詞の能格項の数を表す．Interset 2.041で対応する素性は`ergnumber`である．
* `Number[dat]` は動詞の与格項の数を表す．Interset 2.041で対応する素性は`datnumber`である．

`Number[abs]`ではなく，単に`Number`を用いたくなるかもしれないが，それには問題が2点存在する (少なくともバスク語において). まず，絶対格項は常に主語となるわけではない．他動詞では絶対格項が目的語となるため，主格-対格言語 (nominative-accusative languages) との並行性を見出す根拠は薄い．
次に，これがより重要であるのだが，バスク語のいつくかの定動詞では名詞の屈折 (inflection) に対応する形態素を備えている．よって，それらの形式は絶対格項について人称-数の一致を示すと同時に，名詞の屈折 (格，数など)も反映している.
例: _dena_ (`Number=Sing|Number[abs]=Sing`),
_dituena_ (`Number=Sing|Number[abs]=Plur|Number[erg]=Sing`),
_dugunak_ (`Number=Plur|Number[abs]=Sing|Number[erg]=Plur`),
_direnak_ (`Number=Plur|Number[abs]=Plur`).
よって，素性`Number`に対しては名詞の屈折素性，`Number[abs]`に関しては一致素性という区分を保持しておく．
また，素性間の衝突がないとはいえ，`Person[abs]`および`Polite[abs]`についても定義しておく．ただし，これらの素性は`Person[erg]`, `Polite[erg]`, `Person[dat]`および`Polite[dat]`と同じような位置付けだと考えた方がいい．

### Sing: 単数

例: [eu] _<b>d</b>akarki<b>o</b>gu_ `Number[abs]=Sing|Number[dat]=Sing`

### Plur: 複数

例: [eu] _dakarkio<b>gu</b>_ `Number[erg]=Plur`
