---
layout: feature
title: 'PossGender'
shortdef: 'possessor’s gender'
---

所有形容詞・代名詞 (possessive adjectives and pronouns) は2つの異なる性 (gender) を持つことがある: 所有物 (被修飾名詞との性の一致 (agreement)) と所有者 (語彙的な素性であり，固有の性をもつ)．素性`PossGender`所有者の性を表す．今のところサブセットしかコーパスでは観察されないが，議論を簡潔にするため，この素性の可能な値は`Gender`のものと同一だと考えたい．

以下に示すチェコ語の例では，男性 (masculiune) の`PossGender`が接尾辞 <I>-</I><I>ův, -ova, -ovo,</I> を含意し，女性 (feminine) の`PossGender`が
 <I>-</I><I>in, -ina, -ino</I> のいずれかを使用していることを含意する．

### Masc: 男性の所有者 (masculine possessor)

Examples:
[cs]
<span style='color: red'><I>otcův
syn</I></span>
(father's
son; PossGender=Masc|Gender=Masc);
<span style='color: red'><I>otcova
dcera</I></span>
(father's
daughter; PossGender=Masc|Gender=Fem);
<span style='color: red'><I>otcovo
dítě</I></span>
(father's
child; PossGender=Masc|Gender=Neut).

### Fem: 女性の所有者 (feminine possessor)

Examples:
[cs]
<span style='color: red'><I>m</I></span><span style='color: red'><I>atčin
syn</I></span>
(mother's
son; PossGender=Fem|Gender=Masc);
<span style='color: red'><I>matčina
dcera</I></span>
(mother's
daughter; PossGender=Fem|Gender=Fem);
<span style='color: red'><I>matčino
dítě</I></span>
(mother's
child; PossGender=Fem|Gender=Neut).
