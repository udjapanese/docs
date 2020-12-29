---
layout: feature
title: 'Case'
shortdef: 'case'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td style="background-color:cornflowerblue;color:white"><strong>Core:</strong> </td>
  <td colspan="4" align="center"><a href="#Abs">Abs</a></td>
  <td colspan="4" align="center"><a href="#Acc">Acc</a></td>
  <td colspan="3" align="center"><a href="#Erg">Erg</a></td>
  <td colspan="4" align="center"><a href="#Nom">Nom</a></td>
</tr>
<tr>
  <td colspan="2" style="background-color:cornflowerblue;color:white"><strong>Non-core:</strong> </td>
  <td><a href="#Abe">Abe</a></td>
  <td><a href="#Ben">Ben</a></td>
  <td><a href="#Cau">Cau</a></td>
  <td><a href="#Cmp">Cmp</a></td>
  <td><a href="#Cns">Cns</a></td>
  <td><a href="#Com">Com</a></td>
  <td><a href="#Dat">Dat</a></td>
  <td><a href="#Dis">Dis</a></td>
  <td><a href="#Equ">Equ</a></td>
  <td><a href="#Gen">Gen</a></td>
  <td><a href="#Ins">Ins</a></td>
  <td><a href="#Par">Par</a></td>
  <td><a href="#Tem">Tem</a></td>
  <td><a href="#Tra">Tra</a></td>
  <td><a href="#Voc">Voc</a></td>
</tr>
<tr>
  <td colspan="2" style="background-color:cornflowerblue;color:white"><strong>Local:</strong> </td>
  <td><a href="#Abl">Abl</a></td>
  <td><a href="#Add">Add</a></td>
  <td><a href="#Ade">Ade</a></td>
  <td><a href="#All">All</a></td>
  <td><a href="#Del">Del</a></td>
  <td><a href="#Ela">Ela</a></td>
  <td><a href="#Ess">Ess</a></td>
  <td><a href="#Ill">Ill</a></td>
  <td><a href="#Ine">Ine</a></td>
  <td><a href="#Lat">Lat</a></td>
  <td><a href="#Loc">Loc</a></td>
  <td><a href="#Per">Per</a></td>
  <td><a href="#Sub">Sub</a></td>
  <td><a href="#Sup">Sup</a></td>
  <td><a href="#Ter">Ter</a></td>
</tr>
</table>

通常，`Case`は[名詞 (nouns)](u-pos/NOUN)の屈折素性である．言語によっては，名詞との一致 (agree) を示す他の品詞  ([代名詞 (pronouns)](u-pos/PRON) [形容詞 (adjectives)](u-pos/ADJ), [限定詞 (determiners)](u-pos/DET), [数量詞 (numerals)](u-pos/NUM), [動詞 (verbs)](u-pos/VERB)) にも`Case`が用いられることがある．いくつかのタグセットでは，`Case`は[側置詞 (adpositions)](u-pos/ADP)の結合価 (valency) でもある (項が特定の格をとるように側置詞が指定する).
UDのツリーバンクで前置詞の結合価に格情報を記載することは余剰的である．同一の格素性が名詞側にも記載されるためである．

格は，特に自由語順言語において名詞句の文中における役割を決定するのに役立つ．例えば，主格 (nominative) と対格 (accusative) は動詞の主語と目的語を区別する．一方，固定語順言語においては，これらの文法的機能は文中の名詞句の位置から区別される．

ここでは，形態統語論的なレベルから，形態として現れる格 (拘束形態素) を扱うことにする. より高次なレベルでは格は_役割_という広い意味で解され，名詞に側置詞を加えることによって表現される．ある言語で接辞によって表現されるものは，他の言語では側置詞によって表現される (依存関係ラベルについては[u-dep/case]()を参照)．

#### 例

* [cs] 主格 (nominative) _matka_ "mother", 属格 (genitive) _matky_, 与格 (dative) _matce_,
  対格 (accusative) _matku_, 呼格 (vocative) _matko_, 所格 (locative) _matce_,
   具格 (instrumental) _matkou_
* [de] 主格 _der Mann_ "the man", 属格 _des Mannes_,
  与格 _dem Mann_, 対格 _den Mann_
* [en] 主格/直接 (direct) 格 _he, she_,
  対格/斜格 (oblique) _him, her._

下記にある個別の格についての記述は格の典型的な意味についての示唆を含んでいる．ただし，ここで言及した意味は実際に用いられた格で生起しない場合も多いことを銘記されたい．動詞，側置詞や他の語の結合価は，名詞が特定の結合価スロット (意味役割) を満たすには何らかの文法的格を取るように要求する．この説明は前置詞の意味の説明法とほぼ同一である: 英語の_in_の中心義が時空間上の場所を指すことには多くの人が同意するだろうが，場所の意味が弱い例も存在する：_In God we trust._ _Say it in
English._

いわゆるパニーニモデル (Paninian model) に基づくヒンディー語のコーパスでは，_vibhakti_という素性を用いる．これは，本ページにて記述した格素性と複数の後置詞を混合したものである．_vibhakti_の値 (value) は言語依存のものである
<!--Vibhakti can be mapped on
the Case values described here if we know 1. which source values are
bound morphemes (postpositions are separate nodes for us) and 2. what
is their meaning.-->
例えば，ベンガル語の属格 (`Gen`) は接辞_-ra_ (-র) を用いて標示する (i.e. vib=era).
ヒンディー語では，接辞は名詞と分離され，それは個別の語として表記される &ndash; 後置詞 _kā/kī/ke_ (का/की/के)
後置詞句が属格名詞句と解釈できるとしても，その名詞は属格とは扱われない．その代わり，後置詞は名詞に対して3のうち1つの格形式をとるように要求する: 斜格 (`Acc`)


### <a name="Nom">`Nom`</a>: 主格 (nominative) / 直接格 (direct)

名詞の語基形であり，引用形式 (見出し語) として用いられることが一般的である．多くの言語において，主格は節主語として使われる語形を指す．格が2つ，すなわち"direct"と"oblique"しかない言語では，直接格はNomとして標示される．

### <a name="Acc">`Acc`</a>: 対格 (accusative) / 斜格 (oblique)

対格/斜格はおそらく形態格の中で2番目に広く使われる格である．多くの言語において，対格は動詞の直接目的語として使われる語形を指す．格が"direct"と"oblique"の2つしかない言語では，斜格はAccと標示される．

### <a name="Abs">`Abs`</a>: 絶対格 (absolutive)

いくつかの言語 (e.g. バスク語) では主語と目的語の区別に関して主格-対格を用いない．その代わり，絶対格 (absolutive)-能格 (ergative) の対立によって区別される．

絶対格は自動詞の主語と他動詞の直接目的語を標示する．

### <a name="Erg">`Erg`</a>: 能格 (ergative)

いくつかの言語 (e.g. バスク語) では主語と目的語の区別に関して主格-対格を用いない． その代わり，絶対格 (absolutive)-能格 (ergative) の対立によって区別される．

能格は他動詞の主語を標示する．

### <a name="Dat">`Dat`</a>: 与格 (dative)

多くの言語で，与格は動詞の間接目的語の語形として用いられる．

#### 例

* [de] _Ich gebe <b>meinem Bruder</b> ein Geschenk._ "I give my
  brother a present." (_meinem Bruder_ "my brother" is dative and _ein
  Geschenk_ "a present" is accusative.)

### <a name="Gen">`Gen`</a>: 属格 (genitive)

属格の典型的な意味とは，名詞句が何らかの意味で支配項 (governor) に属することである: 英語では前置詞_of_に訳されることが多い．英語は_'s_を用いた"saxon genitive"を有する; ただし，その接辞はトークン化 (tokenization) の際名詞と分離するため，英語においては"saxon genitive"の素性を必要としない．

意味的な重なりが非常に大きいものの，属格の意味は所有性 (possessivity; [Poss]()) と同一ではない．
所有性は語彙の特性であり (i.e. 見出し語と曲用のパラダイム全体に適用される)，属格は見出し語における語形のサブセットの特徴に過ぎない．所有性の意味は明確に定義が与えられる一方で，属格は (他の格についても同様に) 所有とは関係ない概念を表す場合がある．例えば，[cs] _bez prezidentovy dcery_ "without the president's daughter" は前置詞 _bez_ "without"，所有形容詞_prezidentovy_ "president's"，および名詞_dcery_"daughter"を含んだ前置詞句である．所有形容詞は名詞_prezident_から派生したものであるが，それは名詞の形式を持つだけでなく，事実形容詞といえるのである (独立した見出し語とパラダイムを持つ)．加えて，形容詞と名詞は属格形で示される (主格形は_prezidentova dcera_)．この例において，属格は所有の意味をもたない．属格が生起するのは，前置詞の_bez_が属格の項を常に要求するからである．

#### 例

* [cs] _Praha je hlavní město <b>České republiky</b>._ "Prague is the
  capital <b>of the Czech Republic</b>."

バスク語において，Genは所有属格 (場所の属格と異なって) に用いられる: _<b>diktadorearen</b> erregimena_
"dictator's regime"; _diktadore_ "dictator".

### <a name="Voc">`Voc`</a>: 呼格 (vocative)

呼格は誰かを呼ぶときに用いられる名詞の特殊な形式を指す．呼格は有生名詞 (animate nouns) に生起するのが大半を占める (素性[Animacy]()を参照)．ただし，これは文法的な制約ではなく，無生物 (inanimate things) が呼ばれることもある．

#### 例

* [cs] _Co myslíš, <b>Filip</b><b>e</b>?_ "What do you think,
  <b>Filip</b>?"

### <a name="Loc">`Loc`</a>: 所格 (locative)

所格はその名の通り時空間の場所を表すことが多い．他の格と同様，場所でない意味も存在し，それは稀でなく生起する．ウラル諸語は所格ではなく場所や方向に関する緻密な格のセットを備えている．所格を持つ言語であっても，場所の役割は他の格によって表現されることもある (他の格が前置詞から要求される，といった理由で)．

スラブ諸語において，所格は前置詞との組み合わせで唯一用いられる格である (ただし，この制約は所格を有する他の言語には該当しない．)

#### 例

* [cs] _V <b>červenci</b> jsem byl ve <b>Švédsku</b>._ "In <b>July</b>
  I was in <b>Sweden</b>."
* [cs] _Mluvili jsme tam o <b>morfologii</b>._ "We talked there about
  <b>morphology</b>." (Non-locational non-temporal example)

### <a name="Ins">`Ins`</a>: 具格 (instrumental / instructive)

具格は，名詞が何かを行う道具として用いられることを示す ([cs] _psát
<b>perem</b>_ "to write <b>using a pen</b>" のように)．他の意味も可能であり，例えばチェコ語の前置詞_s_ "with"は具格を要求し，それは他の言語では共格 (comitative) として表現されるような意味を含む．

チェコ語の具格は，受動構文における行為者-目的語に対しても用いられる (cf. 英語の前置詞_by_)

#### 例

* [cs] _Tento zákon byl schválen <b>vládou</b>._ "This bill has been
  approved <b>by the government</b>." (受身の例)

意味的に類似した格にはinstructiveと呼ばれるものがあり，フィンランド語で稀に用いられる ("with (the aid of)" を表現する)．この格は不定詞に適用が可能であり，フィンランド語では名詞のようにふるまう．UDでは，具格とinstructiveに対して1つの包括的なラベルを割り当てている (具格はフィンランド語では定義されない).

#### 例

* [fi] _lähteä_ "to leave"; _2003 <b>lähtien</b>_ "since 2003" (2番目の不定詞がinstructive)
* [fi] _yllättää_ "to surprise"; _sekaantui <b>yllättäen</b>
  valtataisteluun_ lit. _was-involved-in by-surprise.Ins
  power-struggle.Ill._

### <a name="Par">`Par`</a>: 分格 (partitive)

フィンランド語では，分格は不定の事物や終了していない行為を表す．

#### 例

* [fi] _kolme <b>taloa</b>_ "three <b>houses</b>"; (the _-a_ suffix of
  _talo_)
* [fi] _rakastan tätä <b>taloa</b>_ "I love this <b>house</b>"
* [fi] _saanko lainata <b>kirjaa</b>?_ "can I borrow the <b>book</b>?"
  (the _-a_ suffix of _kirja_)
* [fi]_lasissa on <b>maitoa</b>_ "there is (some) <b>milk</b> in the
  glass"

対格と分格の比較: _ammuin karhun_ "I shot a bear.Acc" (and I know that it is dead); _ammuin karhua_ "I shot at a bear.Par" (but I may have missed).

分格の代わりに対格を使うことで，未来時制を代替する: _luen kirjan_ "I will read the book.Acc"; _luen kirjaa_
"I am reading the book.Par".

### <a name="Dis">`Dis`</a>: 分布格 (distributive)

分布格 (distributive case) は，何かが任意の時点において特定の集合の全成員に対して発生したことを伝達する．もしくは，頻度を表す場合もある．

#### 例

* [hu] _<b>fejenként</b>_ "per capita"
* [hu] _<b>esetenként</b>_ "in some cases"
* [hu] _<b>hetenként</b>_ "once per week, weekly"
* [hu] _<b>tízpercenként</b>_ "every ten minutes"

### <a name="Ess">`Ess`</a>: 様格 (essive / prolative)

様格は一時的な状態を表し，英語の"as a &hellip"に相当する; 様格に類似したものとして，バスク語ではprolativeと呼ばれるものがある．これも`Ess`とタグ付けされる．

#### 例

* [fi] _lapsi_ "child"; _<b>lapsena</b>_ "as a child / when he/she was child"
* [et] _laps_ "child"; _<b>lapsena</b>_ "as a child"
* [eu] _erreformista_ "reformer"; _<b>erreformistatzat</b>_ "as a reformer"

### <a name="Tra">`Tra`</a>: 変格 (translative / factive)

変格は状態変化を表す ("it becomes X", "it
changes to X")．"in language X" を表す句にも用いられ，Szegedmツリーバンクではこの格がfactiveと呼ばれる.

#### 例

* [fi] _pitkä_ "long"; _kasvoi <b>pitkäksi</b>_ "grew long"
* [fi] _englanti_ "English language"; _<b>englanniksi</b>_ "in/into English"
* [fi] _kello kuusi_ "six o'clock"; _kello <b>kuudeksi</b>_ "by six o'clock"
* [et] _kell kuus_ "six o'clock"; _kella <b>kuueks</b>_ "by six o'clock"
* [hu] _Oroszlány halott <b>várossá</b> válhat._ lit. _Oroszlány dead city.Tra
  could-become._ "Oroszlány could become a dead city."

### <a name="Com">`Com`</a>: 共格 Ucomitative / associative)

共格 (もしくは，associativeとも呼ばれる) は英語の"together with &hellip"に対応する;

#### 例

* [et] _koer_ "dog"; _<b>koeraga</b>_ "with dog"

### <a name="Abe">`Abe`</a>: 欠格 (abessive)

接格は英語の前置詞_without_に相当する．

#### 例

* [fi] _raha_ "money"; _<b>rahatta</b>_ "without money"

### <a name="Ine">`Ine`</a>: 内格 (inessive)

内格は何かの内部にある場所を表す.

#### 例

* [hu] _ház_ "house"; _<b>házban</b>_ "in the house"
* [fi] _talo_ "house"; _<b>talossa</b>_ "in the house"
* [et] _maja_ "house"; _<b>majas</b>_ "in the house"

### <a name="Ill">`Ill`</a>: 入格 (illative)

入格は何かへ入る方向を表す.

#### 例

* [hu] _ház_ "house"; _<b>házba</b>_ "into the house"
* [fi] _talo_ "house"; _<b>taloon</b>_ "into the house"
* [et] _maja_ "house"; _<b>majasse</b>_ "into the house"

### <a name="Ela">`Ela`</a>: 出格 (elative)

出格は何かから出る方向を表す．

#### 例

* [hu] _ház_ "house"; _<b>házból</b>_ "from the house"
* [fi] _talo_ "house"; _<b>talos</b><b>t</b><b>a</b>_ "from the house"
* [et] _maja_ "house"; _<b>majas</b><b>t</b>_ "from the house"

### <a name="Add">`Add`</a>: 追加格 (additive)

追加格は，エストニア語学者によって認定されるが，伝統文法では認識されていない格である．追加格はMultext-East Estonian タグセットやEesti keele puudepankに存在する．入格の意味を持つので，文法によっては追加格は入格の別形態とみなされている．この格の形式は単数形しかなく，全ての名詞に生起するわけではない．

#### 例

* [et] _riik_ "government"; _riigisse_ "to the government" (singular illative); _<b>riiki</b>_ "to the government" (singular additive)

### <a name="Ade">`Ade`</a>: 接格 (adessive)

接格は位置を表す．方向に関して対応する格には向格 (どこかへ向かって) と奪格 (どこかから)がある．

#### 例

* [hu] _pénztár_ "cash desk"; _<b>pénztárnál</b>_ "at the cash desk"
* [fi] _pöytä_ "table"; _<b>pöydällä</b>_ "on the table"
* [et] _laud_ "table"; _<b>laual</b>_ "on the table"

フィンランド語やエストニア語において接格は表面の位置を表すが，ハンガリー語にはこの意味はない．

### <a name="All">`All`</a>: 向格 (allative)

向格は方向を表す (着点は接格)．

#### 例

* [hu] _pénztár_ "cash desk"; _<b>pénztár</b><b>hoz</b>_ "to the cash desk"
* [fi] _pöytä_ "table"; _<b>pöydäll</b><b>e</b>_ "onto the table"

### <a name="Abl">`Abl`</a>: 奪格 (ablative)

奪格の典型的意味: ある点からみた方向

#### 例

* [hu] _a <b>barátomtól</b> jövök_ "I'm coming <b>from my friend</b>"
* [fi] _<b>pöydältä</b>_ "from the table"; _<b>katolta</b>_ "from the roof";
  _<b>rannalta</b>_ "from the beach"

### <a name="Sup">`Sup`</a>: 上格 (superessive)

上格は主に[ハンガリー語](http://www.hungarianreference.com/Nouns/-n-superessive.aspx)で用いられ，頂点や表面上の位置を示す．

#### 例

* [hu] _asztal_ "table"; _<b>asztalon</b>_ "on the table"
* [hu] _könyvek_ "books"; _<b>könyveken</b>_ "on books"

### <a name="Sub">`Sub`</a>: 着格 (sublative)

着格はフィノ-ウゴル諸語で用いられ，動作の着点を表す．元々は物理的な位置 (e.g. "to climb a tree") を表していたが，その拡張として比喩的な使用 (e.g. "to university") もある.

#### 例

* [hu] _Belgrádtól 150 <b>kilométerre délnyugatra</b>_ lit.
  _Belgrade.Abl 150 kilometer.Sub southwest.Sub_ "150 kilometers
  southwest of Belgrade"
* [hu] _hajó_ "ship"; _<b>hajóra</b>_ "onto the ship"
* [hu] _<b>bokorra</b>_ "on the shrub"

### <a name="Del">`Del`</a>: 離格 (delative)

離格は主に[ハンガリー語](http://www.hungarianreference.com/Nouns/ról-rol-delative.aspx)で用いられ，何から動くことを表す ("moved off the table"のように). 他の意味も可能で，例えば"about something"などがある．

#### 例

* [hu] _asztal_ "table"; _az <b>asztal</b><b>ról</b>_ "off the table"
* [hu]_<b>Budapestről</b> jövök_ "I am coming from Budapest"

### <a name="Lat">`Lat`</a>: 方向格 (lative / directional allative)

方向格は どこかへ/どこかに/どこかの中へ/どこかの上に の動作を示す．類似したものにバスク語ではdirectional allative
(スペイン語: _adlativo direccional_) と呼ばれるものがある．しかし，方向格は典型的には向格，入格および着格を合わせたものと考えられる．一方，バスク語では方向格は向格から派生したものであり，存在が独立している．

#### 例

* [eu] _behe_ "low"; _<b>beherantz</b>_ "down"

### <a name="Per">`Per`</a>: 通格 (perlative)

通格は何かに沿う動作を示し，ワルピリ語において用いられる (Andrews 2007, p.162).
Unimorphでは英語の前置詞“along”を彼らが呼ぶところのprolative/translativeの関連から論じている; UDでは両者に対して別の定義を与える．

#### 例

* [wbp] _yurutu_ “road”; _<b>yurutuwana</b>_ “along the road” (_Pirli kalujana <b>yurutuwana</b> yirrarni_ “They are putting stones along the road”)

### <a name="Tem">`Tem`</a>: 時格 (temporal)

時格は時間を示すのに用いられる．

#### 例

* [hu] _<b>hétkor</b>_ "at seven (o'clock)"; _<b>éjfélkor</b>_ "at midnight";
  _<b>karácsonykor</b>_ "at Christmas"

### <a name="Ter">`Ter`</a>: 到格 (terminative / terminal allative)

到格は時空間上の終点を表し，類似したものとしてバスク語にはterminal allativeと呼ばれるもの (スペイン語:
_adlativo terminal_) がある.

#### 例

* [et] _<b>j&otilde;eni</b>_ "down to the river"; _kella <b>kuueni</b>_
  "till six o'clock"
* [hu] _a <b>házig</b>_ "up to the house"; _hat <b>óráig</b>_ "till
  six o'clock"
* [eu] _erdi_ "half"; _<b>erdiraino</b>_ "up to the half"

### <a name="Cau">`Cau`</a>: causative / motivative / purposive

この格を持つ名詞は何かの原因となる．ハンガリー語では貨幣に用いられる ("to buy something _for_ the
money") ことが多いようで，他にも，目的 (goal) を意味することがある．

#### 例

* [hu] _Egy világcég benzinkútjánál 7183 <b>forintért</b> tankoltam._
  lit. _a world-wide.company petrol.station.Ade 7183 forint.Cau
  refueled_ "I refueled my car at the petrol station of a world-wide
  company for 7183 forints."
* [hu] _Elmentem a boltba <b>tejért</b>._ lit. _went the shop.Ill
  milk.Cau_ "I went to the shop to buy milk."
* [eu] _jokaera_ "behavior"; _<b>jokaeragatik</b>_ "because of
  behavior"

### <a name="Ben">`Ben`</a>: 受益者格 (benefactive / destinative)

受益者格は英語の前置詞_for_に相当する．

#### 例

* [eu] _mutil_ "boy"; _<b>mutilarentzat</b>_ "for boys"

### <a name="Cns">`Cns`</a>: considerative

considerativeは交換 (exchange) によって与えられる物を示し，この格はワルピリ語で用いられる (Andrews 2007, p.164).

#### 例

* [wbp] _miyi_ “food”; _<b>miyiwanawana</b>_ “for food” (_Japanangkarlu kaju karli yinyi <b>miyiwanawana</b>_ “Japanangka is giving me a boomerang in exchange for food”)

### <a name="Cmp">`Cmp`</a>: 比較格 (comparative)

比較格は“than X”を意味する．これは比較基準を標示し，比較の[程度 (Degree)]()とは異なる．後者は比較される物の性質を標示するものである．比較格はドラヴィダ語や北東コーカサス諸語において現れる．

### <a name="Equ">`Equ`</a>: 等格 (equative)

等格は “X-like”, “similar to X”, “same as X”を意味する．比較基準を標示し，これは比較される物の性質を標示する[Degree]()とは異なる．等格はトルコ語において現れる．

#### 例

* [tr] _ben_ "I"; _<b>bence</b>_ "like me"

# 参考文献

* Avery D. Andrews: The major functions of the noun phrase. In: Timothy Shopen (ed.) (2007): Language Typology and Syntactic Description, Volume I: Clause Structure. Second Edition. Cambridge University Press. ISBN 978-0-521-58156-1.
