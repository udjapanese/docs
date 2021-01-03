---
layout: feature
title: 'VerbForm'
shortdef: 'form of verb or deverbative'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Conv">Conv</a></td>
  <td><a href="#Fin">Fin</a></td>
  <td><a href="#Gdv">Gdv</a></td>
  <td><a href="#Ger">Ger</a></td>
  <td><a href="#Inf">Inf</a></td>
  <td><a href="#Part">Part</a></td>
  <td><a href="#Sup">Sup</a></td>
  <td><a href="#Vnoun">Vnoun</a></td>
</tr>
</table>

名前からして，この素性は[動詞 (verbs)](u-pos/VERB) だけに適用されるように思えるが，実際はそうでない．当該形式が動詞か他の品詞 ([名詞 (nouns)](u-pos/NOUN), [形容詞 (adjectives)](u-pos/ADJ)，[副詞 (adverbs)](u-pos/ADV)) のどちらに属するかが不明瞭であるような言語も存在するからである．
例えば，分詞 (participles) は動詞か形容詞のいずれに分類されるが，これは言語やコンテクストに左右される．どちらの場合であっても，`VerbForm=Part`は他の動詞形や形容詞形から区別するのに用いられるだろう．

### <a name="Fin">`Fin`</a>: 定動詞 (finite verb)


簡単な規則: [Mood]()の値が空でないとき，それは定動詞である．
しかし，タグセットによっては動詞形と法を1つの素性として表現する場合もあるので注意されたい．

#### 例

* [en] _I <b>do</b>, he <b>does</b>_

### <a name="Inf">`Inf`</a>: 不定詞 (infinitive)

多くの言語で，不定詞は動詞の引用形である．英語とは異なり，不定詞は定動詞と語形が異なる場合が多い．不定詞は助動詞 (auxiliaries) と組み合わせることで時制 (e.g. 未来時制 [cs] _budu <b>sedět</b> vletadle_ "I will sit in a plane") を迂言的に表すことがあり，それは法助動詞 (modal verbs) などの項として生起する．言語によっては不定詞が名詞のようにふるまうことがあり，名詞として使用される (英語の動名詞のように)．

#### 例

* [de] _ich muss <b>gehen</b>_ “I must <b>go</b>”

### <a name="Sup">`Sup`</a>: スピーヌム (supine)

スピーヌムは珍しい動詞形である．スピーヌムはスラブ語 (スロベニア語) のいくつかでは現存しており，移動動詞の項として不定詞の代わりに用いられる (old [cs] _jdu <b>spat</b>_ lit. _I-go sleep_)．

"スピーヌム"と呼ばれる動詞形はスウェーデン語にも存在する．これは分詞の特殊な形式をとり，動詞の合成的な過去形を形成する．スピーヌムは助動詞_ha_ (to have) の後に用いられるが，_vara_ (to be) には後続しない:

* 単純過去: I ate (the) dinner = _Jag åt maten_ (using preterite)
* 合成過去 (Composite past): I have eaten (the) dinner = _Jag har <b>ätit</b> maten_ (スピーヌムを用いて)
* 中性の過去分詞 (Past participle common): (The) dinner is eaten = _Maten är äten_ (using past participle)
* 般性の過去分詞 (Past participle neuter): (The) apple is eaten = _Äpplet är ätet_
* 複数の過去分詞 (Past participle plural): (The) apples are eaten = _Äpplena är ätna_ 

### <a name="Part">`Part`</a>: 分詞 (participle) 動詞的形容詞 (verbal adjective)

分詞 (participle) は動詞と形容詞の性質をもつ不定詞である．その用法は言語間で異なり，複雑時制 (complex tense) や受身 (passives) といった迂言的な動詞形で用いられる; また，純粋な形容詞としても用いられる．

他の素性は，過去/現在分詞の区別 (英語)，現在/受動分詞 (チェコ語)，未完了/完了分詞 (ヒンディー語) の区別に貢献する．

#### 例

* [en] _he could have <b>been prepared</b> if he had
  <b>forseen</b> it_; _I will be <b>driving</b> home_.

### <a name="Conv">`Conv`</a>: 副動詞 (converb), 同時形 (transgressive), 副詞的分詞 (adverbial participle), 動詞的副詞 (verbal adverb)

副動詞は副詞的分詞や同時形 (transgreessive) とも呼ばれ，これは動詞と副詞の性質をもつ不定動詞である．副動詞はスラブ語やインド・アーリヤ諸語に生起する．

この値はUDv1では`Trans`と呼ばれたが，UDv2では`Conv`と呼称されている．

#### 例

* [cs] _zírali na mne, pevně <b>svírajíce</b> své zbraně_ "they
  stared at me <b>while gripping</b> their guns firmly";
  _<b>udělavši</b> večeři, zavolala rodinu ke stolu_ "<b>having
  prepared</b> the dinner, she called her family to the table"

### <a name="Gdv">`Gdv`</a>: 動詞状形容詞 (gerundive)

動詞状形容詞はラテン語や古代ギリシア語で用いられ，動名詞 (gerund) と混同しないように注意したい．

### <a name="Ger">`Ger`</a>: 動名詞 (gerund)

動名詞は動詞と名詞の性質を備えた不定動詞である．英語において動名詞の形式は現在分詞と同一であるため，本タグセットでは両者を区別しない．

`VerbForm=Ger`の使用は推奨できない．スペイン語などでは_動名詞 (gerund)_という用語が混乱を生むので，別の値を用いることを推奨する: スペイン語 (および他のロマンス諸語) では，これは現在分詞を指すので`Tense=Pres|VerbForm=Part`としてラベル付けすべきである; スラブ語では副動詞 (副詞的分詞) を指すので，`VerbForm=Conv`としてラベル付けすべきである; また，UDv1では動詞名詞 (verbal nouns) に対して用いることが推奨されたので，UDv2では`VerbForm=Vnoun`を用いる．

しかし，素性`VerbForm=Ger`はUDv2でも利用可能であって，他の選択肢がなければ許容される．この素性は将来のバージョンで削除されるだろうが，ともかく包括的な調査が必要である．

#### 例

* [en] _I look forward to <b>seeing</b> you_; _he turns a blind
  eye to my <b>being</b> late_

### <a name="Vnoun">`Vnoun`</a>: 動詞的名詞 (verbal noun, masdar)

動詞的名詞は不定詞 (infinitives) とは区別される．研究者によっては，これは"masdars"と呼ばれることがある (e.g. Haspelmath, 1995)

#### 例

* [cs] _<b>dělání</b>_ "doing"

### 参考文献

* Haspelmath, Martin. 1995. The converb as a cross-linguistically valid category. _Converbs in Cross-Linguistic Perspective: Structure and Meaning of Adverbial Verb Forms – Adverbial Participles, Gerunds –,_ edited by Martin Haspelmath and Ekkehard König, Berlin: Mouton de Gruyter, Empirical Approaches to Language Typology, 1–56.

