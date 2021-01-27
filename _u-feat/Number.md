---
layout: feature
title: 'Number'
shortdef: 'number'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Coll">Coll</a></td>
  <td><a href="#Count">Count</a></td>
  <td><a href="#Dual">Dual</a></td>
  <td><a href="#Grpa">Grpa</a></td>
  <td><a href="#Grpl">Grpl</a></td>
  <td><a href="#Inv">Inv</a></td>
  <td><a href="#Pauc">Pauc</a></td>
  <td><a href="#Plur">Plur</a></td>
  <td><a href="#Ptan">Ptan</a></td>
  <td><a href="#Sing">Sing</a></td>
  <td><a href="#Tri">Tri</a></td>
</tr>
</table>

`Number` は通常，[名詞 (nouns)](u-pos/NOUN) の屈折素性である．言語によっては，他の品詞 ([代名詞 (pronouns)](u-pos/PRON),
[形容詞 (adjectives)](u-pos/ADJ), [限定詞 (determiners)](u-pos/DET), [数詞 (numerals)](u-pos/NUM), [動詞 (verbs)](u-pos/VERB))も数に関して名詞との一致 (agreement) を標示することがある．

### <a name="Sing">`Sing`</a>: 単数 (singular number)

人物・動物・事物を1つ示す単数名詞.

#### 例

* [en] _<b>car</b>_

### <a name="Plur">`Plur`</a>: 複数 (plural number)

人物・動物・事物を複数示す複数名詞.

#### 例

* [en] _<b>cars</b>_

### <a name="Dual">`Dual`</a>: 双数 (dual number)

人物・動物・事物を2つ示す双数名詞

#### 例

* [sl] singular _glas_ "voice", dual _<b>glasova</b>_ "voices", plural
  _glasovi_ "voices"
* [ar] singular سَنَةٌ _sanatun_ "year", dual <b>سَنَتَانِ
  _sanatāni_</b> "years", plural سِنُونَ _sinūna_ "years".

### <a name="Tri">`Tri`</a>: 三数 (trial number)

三数代名詞 (trial pronoun denotes) は人物・動物・事物を3つ示す．三数代名詞
はオーストロネシア諸語のいくつかに現れる．

### <a name="Pauc">`Pauc`</a>: 少数 (paucal number)

少数名詞 (paucal noun) は“少数の”人物・動物・事物を表す．

### <a name="Grpa">`Grpa`</a>: 複数の少数 (greater paucal number)

複数少数名詞 (greater paucal noun) は "少数ではないが，多数でない" 人物・動物・事物を指す．
オーストロネシア言語のスルスルンガ語 (Sursurunga) に生起する．

### <a name="Grpl">`Grpl`</a>: 大数 (greater plural number0
大数名詞 (greater plural noun) は “多数の，可能なもの全ての” 人物・動物・事物を指す．
その正確な意味は言語によって多岐にわたる．

### <a name="Inv">`Inv`</a>: 逆数 (inverse number)

逆数は特定の名詞の数がデフォルトでないことを表す． (名詞よっては単数がデフォルトであったり，複数がデフォルトであったりする.)
逆数はキオワ語 (Kiowa) に生起する．

### <a name="Count">`Count`</a> 加算複数 (count plural)

加算複数はブルガリア語やマケドニア語で確認され，"加算形"，"加算複数"，"定量複数" のように，様々な呼び方がある (Sussex and Cubberley 2006, p. 324).
数詞 (numeral) に後続する場合，これは名詞の特殊な複数形となる．
(この形式はスラブ祖語の双数形に起源を持つが，`Number=Dual`とは標示されない．
なぜなら，(1)双数はブルガリア語で消失した (2)その形式が2という数と意味的な関連性を持たなくなったからである．)

#### 例

* [bg] _tri <b>stola</b>_ “three chairs” vs. _stolove_ “chairs”

### <a name="Ptan">`Ptan`</a>: 絶対複数 (plurale tantum)

名詞によっては，例えそれが1つの事物 (意味的に単数) しか表していなくても複数形でしか生起しないようなものがある;
いくつかのタグセットでは．この区別を標示する．
文法的には複数形のようにふるまうので，`Plur`はバックオフの値をとる; しかし，性 (gender) も標示する言語については，単数形の不在が性について不明であること意味する場合がある．チェコ語において加算名詞が絶対複数を表す場合，このような特別なタイプの数詞が用いられる ([NumType]() = Sets)．

#### 例

* [en] _<b>scissors, pants</b>_
* [cs] _<b>nůžky, kalhoty</b>_

### <a name="Coll">`Coll`</a>: 集合名詞，質量名詞，絶対単数 (collective / mass / singulare tantum)

集合名詞，質量名詞，絶対単数は単数形の特別例である．これらは文法的単数が事物の集合 (i.e. 意味的に複数) を表す場合に適用される．理論的には複数形を形成できるだろうが，意味的に単数を表すのは難しい．
ただし，複数形は"いくつかの種類の"，"いくつかのパッケージの"といった意味を表すことがある．


#### 例

* [cs] _<b>lidstvo</b>_ "mankind"

### 参考文献

* Sussex, Roland and Cubberley, Paul. 2006. _The Slavic Languages._ Cambridge University Press.

