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

定性 (definiteness) とは，典型的に名詞，形容詞および冠詞に関する特徴を指す．その値は，既知で具体的なものか，一般的か，未知のものかによって区別される．定性は，定/不定[冠詞 (articles)](u-pos/DET)もしくは，[名詞 (nouns)](u-pos/NOUN), [形容詞 (adjectives)](u-pos/ADJ)で標示される. アラビア語において，定性は"state"とも呼ばれる.

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

[連語形 (construct state)](http://en.wikipedia.org/wiki/Status_constructus) はアラビア語で用いられる．2つの名詞が所有関係 (genitive relation) にあるとき，先頭の名詞 ("nomen regens") は"縮約定性 (reduced definiteness)"を有し，後続の名詞は属格となり，それは定か不定のどちらかである．縮約形 (reduced form) は定の形態素 (冠詞) および不定の形態素 (nunation) を持たない．

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

### <a name="Com">`Com`</a>: 複雑な定性 (complex)

このタイプの定性はアラビア語における<A
HREF="http://books.google.cz/books?id=rs3hzfgj3hoC&amp;pg=PA131&amp;lpg=PA131&amp;dq=arabic+improper+annexation&amp;source=bl&amp;ots=d6gGCpprOX&amp;sig=3G6YkRZsIy_EL0OCEh7_V7qqnlE&amp;hl=cs&amp;ei=ZasDTuLhGc_vsgaLlcyeDg&amp;sa=X&amp;oi=book_result&amp;ct=result&amp;resnum=2&amp;ved=0CB4Q6AEwAQ#v=onepage&amp;q=arabic%20improper%20annexation&amp;f=false">適正でない併合 (improper annexation)</A>に用いられる．上記の所有構文 (genitive construction) は主に2つの名詞から構成される (first reduced, second genitive)．これは，アラビア語において適正な併合 (proper annexation) もしくは iḍāfaと呼ばれる. 先頭要素が形容詞もしくは形容詞的に用いられた分詞であり，かつ2番目の要素が定名詞である場合，この構文は "適正でない併合 (improper annexation)" もしくは "false iḍāfa" と呼ばれる．その結果．この構文は複合形容詞 (compound adjective) となり，限定付加詞 (attributive adjunct) として用いられる．そして，この構文は定性に関して被修飾名詞と一致 (agree) しなければならない．また，先頭要素 (形容詞もしくは分詞) が定冠詞をとる場合では，これが定名詞と同じ形式であるように見えるため，派生元が異なることを示すためにも_複雑な_定性の値が付与される．詳細は<A
HREF="http://ufal.mff.cuni.cz/padt/PADT_1.0/docs/papers/2004-nemlar-padt.pdf">Hajič
et al.</A> p.3 についても参照されたい．

#### 例:

* [ar] مُخْتَلِفٌ  _muxtalifun_ "different/various" (能動分詞,
  Form VIII); نَوْعٌ ج أنْوَاعٌ _nawˀun ja anwāˀun_ "kind"; مُخْتَلِفُ
  الأنْوَاعِ _muxtalifu al-anwāˀi_ "of various kinds" (false iḍāfa);
  مَشَاكِلُ مُخْتَلِفَةُ الأنْوَاعِ _mašākilu muxtalifatu al-anwāˀi_
  "problems of various kinds"; اَلْمَشَاكِلُ <b>الْمُخْتَلِفَةُ</b>
  الأنْوَاعِ _al-mašākilu <b>al-muxtalifatu</b> al-anwāˀi_ "the
  problems of various kinds".
