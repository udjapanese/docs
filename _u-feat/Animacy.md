---
layout: feature
title: 'Animacy'
shortdef: 'animacy'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Anim">Anim</a></td>
  <td><a href="#Hum">Hum</a></td>
  <td><a href="#Inan">Inan</a></td>
  <td><a href="#Nhum">Nhum</a></td>
</tr>
</table>


[性 (Gender)]() (アフリカ諸語の名詞クラス) と同じく，有生性 (animacy) は [名詞 (nouns)](u-pos/NOUN) についての特徴である．また，有生性は名詞との一致 (agreement) を標示する他の品詞 ([代名詞 (pronouns)](u-pos/PRON),
[形容詞 (adjectives)](u-pos/ADJ), [限定詞 (determiners)](u-pos/DET), [数詞 (numerals)](u-pos/NUM), [動詞 (verbs)](u-pos/VERB))における屈折素性 (inflectional feature) でもある．
言語によっては，性についてのみ区別するもの，有生性についてのみ区別するものもある．また，性と有生性の両方が文法に何らかの役割を果たす言語もある．
(UD以外のタグセットでは2つの素性を性についての拡張システム (extended system) に包括する場合がある; ただし，UDでは別々のタグ付けを行う)

性と同じように有生性の値 (value) は名詞の意味特徴を表すが，あくまでも近似に過ぎない．これは当該カテゴリの典型的な成員を表すだけである．文法的には有生と扱われるが，意味的には無生物 (inanimate) である名詞も存在する．

以下の表は，ポーランド語の男性 (masculines) 決定詞_który_ "which" の曲用 (declension) について，有生性から3通りの区別 (人間-人間以外の生物-無生物) を与えるものである (上部と下部の行にある太字部分は，中間部の行とは区別される):

|------------------------------------------------------------------------------------------------------------------------------------------------|
| gender            | sg-nom | sg-gen  | sg-dat  | sg-acc      | sg-ins | sg-loc | pl-nom     | pl-gen  | pl-dat | pl-acc      | pl-ins  | pl-loc  |
|------------------------------------------------------------------------------------------------------------------------------------------------|
| animate human     | który  | którego | któremu | którego     | którym | którym | **którzy** | których | którym | **których** | którymi | których |
| animate non-human | który  | którego | któremu | **którego** | którym | którym | **które**  | których | którym | **które**   | którymi | których |
| inanimate         | który  | którego | któremu | **który**   | którym | którym | które      | których | którym | które       | którymi | których |
|------------------------------------------------------------------------------------------------------------------------------------------------|
{: cellpadding="2" cellspacing="0" }

チェコ語の対応するパラダイムでは，2つの値についてのみ区別される:
男性・有生と男性・無生物

|------------------------------------------------------------------------------------------------------------------------------------------------|
| gender            | sg-nom | sg-gen  | sg-dat  | sg-acc      | sg-ins | sg-loc | pl-nom     | pl-gen  | pl-dat | pl-acc      | pl-ins  | pl-loc  |
|------------------------------------------------------------------------------------------------------------------------------------------------|
| animate           | který  | kterého | kterému | **kterého** | kterým | kterém | **kteří**  | kterých | kterým | které       | kterými | kterých |
| inanimate         | který  | kterého | kterému | **který**   | kterým | kterém | **které**  | kterých | kterým | které       | kterými | kterých |
|------------------------------------------------------------------------------------------------------------------------------------------------|
{: cellpadding="2" cellspacing="0" }

より一般的に言えば，言語には有生と無生物 (e.g. チェコ語の男性) を区別するもの，人間と人間以外 (e.g. RyukyuanのYuwan語) を区別するもの，そして人間と人間以外，有生と無生物の3通りの区別を行うもの (e.g. ポーランド語の男性) がある.

### <a name="Anim">`Anim`</a>: 有生物

人間，動物，架空の人物，職名などは，通常は有生物 (animate) である．擬人化された (personified) 場合，ふつう非生物を表す名詞であっても有生の屈折を受ける．また，特定の言語における特定の語は意味的な理由がなくとも，文法上有生物としてふるまうものがある．

### <a name="Inan">`Inan`</a>: 無生物

有生物でない名詞は無生物 (inanimate) である

### <a name="Hum">`Hum`</a>: 人間

有生物のサブセットには，典型的な成員が人間 (human) であり，動物 (animal) でないようなものがある．ここでも例外として，意味的には整合しないが文法上人間のクラスに属するような名詞が存在する．

### <a name="Nhum">`Nhum`</a>: 非人間

人間と非人間 (non-human) についてのみ区別する言語において，この値 (non-human) には無生物 (inanimate) も含まれている．人間・生物，非人間・生物．非人間・無生物の3通りを区別する言語では，この値 (non-human) は非人間・生物を表す場合にのみ用いられる．そして，`Inan`が無生物に対して用いられる．