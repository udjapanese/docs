---
layout: feature
title: 'NounClass'
shortdef: 'noun class'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td rowspan="2" style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Bantu1">Bantu1</a></td>
  <td><a href="#Bantu2">Bantu2</a></td>
  <td><a href="#Bantu3">Bantu3</a></td>
  <td><a href="#Bantu4">Bantu4</a></td>
  <td><a href="#Bantu5">Bantu5</a></td>
  <td><a href="#Bantu6">Bantu6</a></td>
  <td><a href="#Bantu7">Bantu7</a></td>
  <td><a href="#Bantu8">Bantu8</a></td>
  <td><a href="#Bantu9">Bantu9</a></td>
  <td><a href="#Bantu10">Bantu10</a></td>
</tr>
<tr>
  <td><a href="#Bantu11">Bantu11</a></td>
  <td><a href="#Bantu12">Bantu12</a></td>
  <td><a href="#Bantu13">Bantu13</a></td>
  <td><a href="#Bantu14">Bantu14</a></td>
  <td><a href="#Bantu15">Bantu15</a></td>
  <td><a href="#Bantu16">Bantu16</a></td>
  <td><a href="#Bantu17">Bantu17</a></td>
  <td><a href="#Bantu18">Bantu18</a></td>
  <td><a href="#Bantu19">Bantu19</a></td>
  <td><a href="#Bantu20">Bantu20</a></td>
</tr>
</table>

`NounClass` は[性 (Gender)]() 及び [有生性 (Animacy)]() に類似している．[名詞 (nouns)](u-pos/NOUN)の語彙カテゴリに含まれ，名詞との一致 (agree) を示す他の品詞 ([代名詞 (pronouns)](u-pos/PRON), [形容詞 (adjectives)](u-pos/ADJ), [限定詞 (determiners)](u-pos/DET), [数詞 (numerals)](u-pos/NUM), [動詞 (verbs)](u-pos/VERB)) の屈折を表すからである.

性と名詞クラスの区別は明瞭ではなく，特定の語族で伝統的に採用された術語法からは区別の条件づけが部分的に与えられる．概して，可能な値 (value) が比較的少なく (大体2-4)，その割り振りがヒトや動物の性別に対応するときは，性 (gender) とみなされる．カテゴリの数が多い (10-20) 語族においては，それは名詞クラスと呼ばれる．また，名詞クラス・性の両方を用いる語族は存在しない．

バントゥー諸語では，名詞クラスは[数 (Number)]() もエンコードする; ゆえに，名詞クラスは名詞の語彙的な屈折素性である．バントゥー語に詳しい人ならば名詞クラスから数を推測できるとはいえ，当該の語には`NounClass`に加えて`Number`もタグ付けされる．ただし，このような語の見出し語 (lemma) は単数形であることが望ましい．

この素性の値の集合は語族 (language family) や語群 (language group) によって変わる．語群内では，言語間において意味の類似したクラスを設定可能である (しかし，同じ語群であっても特定のクラスが統合されたり，消失する場合もある). 素性`NounClass`の値は，語群 (e,g, `Bantu`) における識別子として作用し，クラスの数を与える (バントゥー諸語の研究者の間で標準化されたクラス数の体系が存在する; このような体系は名詞クラスを持つ他の語族でも構築が可能だろう)．

### <a name="Bantu1">`Bantu1`</a>: 単数の人物

これに対応する複数形のクラスは`Bantu2`である．¥

#### 例

* [sw] _<b>mtoto</b>_ “child”

## スワヒリ語における名詞クラスのリスト

([https://en.wikipedia.org/wiki/Noun_class](https://en.wikipedia.org/wiki/Noun_class#Bantu_languages)より)

<table class="wikitable">
<tbody><tr>
<th>クラス数</th>
<th>接頭辞 (Prefix)</th>
<th>典型的な意味</th>
</tr>
<tr>
<td>1</td>
<td><i>m-, mw-, mu-</i></td>
<td>singular: persons</td>
</tr>
<tr>
<td>2</td>
<td><i>wa-, w-</i></td>
<td>plural: persons (クラス1の複数)</td>
</tr>
<tr>
<td>3</td>
<td><i>m-, mw-, mu-</i></td>
<td>singular: plants</td>
</tr>
<tr>
<td>4</td>
<td><i>mi-, my-</i></td>
<td>plural: plants (クラス3の複数)</td>
</tr>
<tr>
<td>5</td>
<td><i>ji-, j-,</i> Ø-</td>
<td>singular: fruits</td>
</tr>
<tr>
<td>6</td>
<td><i>ma-, m-</i></td>
<td>plural: fruits (クラス5, 9, 11, まれに1の複数)</td>
</tr>
<tr>
<td>7</td>
<td><i>ki-, ch-</i></td>
<td>singular: things</td>
</tr>
<tr>
<td>8</td>
<td><i>vi-, vy-</i></td>
<td>plural: things (クラス7の複数)</td>
</tr>
<tr>
<td>9</td>
<td><i>n-, ny-, m-,</i> Ø-</td>
<td>singular: animals, things</td>
</tr>
<tr>
<td>10</td>
<td><i>n-, ny-, m-,</i> Ø-</td>
<td>plural: animals, things (クラス9と11の複数)</td>
</tr>
<tr>
<td>11</td>
<td><i>u-, w-, uw-</i></td>
<td>singular: no clear semantics</td>
</tr>
<tr>
<td>15</td>
<td><i>ku-, kw-</i></td>
<td>verbal nouns</td>
</tr>
<tr>
<td>16</td>
<td><i>pa-</i></td>
<td>locative meanings: close to something</td>
</tr>
<tr>
<td>17</td>
<td><i>ku-</i></td>
<td>indefinite locative or directive meaning</td>
</tr>
<tr>
<td>18</td>
<td><i>mu-, m-</i></td>
<td>locative meanings: inside something</td>
</tr>
</tbody></table>
