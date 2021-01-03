---
layout: feature
title: 'Polite'
shortdef: 'politeness'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Elev">Elev</a></td>
  <td><a href="#Form">Form</a></td>
  <td><a href="#Humb">Humb</a></td>
  <td><a href="#Infm">Infm</a></td>
</tr>
</table>

丁寧さ (politenss) や尊敬 (respect) を表す手段は多岐にわたる; 1つの手段として，形態論的な方法がある．言語学の文献によると，丁寧さの次元は3つから4つあるとされる．素性`Polite`は今のところ2つの次元についてカバーしている; UDの将来のバージョンでは，必要に応じて洗練された値 (value) の体系が構築されるだろう．現時点でカバーされる2つの軸 (axis) とは次のものである:

* 話者-指示対象 (聞き手が指示対象である場合も，これに含まれる)
* 話者-聞き手 (聞き手が指示対象ではないが，聞き手が誰かによって語形が変化する)

印欧語において代名詞が発話に含まれる際に代名詞もしくは動詞の人称 (person) および数 (number) が変更される現象は，話者-指示対象の軸に属する．尊敬代名詞 (honorific pronouns) は聞き手を指示するために用いられるからである．

チェコ語ではフォーマルな2人称が単複同形であり，インフォーマルな2人称複数とも同一である．そのため，フォーマルな言い方をする場合であっても代名詞と定の動詞 (分詞 (participle) はそうでない) は特別な形式を持たない (すなわち，フォーマルな単数形はインフォーマルな単数形と同一であるが，インフォーマルな複数形とは同一でない).

ドイツ語，スペイン語もしくはヒンディー語では，数と人称が変化する (インフォーマルな3人称はフォーマルな2人称として用いられる)．さらに，フォーマルな使用域 (register) でのみ生起する特別な代名詞がある ([de] _Sie;_ [es] _usted, ustedes;_
[hi] आप _āpa_).

日本語では，動詞と他の語は丁寧さを表す形式とインフォーマルな形式を持つ．しかし，丁寧さを表す形式は聞き手を指示しない (2人称には存在しない)．主題 (topic) が聞き手に関与しないとしても，これらの形式は聞き手が誰なのかを示すために用いられる．この種の丁寧さを表すことばは丁寧語 (teineigo) と呼ばれ，これは話者-聞き手の軸に属する．しかし，現行の取り組みでは両軸に対して同じ値を用いる．つまり，`Polite=Form`が丁寧語にも用いられるということである．


### <a name="Infm">`Infm`</a>: インフォーマルな使用域 (informal register)

使用法は多岐にわたる．ただし，当該言語が丁寧さのレベルを区別するとすれば，インフォーマルな使用域とは家族や近しい友人とのコミュニケーションを意味する．

例:

* [cs] _<b>ty jdeš / vy jdete</b>_ (you go.Sing/Plur)
* [de] _<b>du gehst / ihr geht</b>_ (you go.Sing/Plur)
* [es] _<b>tú vas / vosotros vais</b>_ (you go.Sing/Plur)
* [ja] <b>行かない _ikanai_</b> (will not go)

### <a name="Form">`Form`</a>: フォーマルな使用域 (formal register)

この使用法は多岐にわたる．当該言語が丁寧さに関して区別するのであれば，フォーマルな使用域とは，知らない人および話者よりも社会的地位が高い人とのコミュニケーションを意味する．

例:

* [cs] _<b>vy jdete</b>_ (you go.Sing/Plur)
* [de] _<b>Sie gehen</b>_ (you go.Sing/Plur)
* [es] _<b>usted va / ustedes van</b>_ (you go.Sing/Plur)
* [ja] <b>行きません _ikimasen_</b> (will not go)

### <a name="Elev">`Elev`</a>: 指示対象の格上げ (referent elevating)

この使用域は話者-指示対象の軸に属し，フォーマルな使用域のサブタイプに属するものとして捉えられる．例としては日本語の尊敬語 (sonkeigo) があり，これは指示対象の地位を上げるような尊敬形 (honorific forms) の集合を指す．

* [ja] <b>なさる _nasaru,_</b> なさいます _nasaimasu_ (to do; 客や目上の人について話す場合)

### <a name="Humb">`Humb`</a>: 話者の謙遜 (speaker humbling)

この使用域は話者-指示対象の軸に属し，フォーマルな使用域のサブタイプに属するものとして捉えられる．例としては日本語の謙譲語 (kenjōgo) があり，これは話者の地位を下げることによって相対的に指示対象の地位を上げるような尊敬形 (honorific forms) の集合を指す．

* [ja] <b>いたす _itasu,_</b> いたします _itashimasu_ (to do; 話者や話者の属するグループの成員による行為を指す場合)

### 参考文献

* Brown, Penelope and Stephen C. Levinson. 1987. Politeness: Some Universals in Language Usage. Studies in Interactional Sociolinguistics, Cambridge, UK: Cambridge University Press.
* Comrie, Bernard. 1976. Linguistic politeness axes: Speaker-addressee, speaker-referent, speaker-bystander. Pragmatics Microfiche 1.7(A3). Department of Linguistics, University of
Cambridge.
* Wenger, James R. 1982. Some Universals of Honorific Language with Special Reference to Japanese. Ph.D. thesis, University of Arizona, Tucson, AZ.
