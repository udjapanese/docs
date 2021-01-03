---
layout: feature
title: 'PartType'
shortdef: 'particle type'
---

いくつものタグセットで，不変化詞 (particle) のタイプが示されている．ここではIntersetにあるものを提示し，UDによる不変化詞の新たな定義に整合させる．

### Mod: 法不変化詞 (modal particle)

Examples: [bg] май (possibly), нека (let), [cs] ať, kéž, nechť (let)

### Emp: 強調不変化詞 (particle of emphasis)0

Examples: [bg] даже (even)

### Res: 応答不変化詞 (particle of response)

Examples: yes, no

### Inf: 不定詞マーカー (infinitive marker)

これらは従属接続詞 (subordinating conjunctions) だろうか．そうだとすれば，この素性は"conjtype"の値となるだろうか？

Examples: [en] to, [de] zu, [da] at, [sv] att

### Vbp: ドイツ語における分離した動詞の接頭辞

他のゲルマン語には動詞不変化詞に類するものがあり，それらは側置詞 (adposition) や副詞に重複する．これらについては，側置詞/副詞のタグを付与した上で素性`Vbp`を追加するべきだろうか?

  Examples: [de] vor
(in "stellen Sie sich vor")

加えて，複数の言語には疑問不変化詞 (question particles; 疑問文にする i.e. 疑問マーカーとして音声化されるものの一種) や否定不変化詞 (英語の"not", ドイツ語のGerman "nicht"など; 人によってはこれらを副詞と呼ぶ). Intersetにあるこれら2タイプを捉えるため，"prontype"の値として"int"および"neg"を多用してきたが，prontypeが他の品詞に属することから，この方法には不満が残らないわけではない．しかし，素性"PartType"を維持するとすれば，ここでもやはり値"int"と"neg"を追加しておきたい．
