---
layout: feature
title: 'PossNumber'
shortdef: 'possessor’s number'
---

所有形 (possessives) は2つの異なる数 (number) を持つ: 所有物 (被修飾名詞との数の一致 (agreement)) と所有者．素性`PossNumber`は所有者の数を捉える．今のところサブセットだけがコーパスで観察されるが，議論の簡潔性のため，この素性の値は`Number`の値と同一だと考えたい．

### Sing: 単数の所有者 (singular possessor)

Examples:
[en]
<span style='color: red'><I>my,
his</I></span><span style='color: red'><I>,
her, its</I></span>;
[cs]
<span style='color: red'><I>můj</I></span><I>
pes</I>
(my
dog; PossNumber=Sing|Number=Sing); <span style='color: red'><I>mí</I></span><I>
psi</I>
(my
dogs; PossNumber=Sing|Number=Plur).

### Plur: 複数の所有者 (plural possessor)

Examples:
[en]
<span style='color: red'><I>our,
t</I></span><span style='color: red'><I>heir</I></span>;
[cs]
<span style='color: red'><I>náš</I></span><I>
pes</I>
(our
dog; PossNumber=Plur|Number=Sing); <span style='color: red'><I>naši</I></span><I>
psi</I>
(our
dogs; PossNumber=Plur|Number=Plur).
