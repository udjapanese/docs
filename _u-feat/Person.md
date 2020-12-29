---
layout: feature
title: 'Person'
shortdef: 'person'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#0">0</a></td>
  <td><a href="#1">1</a></td>
  <td><a href="#2">2</a></td>
  <td><a href="#3">3</a></td>
  <td><a href="#4">4</a></td>
</tr>
</table>

人称 (person) は，典型的には人称・所有[代名詞pronouns](u-pos/PRON) / [限定詞 (determiners)](u-pos/DET)，および[動詞 (verbs)](u-pos/VERB)の素性を指す．動詞においは，動詞主語の人称を標示する一致素性 (agreement feature) である (バスク語など，言語によっては目的語の人称も標示することがある)．動詞に人称を標示することで代名詞を主語として加える必要がなくなるため，時おり省略されることがある (pro-drop 言語) 

### <a name="0">`0`</a>: ゼロ人称 (zero person)

ゼロ人称は非人間的な陳述 (impersonal statement) であり，フィンランド語やプエブロのケラス語に現れる．(この構文はフィンランド語において特徴的だが，特殊な形態を用いるわけではないので専用の素性を必要とはしない．しかし，ケラス語ではゼロ人称が独自の形態をもつ (Davis 1964: 75)．

### <a name="1">`1`</a>: 1人称 (first person)

単数の1人称 (singular) は話者/筆者のみを指示し，複数の1人称 (plural) は話者と1人以上の人物を含む．いくつかの言語 (e.g. 台湾語) では，複数の1人称が包括的  (inclusive) なものと排他的 (exclusive) なものに区別される: 前者は発話の聞き手 (i.e. _I + you_) を含み，後者は聞き手を含めない (i.e. _I + they_).

#### 例

* [en] _<b>I</b>_, _<b>we</b>_
* [cs] _<b>dělám</b>_ "<b>I</b> do"

### <a name="2">`2`</a>: 2人称 (second person)

単数の2人称は発話/テキストの聞き手 (読者) を指示し，複数の2人称は複数の聞き手を含み，加えて第3者が含まれることもある．

#### 例

* [en] _<b>you</b>_
* [cs] _<b>děláš</b>_ "<b>you</b> do"

### <a name="3">`3`</a>: 3人称 (third person)

3人称は1人かそれより多くの人物を指し，それらは話者でも聞き手でもない．

#### 例

* [en] _<b>he</b>_, _<b>she</b>_, _<b>it</b>_, _<b>they</b>_
* [cs] _<b>dělá</b>_ "<b>he/she/it does</b>"

### <a name="4">`4`</a>: 4人称 (fourth person)

4人称 (fourth person) は，他の3人称の項と形態的に独立したものとして理解される (e.g. ナバホ語)

### 参考文献

* Davis, Irvine. 1964. The language of Santa Ana Pueblo (anthropological papers, no. 69). _Smithsonian Institution Bureau of American Ethnology, Bulletin 191: Anthropological Papers,_ Numbers 68-74, Washington, DC: United States Government Printing Office, 53–190.
