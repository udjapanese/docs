---
layout: feature
title: 'Tense'
shortdef: 'tense'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Fut">Fut</a></td>
  <td><a href="#Imp">Imp</a></td>
  <td><a href="#Past">Past</a></td>
  <td><a href="#Pqp">Pqp</a></td>
  <td><a href="#Pres">Pres</a></td>
</tr>
</table>

時制 (tense) は典型的には[動詞 (verbs)](u-pos/VERB)の素性であるが，他の品詞 ([名詞 (nouns)](u-pos/NOUN), [形容詞 (adjectives)](u-pos/ADJ), [副詞 (adverbs)](u-pos/ADV)) も，分詞 (participles) といった境界線上にある語が動詞か他の品詞に属するかによって時制を持つ場合がある．

時制は当該行為が行われた/行う/行われる時間を指定する．時間は特定の参照点 (reference point) から決定され，発話時点を指す場合もあれば，コンテクストに依存する場合もある．言語によっては (e.g. 英語)，時制のいくつかが時制と[アスペスト (aspect)](Aspect)との組み合わせから表現される．他の言語 (e.g. チェコ語) ではアスペクトと時制が完全には独立しないものの，それらが分離することがある.
ここで行うのは単一の語に適用される素性の定義についてである．時制が迂言的に表され (2以上の動詞，すなわち助動詞 (auxiliary verb) の直接法 (indicative) + 主動詞の分詞 から)，かつ特定の時制に特有な語が存在しない場合，この素性は時制を明示的に表さないだろう．例えば，[en] _I <b>had been</b> there_ は過去完了 (大過去) の時制をもち，これは助動詞の単純過去_to have_と主動詞_to be_の過去分詞から成る．そのとき，助動詞 `VerbForm=Fin|Mood=Ind|Tense=Past` とタグ付けされ，分詞は `VerbForm=Part|Tense=Past` とタグ付けされる; 両者はともに`Tense=Pqp`を持たない．一方，ポルトガル語は大過去を1語によって形成することができ，_estivera_といったものは `VerbForm=Fin|Mood=Ind|Tense=Pqp` としてタグ付けされるだろう．


### <a name="Past">`Past`</a>: 過去時制/過去形/アオリスト

過去時制は行為が参照点よりも前に発生したことを示す．典型例において参照点は発話時点であり，過去事象は話者がそれについて話す以前に起きたものである．しかし，`Tense=Past`は過去分詞と他の分詞を区別するのにも用いられ，また過去の副動詞 (past converb) を他から区別するためにも使われる;これらの事例では，参照点自体は発話時点と比べて過去かもしれないし未来かもしれない．
例えば，チェコ語の文_spatřivše vojáky, velmi se ulekli_ “having seen the soldiers, they got very scared” 内にある副動詞 _spatřivše_ “having seen” は「恐れを抱く」という事象よりも前に起こったことを示す．

当該事象の発生が発話時点に先行するとはいえ，その情報は副動詞自体にはエンコードされていない．“getting scared”という事象が過去時制で表されることから生ずるのである．

定動詞のうち，英語の単純過去形が`Tense=Past`の例に該当する．これは，ドイツ語ではPräteritumに相当し，トルコ語ではnon-narrative pastに相当する．また，ブルガリア語ではアスペクトに関して中立的である過去時制 (アオリスト) に相当し，未完了動詞・完了動詞のどちらでも自由に用いることができる (未完了の欄も参照されたい)．

#### 例

* [en] _he <b>went</b> home_
* [en] _he has <b>gone</b> home_



### <a name="Pres">`Pres`</a>: 現在/非過去時制

現在時制は行為が特定の参照点において進行中であること (もしくは状態) を示す; また，現在時制は習慣的に発生する事象を表すこともできる．
典型的には，参照点は発話時点である; しかし，`Tense=Pres`は他の分詞 (participle) から現在分詞を区別するのに用いられ，現在の副動詞 (converbs) から他を区別するためにも用いられる．これらの事例では，参照点が発話時点に比べて過去あるいは未来であることがある．例えば，英語の現在分詞は過去進行時制 (past progressive tense) を形成するのに用いられるだろう:
_he was watching TV when I arrived._

同様に，いくつかのスラブ語 (e.g. チェコ語) では未来時制 (future tense) を持つが，現在形が未来の意味を表すような動詞のサブセットも存在する．

#### 例

* [en] _he <b>goes</b> home_
* [en] _he was <b>going</b> home_



### <a name="Fut">`Fut`</a>: 未来時制 (future tense)

未来時制は参照点よりも後に起こる行為を指す: 典型的に参照点は発話時点である．

#### 例

* [es] _<b>irá</b> a la casa_ “he/she/it will go home”



### <a name="Imp">`Imp`</a>: 未完了 (imperfect)

未完了は過去時制の特殊事例であり，ブルガリア語やクロアチア語などで用いられる．注意したいのは，未完了時制が常に 過去時制 + 未完了アスペクト と同じでないことである．例えば，ブルガリア語には動詞の意味に固有の語彙的アスペクトが含まれるが．これは文法的アスペクトと常に合致するわけではない．主節において未完了動詞は未完了時制をもち完了動詞が完了時制をもつとはいえ，埋め込み節内で両者の規則が破られることもある．

#### 例

* [bg] _тя оставаше, където той и да <b>отидеше</b>_ / _tja ostavaše, kădeto toj i da <b>otideše</b>_ “it remained where he left it”



### <a name="Pqp">`Pqp`</a>: 大過去 (pluperfect)

大過去は過去に起きた特定の行為よりも前に起こった行為を指す．英語において大過去 (過去完了) が分析的に形成される場合には，この値が適用されない．この値はポルトガル語などに適用される．

#### 例

* [pt] _afirmou que os sequestradores já <b>ligaram</b>_ “he said that the kidnappers had already called”
