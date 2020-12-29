---
layout: feature
title: 'Definite'
shortdef: 'definiteness or state'
redirect_from: "u/feat/Definiteness.html"
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Com">Com</a></td>
  <td><a href="#Cons">Cons</a></td>
  <td><a href="#Def">Def</a></td>
  <td><a href="#Ind">Ind</a></td>
  <td><a href="#Spec">Spec</a></td>
</tr>
</table>

定性 (definiteness) とは，典型的に名詞，形容詞と冠詞に関する特徴を指す．その値は，既知で具体的なものか，一般的か，未知のものかによって区別される．定性は定/不定[冠詞 (articles)](u-pos/DET)もしくは，[名詞 (nouns)](u-pos/NOUN), [形容詞 (adjectives)](u-pos/ADJ)に標示される. アラビア語において，定性は"state"とも呼ばれる.

### <a name="Ind">`Ind`</a>: 不定 (indefinite)

`Spec`が区別される言語において，値`Ind`は非特定的・不定として解釈される (i.e. “any (one) stick”)．

#### 例

* [en] _<b>a</b> dog_
* [sv] _<b>en hund</b>_ “a dog”

### <a name="Spec">`Spec`</a>: 特定的な不定 (specific indefinite)

特定的な不定 (e.g. “a certain stick”) はラコタ語などに生起する．特定的な不定が用いられる言語において，値`Ind`は非特定的な不定として解釈される (i.e. “any (one) stick”)．

### <a name="Def">`Def`</a>: 定 (definite)

#### 例

* [en] _<b>the</b> dog_
* [sv] _<b>hunden</b>_ “the dog”

### <a name="Cons">`Cons`</a>: 連語形 (construct state / reduced definiteness)

[連語形 (construct state)](http://en.wikipedia.org/wiki/Status_constructus) はアラビア語で用いられる．2つの名詞が所有関係 (genitive relation) にあるとき，先頭の名詞 ("nomen regens") は"reduced definiteness"を有し，後続の名詞は属格であり定か不定である．Reduced formは定の形態素 (冠詞) および不定の形態素 (nunation) を持たない．

UD v1において，この値は`Red`と呼ばれた．UD v2では`Cons`とリネームされた．

#### 例

* [ar] indefinite state:
  حلوَةٌ
  _ḥulwatun_ "a sweet";
  definite state:
  الحلوَةُ
  _al-ḥulwatu_ "the sweet";
  construct state:
  <b>حلوَةُ </b>
  _<b>ḥulwatu</b>_
  "sweet of".

### <a name="Com">`Com`</a>: complex

Used in <A
HREF="http://books.google.cz/books?id=rs3hzfgj3hoC&amp;pg=PA131&amp;lpg=PA131&amp;dq=arabic+improper+annexation&amp;source=bl&amp;ots=d6gGCpprOX&amp;sig=3G6YkRZsIy_EL0OCEh7_V7qqnlE&amp;hl=cs&amp;ei=ZasDTuLhGc_vsgaLlcyeDg&amp;sa=X&amp;oi=book_result&amp;ct=result&amp;resnum=2&amp;ved=0CB4Q6AEwAQ#v=onepage&amp;q=arabic%20improper%20annexation&amp;f=false">improper
annexation</A> in Arabic. 上記の所有構文 (genitive construction) は主に2つの名詞から構成される (first reduced, second genitive). これは，アラビア語においてproper annexation もしくは iḍāfaと呼ばれる. If the first member is an
adjective or adjectivally used participle and the second member is a
definite noun, the construction is called improper annexation or false
iḍāfa.  The result is a compound adjective that is usually used as an
attributive adjunct and thus must agree in definiteness with the noun
it modifies. Its first part (the adjective or participle) may get
again the definite article. Although it may look the same as the form
for the definite state, it is assigned a special value of _complex_
state to reflect the different origin. See also <A
HREF="http://ufal.mff.cuni.cz/padt/PADT_1.0/docs/papers/2004-nemlar-padt.pdf">Hajič
et al.</A> page 3.

#### 例:

* [ar] مُخْتَلِفٌ  _muxtalifun_ "different/various" (active participle,
  Form VIII); نَوْعٌ ج أنْوَاعٌ _nawˀun ja anwāˀun_ "kind"; مُخْتَلِفُ
  الأنْوَاعِ _muxtalifu al-anwāˀi_ "of various kinds" (false iḍāfa);
  مَشَاكِلُ مُخْتَلِفَةُ الأنْوَاعِ _mašākilu muxtalifatu al-anwāˀi_
  "problems of various kinds"; اَلْمَشَاكِلُ <b>الْمُخْتَلِفَةُ</b>
  الأنْوَاعِ _al-mašākilu <b>al-muxtalifatu</b> al-anwāˀi_ "the
  problems of various kinds".
