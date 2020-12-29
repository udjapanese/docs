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

### Vbp: separated verb prefix in German

他のゲルマン語には動詞不変化詞に類するものがあり，それらは側置詞 (adposition) や副詞と重複する．これらには側置詞/副詞としてタグ付けした上で素性`Vbp`を追加するべきだろうか?
  Examples: [de] vor
(in "stellen Sie sich vor")

加えて，複数の言語には疑問不変化詞 (question particles; 文を疑問にする i.e. 疑問マーカーとして音声化されるものの一種) や否定不変化詞 (英語の"not", ドイツ語のGerman "nicht"など; 人によってはこれらを副詞と呼ぶ). Intersetにあるこれらの2タイプを捉えるため，"prontype"の値"int"および"neg"を多用してきたが，prontypeが他の品詞に属することから，この方法には不満が残らないわけではない．素性"PartType"を維持するとすれば，ここでも値"int"と"neg"を追加しておきたい．
