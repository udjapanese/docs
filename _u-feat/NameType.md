---
layout: feature
title: 'NameType'
shortdef: 'type of named entity'
---

この素性は名称のある存在物を分類する (token-based, no nesting of entities etc.)． この素性は主に[cs-pos/PROPN]()タグに適用される: 複数の語から成る外国語の名称については，[adjectives](cs-pos/ADJ)もこの素性を持つ <!--Czechがチェコ語なのか，"Czech"という語を指すのかが分からない(they preserve the `ADJ` tag but at the same time they would not exist in Czech
otherwise than in the named entity).-->

### `Geo`: 地理的な名称

都市，国家，河川，山といったものの名称

#### 例

* _<b>Praha</b>&nbsp;_ “Prague”, _<b>Kostelec</b> nad Černými lesy&nbsp;_, _<b>Německo</b>&nbsp;_ “Germany”

### `Prs`: 人名

この値は，名 (given name) か姓かどうか判断できないものの，人名だと判断できるような名称に対して用いられる．

### `Giv`: 名 (given name of person)

名 (ファミリーネームでない) を表す．これは，欧米人のファーストネームや中国語における (3つの) 音節の後ろから2つに相当する.

### `Sur`: 姓/ファミリーネーム

ファミリーネーム (姓) を表す．これは，欧米人のラストネームや中国語における (3つの) 音節の先頭に相当する.

### `Nat`: 国籍

特定の国家もしくは，特定の領地の住人を示す

#### 例

* _<b>Čech</b>&nbsp;_ “Czech”, _<b>Němec</b>&nbsp;_ “German”, _<b>Pražan</b>&nbsp;_ “Praguer”

### `Com`: 会社，組織

### `Pro`: 製品

### `Oth`: その他

競技場，ゲリラ拠点，イベントなどの名称